# Приложение "Марсоход" по принципам TDD. MarsRoverTDD

## Описание задачи:

Космическое агентство планирует высадить группу роботов-марсоходов на красную планету с целью исследования плато прямоугольной формы. Предполагается, что бортовые камеры роботов фиксируют полный обзор окружающей местности и затем отправят сделанные снимки на Землю.

Позиция марсохода определяется двумя координатами: `x` и `y`. Положение камеры обозначается буквой, которая определяет одну из четырех сторон света. Например, `0, 0, N` означает что робот стоит в левом нижнем углу и смотрит на север.

Управление марсоходом происходит путем отправки одной из трех команд - `L`, `R` или `M`. `L` и `R` означают поворот на 90 градусов в соответствующую сторону. `M` - перемещение на вперед на одну координату.

Первая строка входа - координаты верхнего правого угла плато. Координаты нижнего левого угла по умолчанию всегда равны `0, 0`. Каждый робот имеет две строки ввода: первая означает текущее положение марсохода и направление камеры (две целых цифры и буква, разделенные пробелами), вторая - инструкции по передвижению.

Роботы передвигаются последовательно, т.е. следующий марсоход не начнет движение прежде, чем остановится текущий.

## Пример тестового ввода:

`5 5` 👈 верхний правый угол плато  
'2' 👈 марсоходов на плато
`1 2 N` 👈 текущее положение и направление камеры первого марсохода  
`LMLMLMLMM` 👈 управление положением первого марсохода  
`3 3 E` 👈 текущее положение и направление камеры второго марсохода  
`MMRMMRMRRM` 👈 управление положением второго марсохода

## Пример тестового вывода:

`1 3 N` 👈 конечное положение и направление камеры первого марсохода  
`5 1 E` 👈 конечное положение и направление камеры второго марсохода

# Требования к инфраструктуре проекта:

- Деплоймент-юнит должен собираться одной кнопкой (`build.sh`).
- Проект со всей инфраструктурой должен разворачиваться и запускаться локально также одной кнопкой (`run.sh` для запуска, `stop.sh` для остановки, например через `docker-compose`).
- Проект содержит средства обнаружения ошибок и других проблем с кодом (высокая цикломатическая сложность, большое количество параметров и т.п.).
- Проект не должен содержать нарушений code-style.
- Проект не должен содержать warning'ов.
- Проект не должен содержать зависимости со `SNAPSHOT` версиями.
- При сборке должна отображаться информация об устаревших зависимостях.
- Разработчик должен легко понимать, почему упала сборка (как локально, так и на CI-сервере).
- Подумайте и добавьте свои правила автоматизации/инструменты, которые считаете нужными и которые помогли бы вам в работе
- Формулировка “не должен содержать” обозначает, что сборка должна завершиться неуспехом в случае нарушения условия.
- В качестве СI-сервера возьмите GitHub Actions, бесплатного доступа будет вполне достаточно.
- Способ сдачи задания - форкнуть исходный репозиторий, сделать все необходимые правки, прислать нам ссылку.
