# itransTask3

На языке C# или JavaScript в соответствии со своей группой реализовать скрипт, который реализует обобщенную игру камень-ножницы-бумага (любое число произвольных комбинаций).
При запуске параметрами командной строки (аргументы метода Main в случае C#, process.argv под Node.js) передаётся нечётное число >=3 неповторяющихся строк (при неправильно заданных аргументах необходимо вывести аккуратное сообщение об ошибке — что именно неверно, пример как правильно). Все сообщения на английском языке. Эти строки — это ходы (например, Камень Ножницы Бумага или Камень Ножницы Бумага Ящерица Спок или 1 2 3 4 5 6 7 8 9).

Важно: ходы передаются аргументами командной строки, вы их не парсите из потока ввода (например, ход может содержать пробел, но для вашего кода это не должно иметь никакого значения).
Победа определяется так — половина следующих по кругу выигрывает, половина предыдущих по кругу проигрывает (семантика строк не важна, в какой последовательности что пользователь ввел, в такую игру и играет, даже если по его порядку камень проигрывает ножницам — для вас содержимое строк не важно).
Скрипт генерирует криптографически стойкий случайный ключ случайный ключ (RandomNumberGenerator в C# или что-то вроде https://www.npmjs.com/package/random-number-csprng) длиной не менее 256 бит, делает свой ход, вычисляет HMAC (на базе SHA2 или SHA3) от хода со сгенерированным ключом, показывает пользователя HMAC. После этого пользователь получает "меню" 1 - Камень, 2 - Ножницы, ...., 0 - Exit. Пользователь делает свой выбор (при некорректном вводе опять отображается "меню"). Скрипт показывает кто победил, ход компьютера и исходный ключ.
