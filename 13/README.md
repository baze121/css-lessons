# Практикум: многоколоночные макеты
В этом практикуме мы рассмотрим, как создавать многоколоночные макеты,
основанные на обтекаемых элементах. Вы создадите трехколоночный резиновый и 
фиксированный дизайны. Кроме того, вы научитесь применять ряд других методов 
достижения аналогичного результата.
Чтобы начать обучение, вы должны иметь в распоряжении файлы с учебным
материалом. 
# Структурирование HTML-кода
Первый шаг в верстке макета на основе каскадных таблиц стилей — идентификация
различных элементов на странице. Вы делаете это, обертывая фрагменты HTML-кода
в контейнеры div, каждый из которых представляет отдельный элемент страницы.
1. Откройте файл index.html в редакторе HTML-кода и установите курсор на пустой
строке после HTML-комментария: `<!-- первая боковая панель -->`.
Как вы можете видеть, часть HTML-разметки уже сделана: на данный момент
созданы баннер и нижний колонтитул. Прежде чем создавать какие-либо стили,
вы должны добавить структуру и контент на страницу. Далее вы добавите элемент aside для левой боковой панели.
2. Добавьте открывающий тег `<aside>` для левой боковой панели: `<aside class =
"sidebar1">`. Затем нажмите клавишу Enter, чтобы перейти на новую строку.
В примере применяется HTML5-элемент aside, но для создания такой колонки
можно воспользоваться и элементом div.
Если бы вы создавали веб-страницу с нуля, то в этом пункте пришлось бы
добавлять HTML-код для боковой панели на странице и, возможно, определять список публикаций сайта, ссылки на родственные сайты и т. д. В данном
случае вам не придется этого делать. Код неупорядоченного списка ссылок
уже набран в отдельном файле. Осталось только скопировать его и добавить
на страницу.
3. Откройте файл sidebar1.txt, скопируйте его содержимое, а затем вернитесь к файлу index.html. 
Вставьте скопированный HTML-код после тега `<aside>`, который
вы создали в шаге 2 (или тега `<div>`, если вы решили использовать его).
Боковая панель почти готова. Осталось лишь закрыть элемент aside.
4. Сразу же после кода, который вы только что добавили, введите код `</aside>`.
Вы только добавили на страницу первый элемент макета. Чуть позже мы отформатируем его так, чтобы он был похож на колонку. 
Но сначала вы должны добавить еще немного кода.
5. Установите курсор на пустую строку после следующего HTML-комментария:
`<!-- основной контент -->`, а затем введите код `<article class = "main">`.
Этот раздел будет хранить главное содержимое страницы. Нужный HTML-код
вы также возьмете в другом файле.
6. Откройте файл main.txt, скопируйте его содержимое, вернитесь к файлу index.
html и вставьте скопированный код после тега `<article>`, который вы только что создали. 
Добавьте закрывающий тег `</article>` точно так же, как в шаге 4. Сохраните HTML-файл.
Это весь HTML-код, который нужен для создания дизайна. Теперь пришло
время переключиться на создание каскадной таблицы стилей.
# CSS-верстка
Если вы просмотрите страницу, то увидите, что для баннера, навигационных 
кнопок и текста стили уже созданы. Так получилось потому, что к странице 
присоединена внешняя таблица стилей с базовым форматированием. Далее нужно создать
стили для форматирования колонок на странице.
1. Откройте в редакторе HTML-кода файл styles.css.
Поскольку веб-страница использует внешнюю таблицу стилей, новые стили
будут добавляться в этот CSS-файл. Теперь вы работаете с двумя файлами:
HTML и CSS, поэтому перед просмотром страницы в браузере нужно убедиться
в том, что сохранены оба файла.
2. Перейдите в конец CSS-файла и найдите комментарий /* стили из практикума */. 
Добавьте ниже этого комментария следующий код:
.sidebar1 {
float: left;
width: 20%;
}
Стиль выравнивает боковую панель по левому краю страницы и задает ей
значение ширины, равное 20 %. Свойство width играет в этом стиле важную
роль: если только вы не выравниваете изображение, для которого задана ширина, 
всегда нужно ограничивать ширину обтекаемого (выравниваемого) элемента. В ином случае браузер установит ширину на основе контента внутри
обтекаемого элемента, что приведет к противоречивым результатам. Здесь
ширина задана в процентном отношении, стало быть, она определяется шириной данного контейнера. В нашем случае контейнером является элемент body,
который заполняет всю ширину окна браузера. Поэтому экранная ширина
боковой панели будет зависеть от ширины окна браузера, используемой посетителем.
3. Сохраните HTML- и CSS-файлы и просмотрите файл index.html в браузере.
Боковая панель теперь представляет собой колонку, выровненную по левому
краю.
Хоть это и типично для обтекаемых элементов, это не то, что нам нужно сейчас. Чтобы основной контент отобразился в виде отдельной колонки, следует добавить достаточное
по размеру поле слева. Это позволит отделить основной контент от
боковой панели.
4. Создайте стиль для второй колонки:
.main {
margin-left: 22%;
}
Поскольку ширина боковой панели составляет 20 %, поле размером 22 % смещает основной контент на дополнительные 2 %, создавая промежуток между
двумя колонками. Дополнительное пустое пространство не только повышает
читабельность текста, но и улучшает внешний вид страницы.
Взгляните на страницу, и увидите, что получился двухколоночный дизайн.
Добавление колонки
Как вы могли заметить, двухколоночный дизайн создать несложно. Добавив третью
колонку, вы сможете преподнести своим посетителям еще большее количество информации. Подобный дизайн также несложно создавать — действия в этом случае
практически такие же, как в предыдущей части этого практикума.
1. Откройте файл sidebar2.txt. Скопируйте из него весь HTML-код, а затем вернитесь к файлу index.html.
HTML-код для этой колонки помещается после элемента article с основным
контентом.
2. Найдите ближе к концу файла HTML-комментарий `<!-- вторая боковая панель -->`.
Щелкните кнопкой мыши на пустой строке ниже этого комментария.
Зачастую, когда для структурирования контента страницы используется много div-контейнеров, найти нужный закрывающий тег `</div>` бывает нелегко.
Вот почему HTML-комментарии, такие как этот, помогают определить HTML-
код на странице.
3. Введите код `<aside class="sidebar2>`, нажмите клавишу Enter и вставьте HTML-
код, который вы скопировали в шаге 1. Вновь нажмите клавишу Enter и добавьте закрывающий тег `</aside>`. Сохраните HTML-файл.
Закрыв элемент div, вы завершили HTML-код третьей колонки на странице.
Теперь приступим к форматированию этой колонки.
4. Вернитесь в редактор HTML-кода к файлу styles.css. Под стилем .main, который вы создали в шаге 4 в предыдущем подразделе, добавьте следующий
код:
.sidebar2 {
float: right;
width: 20%;
}
Указав данный стиль, вы выровняете колонку по правому краю страницы, чтобы по обе стороны основного контента располагались боковые панели.
5. Сохраните все файлы и просмотрите файл index.html в браузере.
Теперь вы должны увидеть нечто странное. Вторая боковая панель отображается ниже основного контента и даже накладывается на нижний колонтитул.
Проблема связана с порядком следования HTML-кода. Когда выравнивается
элемент, то его обтекает и появляется после него только тот HTML-код, который следует в коде за этим обтекаемым элементом. То есть, пока HTML-код
второй боковой панели следует за основным контентом, он появляется не рядом
с ним, а после него.
Справиться со сложившейся ситуацией можно двумя способами. Можно переместить HTML-код второй боковой панели (второй элемент aside), указав его
перед HTML-кодом основного контента (перед элементом article). Тогда первая боковая панель переместится влево, вторая — вправо, а основной контент
поднимется и разместится между ними.
Можно выровнять основной контент. Если установить его ширину таким
образом, чтобы ширина всех трех колонок не превышала 100 %, все они будут располагаться рядом. В текущем примере будет применен именно этот
вариант.
6. Отредактируйте стиль .main следующим образом:
.main {
float: left;
width: 60%;
}
Если сохранить CSS-файл и просмотреть страницу index.html в браузере, проявится еще одна проблема — внезапно все снова будет испорчено! Спокойствие:
это нижний колонтитул попытался обернуть все обтекаемые элементы и создал
тем самым хаос. Как уже ранее говорилось, когда элемент выравнивается и его
обтекает другой элемент, фоновый цвет и границы этого элемента фактически
расширяются под обтекаемый элемент. Странно, все вроде правильно, а результат разочаровывает. Вполне очевидно, что для решения проблемы нужно, чтобы
нижний колонтитул опустился ниже обтекаемых элементов.
7. После стиля .sidebar2 добавьте следующий код:
footer {
clear: both;
}
Как уже упоминалось, свойство clear может опустить элемент ниже колонок. 
В данном случае оно выталкивает нижний колонтитул ниже колонок.
# Добавление разрядки
Три колонки у вас уже есть, но текст выглядит слишком скученно. Эти три колонки практически касаются друг друга, и текст на правой боковой панели слишком
близко прижимается к краю окна браузера. Исправить ситуацию помогут небольшие отступы.
1. Добавьте отступы в стилях .sidebar1, .main и .sidebar2, придав их коду следующий
вид:
.sidebar1 {
float: left;
width: 20%;
padding: 0 20px 0 10px;
}
.main {
float: left;
width: 60%;
padding: 0 20px 0 20px;
}
.sidebar2 {
float: right;
width: 20%;
padding: 0 10px 0 10px;
}
Здесь используется сокращенная запись свойства padding. Числа представляют
верхний, правый, левый и нижний отступы соответственно. То есть в стиль
.sidebar1
добавлен верхний нулевой отступ, 20 пикселов отступа справа, нижний нулевой отступ и 10 пикселов отступа слева.
Если сохранить файл styles.css и просмотреть в браузере страницу index.html,
станет заметна еще одна проблема — выпадение обтекаемого элемента. В результате добавления отступов каждая колонка стала шире, а поскольку общая ширина
колонок (20 + 60 + 20) % уже составила в сумме 100 %, дополнительные отступы
опустили третью колонку под первые две. Это нужно срочно исправить!
Проблему можно решить несколькими способами. Во-первых, можно убрать
отступы из этих стилей и добавить их ко всем внутренним элементам. То есть
добавить 10 пикселов правого и левого отступов к элементам h2, h3, p и ul. Но это
довольно трудоемкий процесс.
Во-вторых, можно убрать отступы из стилей в CSS-файле, а затем в документе
index.html добавить в каждую колонку div-контейнер следующего вида:
    ```
    <aside class="sidebar1">
        <div class="innerColumn">
        … Сюда помещается контент …
        </div>
    </aside>
    ```
    Затем в файле styles.css нужно создать стиль для добавления отступов:
    ```
    .innerColumn {
        padding: 0 20px 0 10px;
    }
    ```
    Поскольку в стиле .innerColumn ширина не задается, контейнер просто разрастается, чтобы занять колонку, а отступы смещают все, что находится внутри него
    (заголовки, абзацы и т. д.), вовнутрь на 10 пикселов. Недостаток такого подхода
    состоит в необходимости добавления дополнительного кода.
    Существует еще один, более простой и широко поддерживаемый браузерами
    способ.
2. Добавьте в верхней части таблицы стилей еще один стиль (сразу после комментария /* сброс стилей браузера */):
    ```
    * {
        box-sizing: border-box;
    }
    ```
    В этом стиле используется универсальный селектор. Благодаря ему свойство
    box-sizing применяется к каждому элементу страницы. Присвоение этому свойству значения border-box
    инструктирует браузеры учитывать размер отступов
    и границ вместе со значением свойства width. То есть дополнительные отступы
    не добавляются к установленному ранее значению ширины. Тем самым предотвращаются любые выпадения
    обтекаемых элементов, поскольку колонки составляют не более 100 % ширины окна браузера.
    И наконец, добавьте границы, чтобы отделить колонки друг от друга.
3. Отредактируйте стиль .main, добавив в него свойства левой и правой границ:
    ```
    .main {
    float: left;
    width: 60%;
    padding: 0 20px 0 20px;
    border-left: dashed 1px rgb(153,153,153);
    border-right: dashed 1px rgb(153,153,153);
    }
    ```
    Эти свойства приведут к добавлению прямых линий с каждой стороны раздела
    основного контента.Просмотрете страницу в браузере.
# Ограничение ширины
В настоящее время у страницы резиновый дизайн, означающий, что контент расширяется, чтобы заполнить всю ширину окна браузера. Но, допустим, вам нужно,
чтобы страница все время оставалась одной и той же ширины, так как вас не
устраивает, как она выглядит на широкоформатных мониторах или при очень маленьком размере окна браузера. Изменить резиновый дизайн на фиксированный
легко. Начните с добавления HTML-кода.
1. Вернитесь в редактор HTML-кода к файлу index.html. Сразу же за открывающим
тегом `<body>` добавьте новый элемент div:
```
<div class="pageWrapper">
```
Таким образом вы заключите всю страницу в блок, который будет использоваться для управления шириной страницы. Вы должны убедиться, что этот
контейнер закрыт.
2. Добавьте закрывающий тег `</div>` перед `</body>`:
    ```
    </div>
    </body>
    ```
    Теперь, когда созданный контейнер включает в себя все содержимое страницы,
    вы можете управлять ее шириной, изменяя ширину данного контейнера.
3. Сохраните HTML-файл и перейдите к редактированию файла styles.css. Добавьте еще один стиль:
    ```
    .pageWrapper {
        width: 960px;
    }
    ```
    Если сохранить CSS- и HTML-файлы и просмотреть страницу index.html в браузере, вы увидите, 
    что ее контент действительно заключен в пространство шириной 960 пикселов. Если сделать ширину окна браузера меньше 960 пикселов,
    появятся полосы прокрутки.
    Но вам, разумеется, не нужно устанавливать точную ширину. Если хотите, чтобы страница поместилась в более узком (скажем, имеющем ширину 760 пикселов) окне браузера, лучше избегать ограничения ширины. Настоящая проблема
    заключается в том, что страницу становится трудно читать в слишком широком
    окне браузера. Другой подход заключается в использовании свойства max-width,
    которое не позволяет div-контейнеру увеличиваться свыше определенной величины, но не препятствует более узкому значению его ширины для помещения
    на небольших экранах. Раз уж вы за это взялись, нужно также центрировать
    div-контейнер в окне браузера.
4. Измените только что созданный в файле styles.css стиль .pageWrapper, чтобы он
приобрел следующий вид:
```
.pageWrapper {
width: 960px;
margin: 0 auto;
}
```
Свойство max-width присуще резиновому макету, но только до конкретного предела. 
В данном случае, когда окно браузера шире 1200 пикселов, div-контейнер
не будет увеличиваться. Свойству margin присвоено значение 0 auto, обеспечивающее нулевые поля сверху и снизу и автоматические поля слева и справа.
Последняя настройка (auto) позволяет браузеру автоматически определять размер полей путем равномерного деления пространства между левой и правой
сторонами и центрируя таким образом div-контейнер в окне браузера.

# Резиновый/фиксированный макет
Страница выглядит вполне привлекательно, но могла бы выглядеть лучше, если
бы черный фон для навигационной панели вверху и для колонтитула внизу, 
а также темно-фиолетовый градиент в баннере распространялись на ширину всей страницы. 
Поскольку навигационная панель, баннер и нижний колонтитул
находятся внутри div-контейнера pageWrapper, эти фоновые цвета прекращают отображаться, когда окно браузера становится шире 1200 пикселов. Вместо этого нуж-
но оставить часть страницы — элементы с фоновым цветом — резиновой, при этом
ограничив ширину элементов с основным контентом.
Фоновый цвет для навигационной панели применяется к элементу nav, фиолетовый градиент — к элементу header, черный фон в нижнем колонтитуле — к элементу footer. 
Чтобы фон каждого из этих элементов распространился на всю ширину страницы, они не должны быть ограничены div-контейнером pageWrapper.
Поэтому сначала нужно удалить этот стиль.
1. Удалите в файле styles.css недавно созданный стиль .pageWrapper.
Контейнер pageWrapper в HTML-коде можно оставить. Этот дополнительный
HTML-код не станет обузой и может понадобиться вам позже для применения
других стилей.
Страница вернется к своему полностью резиновому дизайну. Теперь нужно ограничить только навигационную панель, текст баннера, текст нижнего колонтитула
и основной контент, чтобы они не превышали по ширине 1200 пикселов. Для этого нужно немного углубиться в HTML-код и посмотреть, с какими элементами
следует поработать.
Взгляните на HTML-код файла index.html и найдите элемент nav. Внутри этого
элемента вы увидите кнопки навигации, созданные с помощью простого неупорядоченного списка. Именно это нам и нужно. Для списка можно установить
максимальную ширину 1200 пикселов и центрировать его на странице, позволив элементу nav (и его черному фону) распространиться на всю ширину окна
браузера. То же самое касается текста баннера внутри элемента h1. Для него
также можно установить максимальную ширину и поля. В нижнем колонтитуле можно взять под контроль элемент p.
2. Добавьте в файл styles.css следующий код:
nav ul, header h1, footer p {
max-width: 1200px;
margin: 0 auto;
}
Этот групповой селектор нацелен на панель навигации, баннер и нижний
колонтитул, но не на те элементы, в которых они содержатся. Теперь, если
сохранить CSS-файл и просмотреть в браузере страницу index.html, вы увидите что элементы навигации, название и нижний колонтитул не становятся
шире 1200 пикселов. Но основной контент по-прежнему заполняет все пространство окна браузера. Чтобы исправить ситуацию, нужно заключить три
колонки в еще один div-контейнер для создания группы, размером и выравниванием которой можно управлять.
ПРИМЕЧАНИЕ
Другой способ заключается в том, чтобы добавить контейнер div в элемент header и обернуть им
элементы nav и h1, а второй контейнер div вставить в элемент footer. 
Можно не ограничивать ширину элементов header и footer, ограничивая при этом ширину вложенных div-контейнеров.
3. Откройте в редакторе HTML-кода файл index.html. Непосредственно перед
комментарием `<!-- первая боковая панель -->` добавьте код `<div class="contentWrapper">`:
```
<div class="contentWrapper">
<!-- первая боковая панель -->
```
Теперь этот div-контейнер нужно закрыть.
4. Перейдите в конец HTML-файла. Между закрывающим тегом `</aside>` и открывающим тегом `<footer>` добавьте закрывающий тег </div>, чтобы HTML-код
приобрел следующий вид:
```
</aside>
</div>
<footer>
```
И наконец, можно добавить это новое имя класса к стилю, созданному на шаге 2.
5. Добавьте новый класс к групповому селектору в файле styles.css:
nav ul, header h1, footer p, .contentWrapper {
max-width: 1200px;
margin: 0 auto;
}