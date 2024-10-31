---
title: Алиасы компонентов
---

# Алиасы компонентов

У желудей все как у людей. Есть свои увлечения, субкультуры и даже может быть `&Прозвище`. Желудь `Василий` в силу своего темного прошлого "у своих" зовется не иначе как `Васян`. Как это отразить в ОСени?

```bsl
// file: Классы/Василий.os

&Желудь
&Прозвище("Васян")
Процедура ПриСозданииОбъекта()
КонецПроцедуры

```

Как же разные группы желудей могут обращаться к нашему Василию? Сделать это можно и по имени и по прозвищу. И отзовётся при этом один и тот же желудь:

```bsl
// file: main.os

Василий = Поделка.НайтиЖелудь("Василий");
Васян = Поделка.НайтиЖелудь("Васян");

Ожидаем.Что(Василий).Равен(Васян);
```

Василий может иметь много прозвищ. Поэтому аннотация &Прозвище повторяемая, т. е. на желудь ее можно навесить несколько раз с разными значениями и величать кого угодно и как угодно.