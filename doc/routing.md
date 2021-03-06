Routing
=========

Правильно определенный маршрут содержит имя контроллера и имя Action (функция в классе контроллера).

Пусть паттерн роута будет задаваться регулярным выражением.

Значение для паттерна будет простым массивом, но в массиве значения будут означать:
```["имя_контроллера", "action", "параметр_1", "параметр_2", ... ]```

Например:
```json
{
  "routing": {
    "about-us": ["page", "about"],
    "company/(\w+)": ["company", "show", "$1"],
    "products": ["products", "index"],
    "products/(\w+)/(\d+)": ["products", "show", "$1", "$2"]
  }
}
```

При этом дефолтный роут который будет срабатывать если ничего не задано:
```json
{
  "routing": {
    "(\w+)": ["$1", "index"],
    "(\w+)/(\w+)": ["$1", "$2"]
  }
}
```  
