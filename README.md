Добрый день!

### Предисловие

Данное руководство составлено мною, покупателем данного ноутбука "Lenovo IdeaPad L340 Gaming", и может помочь Вам, специалисту сервисного центра, выявить проблему. Текст руководства есть на рабочем столе ноутбука (вход в ОС без пароля), а также опубликован на https://github.com/igancev/lenovo-service-manual

Обязательно посмотрите пожалуйста записанные мною видео "Скрежет кулеров 1 - 4" на рабочем столе. Видео лучше смотреть и слушать с колонок, или наушников. Тест нужно проводить в тихом помещении. Видео загрузил на youtube, также они есть на рабочем столе ноутбука:

https://youtu.be/9I1LPQHDDw4

https://youtu.be/M8Rup0D5T9g

https://youtu.be/BBaibgKqWLI

https://youtu.be/1XrUmHIOKo0

Думаю Вы, как специалисты, и без меня знаете, как продиагностировать железо. Но на всякий случай, если в Ваших условиях почему - то не получится выявить неисправность, прикладываю данный мануал.

### Выявление проблемы (создание условий, при которых слышно нездоровый шум)

А именно "нездоровый" шум кулеров данного ноутбука (**есть еще предположение, что это писк дросселей/высокочастотный свист, подробнее о догадке тут** https://vk.com/topic-54940932_39175353), ниже я его буду называть для краткости "скрежет". Скрежет явно отличается от здоровых, громких шумов кулера, которые мы привыкли слышать. Скрежет - неоднородный, как своего рода кряхтение. Как будто что - то жарится в масле на сковороде. В обыденных условиях возникает при нагрузке на процессор, т.е. при вычислительных операциях, когда температура процессора возрастает, и кулеры охлаждения начинают работать интенсивнее. Но при максимальной скорости кулеров кряхтение невелируется. Оно есть, но становится более монотонным, и его сложнее услышать, т.к. здоровый шум вентиляции его перебивает. Иногда слышно при старте системы (если пуск не холодный, а перезагрузка), иногда просто при открытии браузера и загрузки к примеру youtube. При открытии разных програм, вообщем при повседневном использовании. Кряхтение отчетливее слышно когда процессор начинает работать на частоте более 4GHz, т.е. наверное когда включается turbo boost.

При обычной температуре ядер ~ 40° - 45° работа кулеров бесшумная, и скрежета нет. Для того, чтобы воспроизвести проблему, нужно нагрузить процессор. Можно открыть несколько предустановленных программ (firefox, phpstorm), что - нибудь в них поделать. При обыденной работе это происходит само собой, но сейчас, в данных условиях, это можно сделать искуственно, следующим образом:

Откроем 3 терминала. 

1) В одном запустим утилиту для мониторинга температуры ядер процессоров:

```bash
watch -n 1 sensors
```

2) (опционально) Запустим утилиту просмотра загруженности ядер процессора (для наглядности)

```bash
htop
```

3) Запустим утилиту, которая создаст нагрузку на ядра процессора:

```bash
stress --cpu 8 --io 4 --vm 2 --vm-bytes 128M --hdd 2 --timeout 20m
```

Увидим, как температура ядер возрастет до 60° - 80°, из - за возникшей нагрузки. Плавно будет нарастать шум кулеров ноутбука, и по мере нарастания можно будет услышать "скрежет", тот самый "нездоровый" звук. 

Обращаю внимание, что скрежет слышно более отчетливо в нижней части ноутбука, а именно в его левой части (если смотреть на экран).

В обыденной жизни скрежет более неоднородный, из - за чего более громкий. Считаю это заводским браком. 

Спасибо, если дочитали до конца! Надеюсь на Ваш профессианализм при выявлении. Успехов, и хорошего дня!
