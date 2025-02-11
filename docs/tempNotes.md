попросил у chatgpt:

```
распредели по категориям команды wezterm, объявленные в KeyAssignment enumeration:
ActivateCommandPalette;
ActivateCopyMode;
ActivateKeyTable;
ActivateLastTab;
ActivatePaneByIndex;
ActivatePaneDirection;
ActivateTab;
ActivateTabRelative;
ActivateTabRelativeNoWrap;
ActivateWindow;
ActivateWindowRelative;
ActivateWindowRelativeNoWrap;
AdjustPaneSize;
AttachDomain;
CharSelect;
ClearKeyTableStack;
ClearScrollback;
ClearSelection;
CloseCurrentPane;
CloseCurrentTab;
CompleteSelection;
CompleteSelectionOrOpenLinkAtMouseCursor;
Copy;
CopyTo;
DecreaseFontSize;
DetachDomain;
DisableDefaultAssignment;
EmitEvent;
ExtendSelectionToMouseCursor;
Hide;
HideApplication;
IncreaseFontSize;
InputSelector;
MoveTab;
MoveTabRelative;
Multiple;
Nop;
OpenLinkAtMouseCursor;
PaneSelect;
Paste;
PasteFrom;
PastePrimarySelection;
PopKeyTable;
PromptInputLine;
QuickSelect;
QuickSelectArgs;
QuitApplication;
ReloadConfiguration;
ResetFontAndWindowSize;
ResetFontSize;
ResetTerminal;
RotatePanes;
ScrollByCurrentEventWheelDelta;
ScrollByLine;
ScrollByPage;
ScrollToBottom;
ScrollToPrompt;
ScrollToTop;
Search;
SelectTextAtMouseCursor;
SendKey;
SendString;
SetPaneZoomState;
SetWindowLevel;
Show;
ShowDebugOverlay;
ShowLauncher;
ShowLauncherArgs;
ShowTabNavigator;
SpawnCommandInNewTab;
SpawnCommandInNewWindow;
SpawnTab;
SpawnWindow;
SplitHorizontal;
SplitPane;
SplitVertical;
StartWindowDrag;
SwitchToWorkspace;
SwitchWorkspaceRelative;
ToggleAlwaysOnBottom;
ToggleAlwaysOnTop;
ToggleFullScreen;
TogglePaneZoomState;
```

ChatGPT сказал:
Вот распределение команд WezTerm из KeyAssignment enumeration по категориям:

1. Управление окнами и вкладками (Windows & tabs)
ActivateLastTab – активировать последнюю вкладку
ActivateTab – активировать вкладку по индексу
ActivateTabRelative – переключиться на вкладку относительно текущей
ActivateTabRelativeNoWrap – переключиться на вкладку относительно текущей без зацикливания
ActivateWindow – активировать окно по индексу
ActivateWindowRelative – переключиться на окно относительно текущего
ActivateWindowRelativeNoWrap – переключиться на окно относительно текущего без зацикливания
MoveTab – переместить вкладку
MoveTabRelative – переместить вкладку относительно текущей позиции
QuitApplication – закрыть WezTerm
ReloadConfiguration – перезагрузить конфигурацию
SetWindowLevel – установить уровень окна
SwitchToWorkspace – переключиться на рабочее пространство
SwitchWorkspaceRelative – переключиться на соседнее рабочее пространство
Hide – скрыть окно
HideApplication – скрыть приложение
Show – показать окно

2. Управление панелями (сплитами) (Panes)
ActivatePaneByIndex – активировать панель по индексу
ActivatePaneDirection – активировать панель в заданном направлении
AdjustPaneSize – изменить размер панели
CloseCurrentPane – закрыть текущую панель
RotatePanes – повернуть панели
SetPaneZoomState – установить масштабирование панели
TogglePaneZoomState – переключить состояние зума панели
SplitHorizontal – разделить текущую панель по горизонтали
SplitVertical – разделить текущую панель по вертикали
SplitPane – разделить панель с дополнительными параметрами

3. Управление буфером и вводом (Input)
Copy – скопировать выделенный текст
CopyTo – скопировать в указанное место (клипборд, буфер и т. д.)
Paste – вставить содержимое буфера
PasteFrom – вставить из указанного источника
PastePrimarySelection – вставить из основного выделения (Linux)
SendKey – отправить клавишу
SendString – отправить строку

4. Скроллинг и навигация по истории (History)
ScrollByCurrentEventWheelDelta – прокручивать в зависимости от события колеса мыши
ScrollByLine – прокрутить на строку вверх/вниз
ScrollByPage – прокрутить на страницу вверх/вниз
ScrollToBottom – прокрутить в самый низ
ScrollToPrompt – прокрутить к ближайшему промту
ScrollToTop – прокрутить в самый верх

5. Выбор и поиск текста (Search & selection)
CharSelect – выбрать символ
CompleteSelection – завершить выделение
CompleteSelectionOrOpenLinkAtMouseCursor – завершить выделение или открыть ссылку
QuickSelect – быстрый выбор текста
QuickSelectArgs – быстрый выбор текста с параметрами
Search – поиск по буферу
SelectTextAtMouseCursor – выделить текст в позиции курсора
ClearSelection – очистить выделение

6. Командная оболочка и управление процессами
SpawnCommandInNewTab – запустить команду в новой вкладке
SpawnCommandInNewWindow – запустить команду в новом окне
SpawnTab – создать новую вкладку
SpawnWindow – создать новое окно
AttachDomain – подключиться к домену (например, к удаленному сеансу)
DetachDomain – отключиться от домена

7. Настройки и интерфейс (Interface)
ActivateCommandPalette – открыть палитру команд
ActivateCopyMode – включить режим копирования
ActivateKeyTable – активировать таблицу клавиш
ClearKeyTableStack – очистить стек таблицы клавиш
DisableDefaultAssignment – отключить стандартное действие клавиши
EmitEvent – отправить пользовательское событие
InputSelector – показать диалог выбора ввода
PromptInputLine – показать строку ввода
ShowLauncher – показать лаунчер
ShowLauncherArgs – показать лаунчер с параметрами
ShowTabNavigator – показать навигатор вкладок
ShowDebugOverlay – показать отладочный оверлей

8. Графика и внешний вид (View)
IncreaseFontSize – увеличить размер шрифта
DecreaseFontSize – уменьшить размер шрифта
ResetFontSize – сбросить размер шрифта
ResetFontAndWindowSize – сбросить шрифт и размер окна
ResetTerminal – сбросить терминал
ToggleAlwaysOnTop – переключить "поверх всех окон"
ToggleAlwaysOnBottom – переключить "под всеми окнами"
ToggleFullScreen – переключить полноэкранный режим

9. Прочее (Other)
Multiple – выполнить несколько действий
Nop – пустое действие (ничего не делать)
StartWindowDrag – начать перетаскивание окна