Изложение в порядке важности

## Главное - сбор, хранение и анализ состояний и анализ поведения

**[SQL](https://en.wikipedia.org/wiki/SQL)** и **[XML](https://en.wikipedia.org/wiki/XML)** [💬](http://www.chernyshov.com/SPPO_6/theory/wt_xml.htm "Описание") по отдельности имеют много разной критики, но по полноте функционала замены им на горизонте пока не наблюдается. Надо внимательно смотреть на преобразование типов данных по цепочке `Python <-> SQL <-> XML <-> пространство имен` [XDM](https://en.wikipedia.org/wiki/XQuery_and_XPath_Data_Model), так как те аскетичнее этих и не перекрываются полностью. Можно применять пространства имен посложнее стандартных, а также пользовательские, которые неплохо бы держать на внешнем ресурсе `xmlns:x__="http://www._____ ..."` . Имеют место быть [сложности 💬](https://en.wikipedia.org/wiki/Object%E2%80%93relational_impedance_mismatch "Вступительная часть по освещению данной темы") в в передаче входных данных на вход функции (хранимой процедуры) `Python -> SQL -> XPath & XQuery` в возврате резутата обратно `XPath & XQuery -> SQL -> Python`.

<!-- 
Если ничего не предпринимать дополнительно, то [SQL Server](https://en.wikipedia.org/wiki/Microsoft_SQL_Server) при возрастании нагрузки с клиентов не собирает запросы от прикладного уровня в очередь, а откидывает их в том числе по взаимоблокировке и недогружается.
-->

Для `SQL`-ных полей есть библиотека [SQLAlchemy](https://docs.sqlalchemy.org/en/14/dialects/mssql.html#module-sqlalchemy.dialects.mssql.pyodbc) в режиме [Core](https://docs.sqlalchemy.org/en/20/core) как слой абстракции.

Для `XML`-ных полей есть интересные возможности у библиотек:
 - [lxml](https://lxml.de/apidoc/lxml.isoschematron.html "Статья от разработчиков") [💬](https://pypi.org/project/lxml "Статья на зеркале с библиотекой со ссылками на GitHub"),
 - [xml.dom](https://docs.python.org/3.9/library/xml.dom.minidom.html "DOM") и [xml.etree](https://docs.python.org/3.7/library/xml.etree.elementtree.html "SAX"),
 - [bs4](https://www.crummy.com/software/BeautifulSoup/bs4/doc/), 

которые предполагается использовать для парса сайтов в основном как [DOM](https://en.wikipedia.org/wiki/Document_Object_Model), но все они используют те же типы данных (пространства имен). Есть плагины [Saxon](https://www.saxonica.com/about/about.xml)-а и есть интеграция со [Schematron](https://en.wikipedia.org/wiki/Schematron)-ом.

Для `XML`-ных структур данных применяются:
 - [XSD](https://en.wikipedia.org/wiki/XML_Schema_(W3C)) [💬](https://bdpx.github.io/xml/lab3/xsd.html "Описание") и [Relax NG](https://en.wikipedia.org/wiki/RELAX_NG) (определение входной информации на соответствие),
 - [XLink](https://en.wikipedia.org/wiki/XLink) (привязка ссылок на внешние ресурсы),
 - [XInclude](https://en.wikipedia.org/wiki/XInclude) [💬](https://www.w3.org/TR/xinclude/) (привязка внешних файлов, в том числе других структур данных),
 - [XPointer](https://en.wikipedia.org/wiki/XPointer) (индексация по подветкам и по узлам),
 - [XPath](https://en.wikipedia.org/wiki/XPath) [💬](https://www.w3.org/TR/xpath-functions/#maps-and-arrays) & [XQuery](https://en.wikipedia.org/wiki/XQuery) [💬](http://xmlhack.ru/texts/03/xquery/what.is.xquery.html) [💬](https://documentation.softwareag.com/webmethods/compendiums/v10-5/C_API_Management/index.html#page/api-mgmt-comp%2Fco-portlet_custom_search_write_xquery.html%23) и [EXPath](http://expath.org/) (написание запросов вручную),
 - [XQL](http://www.ibiblio.org/xql/xql-proposal.html) [💬](https://www.w3.org/TandS/QL/QL98/pp/xql.html) (написание запросов частично программно и частично вручную),
 - [XProc](https://en.wikipedia.org/wiki/XProc), [XSpec](https://github.com/expath/xspec/tree/master) и [OPML](https://en.wikipedia.org/wiki/OPML) (выполнение запроса в прикладном слое),
 - [XSLT](https://en.wikipedia.org/wiki/XSLT), [EXSLT](https://en.wikipedia.org/wiki/EXSLT) и [XMark](https://projects.cwi.nl/xmark/index.html) (оформление результата запроса).

Множество разрозненных наработок только на **XML** только для работы с данными недоведены, устарели и стали историей.

[**Объектно-ориентированные базы данных (сокращенно ООБД)**](https://en.wikipedia.org/wiki/Object_database) в виде составных и пользовательских типов данных с неограниченной гибкостью как продолжение темы [**объектно-ориентированного программирования (сокращенно ООП)**](https://en.wikipedia.org/wiki/Object-oriented_programming), начиная со списков и словарей с их срезами, [DataFrame](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.html)-ы как главный козырь [Pandas](https://en.wikipedia.org/wiki/Pandas_(software)) и заканчивая классами с их композицией и наследованием, к которым подводят мысль во многих книгах, пока к сожалению не обрели своих СУБД и используются в университетской среде насколько позволяет оперативная память операционной системы и только в однопользовательском режиме с запросами на [OQL](https://en.wikipedia.org/wiki/Object_Query_Language).

![007 001 001](https://user-images.githubusercontent.com/104857185/209877366-3c1a9309-736c-49ce-9bb3-709e16110020.jpg)

[**не-SQL-ные СУБД**](https://en.wikipedia.org/wiki/NoSQL "Есть мнение в разных источниках, что они быстрее SQL-ных баз") [:thought_balloon:](https://aws.amazon.com/ru/nosql "Статья на Amazon-е"), числу которых сейчас нет счета, по сравнению с **SQL-ными** имеют столько преимуществ сколько и неудобств. Какая-то одна в чем-то лучше и в чем-то хуже какой-то другой. Вообще то говоря это даже не базы данных, а примежуточный гибрид между файловой системой и таблицами баз данных. Большинство из них в разных модификациях являются продолжением темы [JSON](https://en.wikipedia.org/wiki/JSON) + двоичные поля и [BLOB](https://en.wikipedia.org/wiki/Binary_large_object)-ы. Кстати, могли бы сразу взять за основу [YAML](https://en.wikipedia.org/wiki/YAML). Но видимо разработчики - сторонники [JavaScript](https://en.wikipedia.org/wiki/JavaScript)-а. Не заменят XML, так как есть принципиальное отличие:
 - `*.xml` - ветвление, топология, структура,
 - `*.dat, *.ini, *.json, *.yaml` - словарь, конфигурация, настройка.

Есть коммерческие платформы для работы с данными непонятно на чем (коммерческая тайна), например [MarkLogic](https://www.marklogic.com/), но они сами в себе

## Дополнение к главному - средства работы на стороне пользователей

[Tcl](https://www.tcl.tk/about/language.html "Делал некоторые графические оболочки с помощью среды разработки tkBuilder") [💬](https://en.wikipedia.org/wiki/Tcl "Описание") хорошо применялся в конце 1990-х и в начале 2000-х на [ORACLE Solaris](https://en.wikipedia.org/wiki/Oracle_Solaris) для написания скриптов-обработчиков виджетов в пользовательских и системных утилитах с графической оболочкой внутри среды разработки [tkBuilder](https://sourceforge.net/projects/tkbuilder84/) (см. снимок экрана ниже), [Komodo](https://www.activestate.com/products/komodo-ide/) и [GUI Builder](https://spectcl.sourceforge.net/).

![tkBuilder Начало 4](https://user-images.githubusercontent.com/104857185/219376538-1686668f-58e8-41e1-b9ff-a7f55ed34eaf.png)

[Java](https://en.wikipedia.org/wiki/Java_(programming_language) "Начал изучать его вместе с Python-ом и вскоре понял, что Python значительно лучше и полностью перешел на него.") по-тихому уходит в прошлое :chart_with_downwards_trend: Его поддержка на разных уровнях устаревает и засыхает :hourglass_flowing_sand: Проект на нем - как правило вязанка папок с файлами, в том числе `jar`-иками (сразу не сообразишь, где точка входа на исполнение). В основном допиливают и перепиливают наработки начала 2000-х, когда он перехватил инициативу и хорошо вписался в ВЭБ-разработку, а позднее в районе 7-ой версии переехал в мобильную разработку на [Android](https://en.wikipedia.org/wiki/Android_(operating_system)) :iphone:

[R](https://en.wikipedia.org/wiki/R_(programming_language) "Пробовал его для расчетов данных с SQL Server-а") - простенький предметно-ориентированный язык с бедным набором типов данных, рассчитанный на математиков и экономистов. В [Data Science](https://en.wikipedia.org/wiki/Data_science) с разным успехом применяют богатые возможности [DataFrame](https://www.rdocumentation.org/packages/base/versions/3.6.2/topics/data.frame)-ов для импорта моментальных снимков баз данных и анализа их срезов, но перегонять снимок в память - это круто даже для их серверов. Есть особенность - все числовые переменные векторные, поэтому операции над ними работают не по правилам арифметики, а по правилам действий с векторами и матрицами (векторно-скалярные преобразования и обратно). Графических приложений на нем не предвидится. Пока только скрипты, которые можно исполнять на интерпретаторе или внутри среды разработки [R Studio](https://en.wikipedia.org/wiki/RStudio "Еще сырая. Если зависает скрипт или одна вкладка, то виснет все. Если кодировка не ASCII и не win-1251, то лепит краказябру. В кадре терминала черным и красным шрифтом вываливает все, что надо и не надо. При занятости сервера СУБД его драйвер ждет несколько секунд и сбрасывает соединение. Для сравнения драйвер Python-а ждет часами и сутками"). Документации много. Есть много видео. Примеры узкоспециализированные, в основном от частного к общему (как и принято в США), что затрудняет понимание и перенос на другие примеры.

[Python](https://www.python.org/ "Есть мнение, что в математических расчетах он медленнее C++, но не прилагаются замеры. Когда делал прикладные программы на C++, то в журналах были горы ошибок и предупреждений, на Python-е - там пусто. Установленные интерпретаторы и библиотеки по отдельности лучше не обновлять - возможны глюки. Виртуальное окружение (интерпретатор и библиотеки указанных в файле `requirements.txt` версий) во многопользовательской системе - временная вынужденная мера, от которой по возможности надо уходить, потому что пользователям на клиентах дается ярлык (символическая или мягкая ссылка) на скрипт с файлового сервера, ставятся интерпретатор и используемые с ним библиотеки, но раздавать или делать дубликаты виртуального окружения со всеми переделками разработчика всем клиентам как-то не по фэншую") [💬](https://en.wikipedia.org/wiki/Python_(programming_language) "Описание") 🇳🇱 имеет необъятные возможности благодаря богатству типов данных и разработанным под него библиотекам, теперь надежно доминирует :chart_with_upwards_trend: :bar_chart: Очень много написано про его хорошие стороны. Дополнительно ко всему сказанному и написанному хочу отметить, что скрипты на нем меньше лезут в операционную систему как **C++** и больше работает в профиле пользователя.

[Mojo](https://en.wikipedia.org/wiki/Mojo_(programming_language)) [💬](https://docs.modular.com/mojo/programming-manual.html) [💬](https://www.kdnuggets.com/2023/05/mojo-lang-new-programming-language.html) [💬](https://habr.com/ru/articles/733896/) обещает повышенное быстродействие и упрощенное развертывание. Значимых наработок на нем пока нет.

## Применяемые библиотеки, [FrameWork](https://en.wikipedia.org/wiki/Software_framework)-и и среды разработки:

[tk, ttk и ttk+](https://en.wikipedia.org/wiki/Tk_(software)) используется на [twm](https://en.wikipedia.org/wiki/Twm) [💬](https://gitlab.freedesktop.org/xorg/app/twm "Исходники") в виде комплектной библиотеки [tkinter](https://en.wikipedia.org/wiki/Tkinter) с ограниченными по нынешним временам возможностями для творчества, которая содержит встроенный интерпретатор `tcl`, а также `ttk` (`tk` с темами, как и обещали на `Tcl 8.5`, с помощью [tk-builder](https://pypi.org/project/tk-builder) 🗯️).

[pySimpleGUI](https://www.pysimplegui.org/en/latest/) прост, интересен, имеет наборы стилей, внешне напоминает ВЭБ-разработку, но на нем мало примеров. 

[Gtk и Gtk+](https://en.wikipedia.org/wiki/GTK "В настоящее время имеют ошибки") используются в `Linux`-е в оконном мэнэджере [Gnome](https://en.wikipedia.org/wiki/GNOME). Библиотека [pyGTK](https://en.wikipedia.org/wiki/PyGTK) закрыта в 2011-м, на `Windows` пока не ставится, переехала на [pyGObject](https://pygobject.readthedocs.io/en/latest/) и начиная с версии 3 `GTK+` имеет ошибки. Есть открытые и коммерческие дизайнеры, в том числе [GTK Builder](https://docs.gtk.org/gtk3/class.Builder.html).

[wxPython](https://en.wikipedia.org/wiki/WxPython) неправильно отображает кодировки и не пропорцинально отображает виждеты в разных сочетаниях

[pyQt](https://en.wikipedia.org/wiki/Qt_(software)) позволяет вставлять не только комплектные виджеты, но также виджеты и графику из других фрэймворков. Есть комплектный [QtDesigner](https://doc.qt.io/qt-6/qtdesigner-manual.html) для рисования макетов и записи их отдельным ресурсным файлом :floppy_disk: для вставки их в проект внутри среды разработки [pyCharm](https://en.wikipedia.org/wiki/PyCharm) :netherlands: , которая просто идеальна :books:

## Прикладное ПО для работы на первичной и вторичной аппаратуре

Различные диалекты [ассемблера](https://en.wikipedia.org/wiki/Assembly_language#Assembler), адаптированнные фирмами-изготовителями первичной аппаратуры для:
 - конфигурирования,
 - программирования,
 - каскадного обновления прошивок,
 - заливки файлов соответствия `код события - строка сообщения о событии`,
 - импорта топологии,
 - экспорта собранной информации как правило файлами типа <span color:Green>`*.xml`</span> в серверную компоненту [SCADA-системы](https://en.wikipedia.org/wiki/SCADA).

![IMG_5250](https://user-images.githubusercontent.com/104857185/215399246-d87eb515-82ea-4dd5-977b-c039426b1d20.JPG)

![Правый стенд на Cerberus Pro](https://user-images.githubusercontent.com/104857185/215399494-165b2e5d-c15b-4a3d-9199-4c0c2f7185e5.JPG)

[C++](https://isocpp.org/ "Перешел на него после Fortran-а в 1993-м году") [💬](https://en.wikipedia.org/wiki/C%2B%2B "Описание") еще в ходу и в настоящее время в основном используется для написания операционных систем, драйверов, игрушек и прочего коммерческого программного обеспечения и в источниках уже не упоминается как язык высокого уровня.
