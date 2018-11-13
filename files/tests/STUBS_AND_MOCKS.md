## Stubs & mocks  

**Fakes** (подделки, муляжи) позволяют подсунуть нашему модулю другие реализации зависимостей, которые не станут лезть в базу, смотреть конфиги и т.д. Словом, будут делать только то, что от них требуется.

Выделяют два типа подделок: **стабы** (stubs) и **моки** (mocks).
    
Часто эти понятия путают. Разница в том, что стаб ничего не проверяет, а лишь имитирует заданное состояние. А мок - это объект, у которого есть ожидания. Например, что данный метод класса должен быть вызван определенное число раз. Иными словами, ваш тест никогда не сломается из-за "стаба", а вот из-за мока может.

С технической точки зрения это значит, что используя стабы в Assert мы проверяем состояние тестируемого класса или результат выполненного метода. При использовании мока мы проверяем, соответствую ли ожидания мока поведению тестируемого класса.

### Stub

![StUb](https://i.imgur.com/fvrJBYC.png)

### Mock

![Mock](https://i.imgur.com/SxF0QJ4.png)


### Тестирование состояния и тестирование поведения

Почему важно понимать, казалось бы, незначительную разницу между моками и стабами? Давайте представим, что нам нужно протестировать автоматическую систему полива. Можно подойти к этой задаче двумя способами:

### Тестирование состояния

Запускаем цикл (12 часов). И через 12 часов проверяем, хорошо ли политы растения, достаточно ли воды, каково состояние почвы и т.д.

### Тестирование взаимодействия

Установим датчики, которые будут засекать, когда полив начался и закончился, и сколько воды поступило из системы.

Стабы используются при тестировании состояния, а моки – взаимодействия. Лучше использовать не более одного мока на тест. Иначе с высокой вероятностью вы нарушите принцип «тестировать только одну вещь». При этом в одном тесте может быть сколько угодно стабов или же мок и стабы.
