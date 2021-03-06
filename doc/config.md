Config
======

Конфиг представляет собой массив произвольной структуры.
Класс конфига должен предоставлять возможность получить нужную запись.

Наиболее удобным форматом для задания является json.
Можно создавать сколько угодно файлов, в любом случае они будут объединятся в один массив.

Любой из компонентов фреймворка должен уметь работать совсем без массива конфигов, т.е. все параметры 
должны иметь значения по умолчанию.

Например структуру проекта сделали такой:
```
/config/
  config.json
  routing.json
  database.json
```

Внутри файлов будет такое:
config.json
```json
{
  "config": {
    "foo": "bar",
    "k": "v"
  }
}
```

routing.json
```json
{
  "routing": [
    ...
  ]
}
```

При этом нет никаких ограничений на количество файлов или конфигов в одном файле.

Для реалиазации параметров зависимых от окружения (config B extends A) можно использовать логику последний загруженый
перезаписывает загруженые ранее значения.
