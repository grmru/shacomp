# Об этом
Данная небольшая программка предназначена для поиска хешей в файле. Например, для локальной проверки наличия своего списка паролей в большом текстовом дамп-файле с сайта https://haveibeenpwned.com/Passwords.

# Как собрать исполняемый файл
Что бы Вы не волновались о безопасности данных, которые будут обрабатываться с помощью данного приложения, Вам предлагается самостоятельно скомпилировать исполняемый файл. Это всего лишь один файл на языке C# для .net.

## Windows
Если у Вас установлен .net версии 4.0, то Вы можете использовать скрипт ```build.cmd```. Или любым другим способом воспользоваться командой:
```
csc pwhashcompare.cs
```

## Другие OS
Вам необходимо установить mono.
После этого использовать команду:
```
mcs pwhashcompare.cs
```

# Использование
Для работы необходимо передать 4-ре аргумента:
1. Путь до директории, где лежат файлы, по которым необходимо производить поиск;
2. Маска для фильтрации файлов из директории, указанной в первом аргументе;
3. Файл со списком данных, которые собираетесь искать (список своих паролей);
4. Алгоритм получения хеша - sha1, sha256, md5.

### Пример для Windows:
``` batch
pwhashcompare.exe ./pwned_files "*.txt" mypasswords.txt sha1
```

### Пример для *nix:
``` bash
mono pwhashcompare.exe ./pwned_files "*.txt" mypasswords.txt sha1
```
