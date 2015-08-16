# Табло аэропорта 

## Задание
Сверстайте табло аэропорта. На нём должны быть представлены следующие данные:
* тип рейса (вылет/прилёт; например это может быть иконка);
* номер рейса;
* авиакомпания;
* логотип авиакомпании;
* тип воздушного судна;
* аэропорт назначения;
* плановое время вылета или прилёта;
* статус рейса (для вылетающих: регистрация, ожидание посадки, посадка закончена, вылетел; для прилетающих: по расписанию, летит, приземлился; для всех: задерживается до HH:MM, отменён);
* примечание (например, информация о код-шеринге с другими авиакомпаниями).

В качестве источника можно использовать данные онлайн-табло любого аэропорта мира.
Дизайн оформления выберите на своё усмотрение, при этом необходимо реализовать следующее:
* по наведению курсора на определённое место в табло контрастным цветом выделяются соответствующие строка и столбец;
* нечётные строки табло темнее чётных;
* количество отображаемых данных по высоте больше высоты экрана, при прокрутке заголовок таблицы приклеивается к верхней части видимой области окна браузера;
* при изменении ширины экрана браузера в табло автоматически скрываются и/или сокращаются значения наименее важных столбцов (например, при ширине 1000 пикселей вы показываете всю таблицу, при ширине 900 пикселей — убираете название авиакомпании, оставляя только логотип, 800 пикселей — сокращаете название воздушного судна (Boeing 737-800 -> B737) и так далее);
* в дополнение к предыдущему пункту сделайте так, чтобы по клику на соответствующую строчку в выплывающем окне показывались все данные рейса;
* два чекбокса над самим табло: прилёт и вылет, по нажатию показываются только соответствующие рейсы.

Плюсом будет, если вам удастся реализовать табло без JavaScript.
Результат пришлите в виде двух ссылок: на работающий пример и на исходный код на GitHub.

## Решение
Данное задание было выполнено при помощи HTML и CSS, без использования JavaScript. Данные брались импровизированные, по примеру сервиса [яндекс.расписания](https://rasp.yandex.ru/search/plane/?toName=%D0%A1%D0%B0%D0%BD%D0%BA%D1%82-%D0%9F%D0%B5%D1%82%D0%B5%D1%80%D0%B1%D1%83%D1%80%D0%B3&fromName=%D0%9C%D0%BE%D1%81%D0%BA%D0%B2%D0%B0).

Таблица была проверена и корректно отображалась в следующих браузерах: Google Chrome 44, Mozilla Firefox 40, Яндекс.Браузер 15, Internet Explorer 11.

## Проблемы
Основная проблема, с которой пришлось столкнуться при верстке таблицы, это сохранение чередования цвета фона в строках таблицы при скрытии одного из типов авиа-рейсов (прилет/вылет).

Обычный селектор ```nth-child```, примененный к строкам таблицы, в данном случае, не решает проблему, т.к. он применяется и к элементам со свойством ```display: none```. Соответственно, чередование цветов сбивается.

Для решения проблемы я использовал заливку фона тела таблицы [линейным градиентом](http://htmlbook.ru/CSS3-na-primerakh/lineinyi-gradient). При использовании такого метода чередование цветов в строках сохраняется.

## Демонстрация
[Рабочий пример на GitHub Pages](http://oktava6.github.io/Airport-table/)

Исходный код выше.
