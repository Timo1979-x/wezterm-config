```
; d:\utils\scripts\wezterm.ahk
; "%LOCALAppData%\Microsoft\WindowsApps\AutoHotkey.exe" d:\utils\scripts\wezterm.ahk
#Requires AutoHotkey v2.0
#SingleInstance Force
#Warn

LoadConfig()
changeIcon()

return

;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
; Handle Hotkey events
ToggleConsole(ThisHotkey) {
  dim := GetActiveMonitorDimention()
  ;MsgBox( "monIndex: " . dim.index . " x: " . dim.x . " y: " . dim.y . " width: " . dim.width . " height: " . dim.height)
  DetectHiddenWindows(true)
  local hwnd_id := WinExist(windowMatcher)
  if (hwnd_id != 0) {
    DetectHiddenWindows(false)
    if WinActive() {
      WinHide()
    } else {
      DetectHiddenWindows(true)
      ; show window on top of monitor with your mouse cursor.
      ; window size set to width (1.0 * monitor pixel width) x height (heightRatio * monitor pixel height)
      ; WinMove(dim.x, dim.y, dim.width, dim.height * Float(heightRatio), hwnd_id)
      WinShow()
      WinActivate()
    }
  } else {
    try {
      Run(command)  ; see http://ahkscript.org/docs/commands/Run.htm
    } catch Error as e {
      TrayTip("Could not execute command", command, 3)
      Throw e
    }
  }
  return
}

GetActiveMonitorDimention() {
  dim := { index: 0, x: 0, y: 0, width: 0, height: 0 }
  CoordMode("Mouse", "Screen")
  MouseGetPos(&x, &y)
  local count := MonitorGetCount()
  loop count {
    MonitorGet(A_Index, &Left, &Top, &Right, &Bottom)
    if (x >= Left) && (x <= Right) && (y <= Bottom) && (y >= Top) {
      dim.index := A_Index
      dim.x := Left
      dim.y := Top
      dim.width := Abs(Right - Left)
      dim.height := Abs(Top - Bottom)
    }
  } until (dim.width > 0)
  return dim
}

LoadConfig() {
  global key, command, heightRatio, windowMatcher

  try {
    Hotkey(key, "Toggle")
  }

  command := "wezterm-gui.exe"
  windowMatcher := "ahk_exe wezterm-gui.exe"
  key := "^``" ; Ctrl + ~ (tilda)
  heightRatio := "0.6"

  ; keyboard key (or key-combination) to toggle the console
  try {
    Hotkey(key, ToggleConsole)
  } catch Error {
    TrayTip("Invalid key", "using default: <C-;>", 3)
    key := "^;"
    Hotkey(key, ToggleConsole)
  }
}

ButtonExit(A_ThisMenuItem, A_ThisMenuItemPos, MyMenu) {
  ExitApp()
  return
}

ToggleSuspend(A_ThisMenuItem, A_ThisMenuItemPos, MyMenu) {
  Suspend(-1)
  A_TrayMenu.ToggleCheck("&Suspend")
  return
}

Dummy(A_ThisMenuItem, A_ThisMenuItemPos, MyMenu) {
  return
}

changeIcon() {
  exePath := FindCommand()
  if (exePath != "") {
    TraySetIcon(exePath, 0)
  }

  ; Tray menu customization
  A_IconTip := "Quake Like Console (key: " . key . ")"
  Tray := A_TrayMenu
  Tray.Delete() ; remove standard Menu items
  Tray.Add("Quake Like Console", Dummy)
  Tray.Add("") ; separator
  Tray.Add("&Suspend", ToggleSuspend)
  Tray.Add("") ; separator
  Tray.Add("E&xit", ButtonExit)
}

FindCommand() {
  global command
  path := EnvGet("PATH")
  pathArray := StrSplit(path, ";")
  loop pathArray.Length {
    path := pathArray[A_Index] . "\" . command
    exists := FileExist(path)
    if (exists = "") {
    } else {
      return path
    }
  }
  return ""
}
```