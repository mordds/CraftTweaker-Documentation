# 日志记录器

如果 `print` 函数对你来说不够用的话，你可以使用日志记录器 `logger`。

## 日志记录

- logCommand(String message);
- logInfo(String message);
- logWarning(String message);
- logError(String message);

## 较少使用的方法

- logError(String message, Throwable exception);
- logPlayer([IPlayer](/Vanilla/Players/IPlayer) player);

你没法使用 Java 中的 Throwable 所以第一个函数没用。
第二个函数根本就没实现~
