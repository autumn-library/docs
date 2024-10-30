---
title: Первое приложение
order: 20
---

<!-- TODO: Тут должен быть какой-то заголовок с #, иначе рендерится некрасиво -->

## Инициализация приложения

Для инициализации контекста "ОСени" служит класс `Поделка`, который необходимо создать через `Новый` (один разочек можно и написать это вредное слово), а затем наполнить Желудями, Дубами и Напильниками. Нет, мы не упоролись, скоро расскажем, что тут к чему.

Инициализировать контекст можно так:

```1c
// file: main.os

#Использовать autumn

Поделка = Новый Поделка();
```

И... всё.

При создании Поделки ОСень автоматически просканирует все доступные в системе типов классы, определит, кто их них желудь, а то дуб, и последовательно добавит их в контекст.

Вероятно, помимо загрузки собственно ОСени, вы захотите так же зарегистрировать и собственные классы. Единственное, что для этого нужно, это выполнить обычное для OneScript подключение библиотек по имени или пути:

```1c
// file: main.os

#Использовать autumn
#Использовать "."

Поделка = Новый Поделка();
```

## Запуск приложения

После добавления всех желудей, дубов и прочих частей в нашу поделку мы готовы к запуску приложения.

```1c
Поделка.ЗапуститьПриложение();
```

В чем суть? Жизненный цикл нашей поделки разделен на две фазы:

- фаза инициализации, когда мы можем только добавлять в поделку новые компоненты, но еще не разрешаем им взаимодействовать;
- фаза выполнения, когда в нашу поделку вдыхается жизнь ~~и выдыхаются желуди~~, наше приложение запускается и мы можем наконец начать делать что-то полезное.