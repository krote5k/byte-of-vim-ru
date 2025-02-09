# Передвижение

После того, как вы написали исходный текст, редактирование и переписывание требует много движения между различными частями документа. Например, вы пишете историю и вдруг у вас появляется идея для нового сюжета, но для развития этого сюжета вам нужно вернуться к той части, где главный герой входит в новый город (или что-то в этом роде)... как быстро перемещаться по тексту, чтобы не потерять ход своих мыслей?

Давайте рассмотрим несколько примеров того, как сделать это быстро в Vim.

- Хотите переместить курсор на следующее слово? Нажмите `W`.
- Хотите перейти к следующему абзацу? Нажмите `}`.
- Хотите перейти к 3-му вхождению буквы "Н"? Нажмите `3fh`.
- Хотите переместиться на 35 строк вниз? Нажмите `35j`.
- После одного из вышеуказанных движений, хотите вернуться в предыдущее место? Нажмите `ctrl-о`.

Хотите узнать, как это все это работает? Давайте погрузимся.

Для начала, откройте файл под названием `chandrayaan.txt` и введите следующее [текст из Википедии](http://en.wikipedia.org/wiki/Chandrayaan-1):

> Chandrayaan-1 is India's first mission to the moon. Launched by India's national space agency the Indian Space Research Organisation (ISRO). The unmanned lunar exploration mission includes a lunar orbiter and an impactor. The spacecraft was launched by a modified version of the PSLV XL on 22 October 2008 from Satish Dhawan Space Centre, Sriharikota, Andhra Pradesh at 06:23 IST (00:52 UTC). The vehicle was successfully inserted into lunar orbit on 8 November 2008. The Moon Impact Probe was successfully impacted at the lunar south pole at 20:31 hours on 14 November 2008.
> <br>
> The remote sensing satellite had a mass of 1,380 kilograms (3,042 lb) at launch and 675 kilograms (1,488 lb) at lunar orbit and carries high resolution remote sensing equipment for visible, near infrared, and soft and hard X-ray frequencies. Over a two-year period, it is intended to survey the lunar surface to produce a complete map of its chemical characteristics and 3-dimensional topography. The polar regions are of special interest, as they might contain ice. The lunar mission carries five ISRO payloads and six payloads from other international space agencies including NASA, ESA, and the Bulgarian Aerospace Agency, which were carried free of cost.

## Перемещение курсора, путь Vim

Самые основные клавиши, которые вы будете использовать - это клавиши 'hjkl'. Эти 4 клавиши соответствуют клавишам со стрелками влево, вниз, вверх и вправо соответственно. Обратите внимание, что они расположены прямо под вашей правой рукой, когда Ваши руки помещены на домашнем ряду.

Но почему бы не использовать сами клавиши со стрелками? Проблема в том, что они расположены в отдельном месте на клавиатуре, и это требует столько же движений руки, сколько требуется для использования мыши.

Помните, что пальцы правой руки всегда должны быть помещены на клавиши `jkl;` (и большой палец на пробеле). Теперь давайте посмотрим, как использовать эти 4 клавиши:

![](img/hjkl.png)

| Клавиша | Mnemonic |
|:-------:| ---      |
| `h`     | Вы должны вытянуть указательный палец (который находится на "j") влево, чтобы нажать "h". Это самая левая клавиша и означает движение влево.|
| `j`     | Понижающая клавиша 'j' означает вниз.     |
| `k`     | Повышающая клавиша 'k' означает вверх.    |
| `l`     | Самая правая клавиша 'l' означает вправо. |

Обратите внимание, что мы можем повторить операцию, добавив префикс счетчика. Например, `2j` повторит операцию `j` 2 раза.

Откройте текстовый документ `chandrayaan.txt` и начните практиковать эти клавиши:

1. Поместите курсор на первую букву 'c' в документе.
2. Нажмите `2j` , и должна пропуститься текущая длинная строка, пустая строка и мы перейдем ко второй строке, т.е. второму абзацу.
3. Нажмите `2k`, чтобы вернуться туда, где мы были. Или, как вариант, нажмите `ctrl-o`, чтобы вернуться назад.
4. Нажмите `5l`, чтобы переместиться на 5 символов вправо.
5. Нажмите `5h`, чтобы переместить влево на 5 символов. Или, как вариант, нажмите `ctrl-o`, чтобы вернуться назад.

Сделайте привычкой использование клавиш 'hjkl' вместо клавиш со стрелками. Через несколько попыток вы заметите, насколько быстрее вы используете эти клавиши.

Точно так же существуют более простые клавиши, которые заменяют следующие специальные движения. Обратите внимание, что они снова предназначены для уменьшения движения рук. В этой конкретной задаче случае люди склонны искать и охотиться за этими специальными клавишами, поэтому мы можем полностью избежать этого.

| Традиционные | Vim |
| ---          | --- |
| клавиша 'home' перемещает в начало строки  | клавиша `^` (думайте 'якорь начала') |
| клавиша 'end' перемещает в конец строки    | клавиша `$` (думайте 'доллар останавливает здесь') |
| клавиша 'pgup' перемещает на страницу выше | `ctrl-b` означает перемещение на один экран 'b'ackward (назад) |
| клавиша 'pgdn' перемещает на страницу ниже | `ctrl-f` означает перемещение на один экран 'f'orward (вперед) |

Если вы знаете абсолютный номер строки, к которой хотите перейти, скажем, 50 строка, нажмите `50G`, и Vim перейдет к 50-й строке. Если номер не указан, то `G` приведет вас к последней строке файла. Как добраться до верха файла? Просто нажмите `1G`. Обратите внимание, как один ключ может сделать так много.

- Переместите курсор на первую строку, нажав `1G`.
- Переместите на 20 символов вправо, нажав `20l`.
- Вернитесь к первому символу, нажав `^`.
- Перейдите к последнему символу, нажав `$`.
- Нажмите `G`, для перехода к последней строке.

Что делать, если вы в середине текста, который в настоящее время отображается в окне?

- Нажмите `H`, чтобы прыгнуть как можно выше (первая строка окна)
- Нажмите `M`, для перехода к 'm'iddle (середине) окна
- Нажмите `L`, чтобы перейти как можно ниже (отобразится последняя строка)

Вы, должно быть, начали замечать акцент на слепом вводе и не должны перемещать руки от основной области. Это хорошо.

## Слова, предложения, абзацы

Мы видели, как перемещаться по символам и строкам. Но мы склонны думать о нашем тексте как о словах и как мы складываем их вместе - в предложения, абзацы, главы и так далее. Итак, почему бы не перемещаться по таким текстовым частям, т.е. "текстовым объектам"?

Давайте возьмем первые несколько слов из нашего примера:

> The polar regions are of special interest, as they might contain ice.

Для начала давайте расположим курсор на первом символе, нажав `^`.

> [T]he polar regions are of special interest, as they might contain ice.

<!-- -->

> ПРИМЕЧАНИЕ: Мы используем скобки для обозначения позиции курсора.

Хотите перейти к следующему слову? Нажать `w` (от англ. word - слово). Курсор теперь должен быть на 'p' в 'polar'.

> The [p]olar regions are of special interest, as they might contain ice.

Как насчет перемещения на 2 слова вперед? Просто добавьте количество префиксов в 'w': `2w`.

> The polar regions [a]re of special interest, as they might contain ice.

Аналогично, чтобы перейти к концу следующего слова, нажмите клавишу `e` (end - конец).

> The polar regions ar[e] of special interest, as they might contain ice.

Чтобы переместить одно слово 'b'ackward (назад) - нажмите `b`. Путем префикса счетчика, `2b` мы вернемся на 2 слова.

> The polar [r]egions are of special interest, as they might contain ice.

Смотрите `:help word-motions` для более подробной информации.

Мы видели передвижения по символам и словам, давайте перейдем к предложениям.

> [C]handrayaan-1 is India's first mission to the moon. Launched by India's national space agency the Indian Space Research Organisation (ISRO). The unmanned lunar exploration mission includes a lunar orbiter and an impactor. The spacecraft was launched by a modified version of the PSLV XL on 22 October 2008 from Satish Dhawan Space Centre, Sriharikota, Andhra Pradesh at 06:23 IST (00:52 UTC). The vehicle was successfully inserted into lunar orbit on 8 November 2008. The Moon Impact Probe was successfully impacted at the lunar south pole at 20:31 hours on 14 November 2008.

Поместите курсор на первый символ, используя `^`.

Для перехода к следующему предложению нажмите `)`.

> Chandrayaan-1 is India's first mission to the moon. [L]aunched by India's national space agency the Indian Space Research Organisation (ISRO). The unmanned lunar exploration mission includes a lunar orbiter and an impactor. The spacecraft was launched by a modified version of the PSLV XL on 22 October 2008 from Satish Dhawan Space Centre, Sriharikota, Andhra Pradesh at 06:23 IST (00:52 UTC). The vehicle was successfully inserted into lunar orbit on 8 November 2008. The Moon Impact Probe was successfully impacted at the lunar south pole at 20:31 hours on 14 November 2008.

Разве это не круто?

Для перехода к предыдущему предложению, нажмите кнопку `(`.

Вперед, попробуйте и посмотрите как быстро вы можете двигаться. Опять же, вы можете использовать префикс отсчета, например, `3)`, чтобы продвинуться вперед на 3 предложения.

Теперь используйте весь текст и попробуйте перемещаться по абзацам. Нажмите `}` для перехода к следующему абзацу и `{` - к предыдущему.

Обратите внимание, что "большие" скобки предназначены для большего текстового объекта. Если вы уже заметили это, то поздравляю, вы уже начали думать как виннер, эммм, "думать как Виммер".

Опять же, не пытайтесь *запомнить* эти клавиши, попробуйте сделать их *привычкой* настолько, чтобы ваши пальцы естественно использовали эти клавиши.

Смотрите `:help cursor-motions` для более подробной информации.

## Make your mark

Вы пишете какой-то текст, но внезапно вспоминаете, что нужно обновить связанный раздел в этом же документе, но вы не хотите потерять место, где находитесь в данный момент, чтобы вернуться сюда позже. Что Вы сделаете?

Обычно это означает прокрутку до того раздела, обновление его, а затем прокрутку обратно туда, где вы были. Это много накладных расходов, и мы имеем тенденцию забывать, где были в последний раз.

Мы можем делать вещи немного умнее в Vim. Переместите курсор на 5-ю строку в следующем тексте (слова Джона Леннона). Используйте `ma`, чтобы создать отметку по имени `а`". Переместите курсор в нужное место, например `4j`.


> I am eagerly awaiting my next disappointment. -- Ashleigh Brilliant <br>
> Every man’s memory is his private literature. -- Aldous Huxley <br>
> Life is what happens to you while you’re busy making other plans. -- John Lennon <br>
> Life is really simple, but we insist on making it complicated. -- Confucius <br>
> Do not dwell in the past, do not dream of the future, concentrate the mind on the present moment. -- Buddha <br>
> The more decisions that you are forced to make alone, the more you are aware of your freedom to choose. -- Thornton Wilder

Нажмите `'a` (т. е. одинарную кавычку, за которой следует название метки) и вуаля, Vim прыгает (назад) к строке, где была расположена эта метка.

Вы можете использовать любую букву (a-zA-Z) для обозначения метки, тоесть вы можете иметь до 52 именованных меток для каждого файла.

## Jump around

В различных движениях, которые мы изучили, нам может понадобиться вернуться к предыдущему местоположению или к следующему после перемещения. Чтобы сделать это, просто нажмите `ctrl-o`, чтобы перейти на предыдущую локацию и `ctrl-i`, чтобы прыгать вперед снова в следующие места.

## Части текста {#text-objects}

Существуют различные способы указания текстовых объектов в Vim, чтобы передать их команде. Например, вы хотите визуально выделить часть текста, а затем преобразовать регистр (из верхнего в нижний или из нижнего в верхний) текста с помощью клавиши `~`.

Откройте файл `dapping.txt` который мы создали в предыдущих главах. Используйте различные клавиши для перехода к первой букве слова 'dapper' во втором абзаце. Подсказка: используйте `}`, `j`, `w`.

> Dapping means being determined about being determined and being passionate about being passionate. <br>
> Be a dapper.

Нажмите `v` для запуска визуального режима и затем `ap` для выбора 'p'aragraph (абзаца) 'a'. Нажмите `~` для изменения регистра текста. Если захотите отменить изменения, то просто нажмите `<Esc>`.

> Dapping means being determined about being determined and being passionate about being passionate. <br>
> bE A DAPPER.

Другие мнемоники текстовых объектов - это 'aw', что означает 'w'ord (слово) 'a', `a"` означает строку в кавычках (например "это строка в кавычках"), `ab` - 'b'lock 'a' что означает что-либо в пределах пары скобок и т.д.
Other text object mnemonics are `aw` which means 'a' 'w'ord, `a"` means a quoted string (like "this is a quoted string"), `ab` means 'a' 'b'lock which means anything within a pair of parentheses, and so on.

Смотрите `:help object-motions` и `:help text-objects` для более подробной информации.

## Резюме

Мы увидели богатое количество методов, которые Vim предоставляет нам для перемещения по тексту. Не нужно запоминать каждое из этих движений, гораздо важнее сделать их привычкой, особенно те, которые наиболее важны для вас, и когда они станут для вас привычкой, то уменьшат движения ваших рук, вы станете быстрее и в конечном итоге будете тратить больше времени на размышления о своем письме, а не на программное обеспечение, которое используете для написания.

Смотрите `:help various-motions`, а также `:help motion` о более интересных методах передвижения.
