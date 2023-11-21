## Общие указания

<!--
[Объемы выполняемых работ](https://github.com/tsv19su254052/tsv19su254052/blob/main/Works.md)

[Способы и средства разработки](https://github.com/tsv19su254052/tsv19su254052/blob/main/Languages.md)
-->

Проекты индувидуальной разработки на репозиториях здесь и в организациях, разработанные в том числе по подсказкам со [StackOverFlow](https://stackoverflow.com/users/15883118/tarasov-sergey "Помогает ориентироваться в огромном разнообразии библиотек и их методов на основе опыта их применения другими опытными разработчиками") и с [ChatGPT](https://openai.com/product/gpt-4 "Ищет ответы на короткие вопросы")  частично отслеживаются на `GitHub`-е по мере надобности в объеме, необходимом для удобства сведения и внесения изменений. Полностью функциональны внутри инфраструктуры, так как подключаются к серверу СУБД и что-то тянут с ссылочных файлов. Могут запускаться на исполнение на [клиентах](https://en.wikipedia.org/wiki/Client%E2%80%93server_model) следующими способами:
 - Внутри локальной сети по [ярлыку](https://sysadminwiki.ru/wiki/%D0%9C%D1%8F%D0%B3%D0%BA%D0%B8%D0%B5_%D0%B8_%D0%B6%D1%91%D1%81%D1%82%D0%BA%D0%B8%D0%B5_%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8) , который указывает на исходник (точку входа) в подключенной [сетевой папке](https://ru.wikipedia.org/wiki/File_%28%D1%81%D1%85%D0%B5%D0%BC%D0%B0_URI%29) с файлового сервера. Интерпретатор и библиотеки устанавливаются на каждом клиенте дополнительно, из-за чего возможны глюки и косяки из-за разных версий и подверсий интерпретатора и библиотек.
 - Внутри локальной сети или из внешней сети по [RDP](https://ru.wikipedia.org/wiki/Remote_Desktop_Protocol) в [терминальном сервере](https://ru.wikipedia.org/wiki/%D0%A2%D0%B5%D1%80%D0%BC%D0%B8%D0%BD%D0%B0%D0%BB%D1%8C%D0%BD%D1%8B%D0%B9_%D1%81%D0%B5%D1%80%D0%B2%D0%B5%D1%80). Один набор интерпретаторов и их библиотек для всех пользователей.
 - Внутри локальной сети или из внешней сети по [ВЭБ-мордочке](https://en.wikipedia.org/wiki/Website "Версия для компьютера и мобильная версия"). Предпологается совместая работа например на [coda.io](https://coda.io/workspaces/ws-ga7Eabm46u/folders/fl-7OkuhzSo66?source=doc-title-bar) с пре-`Commit`-ами [Terraform](https://en.wikipedia.org/wiki/Terraform_(software)) на инфраструктуре облака. Вот неплохое [видео](https://www.youtube.com/watch?v=JC_OyWpqNSA) с примером на [Selectel](https://en.wikipedia.org/wiki/Selectel). После ~~вождения за нос в трех соснах~~ знакомства с [Kubernetes](https://en.wikipedia.org/wiki/Kubernetes), `Node`-ами на [Docker](https://en.wikipedia.org/wiki/Docker_(software))-е с каким-нибудь минималистичным `Linux`-ом, `POD`-ами (рисуем проект, пишем конфиги и манифесты на `yaml`-иках и все полностью закидываем туда), а затем с [VPS и VDS](https://www.reg.ru/vps/). И в итоге провайдер таки предложит как вершину их сервиса свои отдельные серверы с нормальной операционной системой типа `Windows Server` и прикладным ПО под нее, а еще лучше перевезти наши серверы к нему, подключить их в его подсетку и за-`deploy`-ить (но мы этого пока не делаем). Так же один набор интерпретаторов и их библиотек для всех пользователей.
 - Из внешней сети в [мобильном приложении](https://en.wikipedia.org/wiki/Mobile_app) :iphone:. 

Оригиналы стволовой и оперативных веток проектов хранятся на файловом сервере.

Функция `GitHub`-а на репозитории ограничена возможностью:
 - [x] выбрать текущую стволовую ветку (принято называть ее `Developing_v...`, ветки `main` и `master` как правило для технического архива),
 - [x] почитать текстовые и графические пояснения к проекту,
 - [x] ознакомиться с математическим обеспечением,
 - [x] посмотреть исходники,
 - [x] почитать в обсуждениях объемы доработок,
 - [x] предложить правку с помощью `Pull Request`-а, предварительно уточнив ветку для внесения правок,
 - [ ] склонировать исходники себе или ответвить их у себя (непрактично, так как клон или ветка со временем устареет или разойдется с оригиналом и будет конфликт слияния).

Суммируя обращения к документации по `GitHub`-у и учитывая некоторый практический опыт работы с ним, дополнительно отмечу некоторые моменты:
 - Перетасовывать папки и файлы внутри проекта ([Git](https://en.wikipedia.org/wiki/Git) и [SVN](https://en.wikipedia.org/wiki/Apache_Subversion) это допускают в отличие от [CVS](https://en.wikipedia.org/wiki/Concurrent_Versions_System)) нежелательно. При обновлении кое-что может улететь с репозитория и из проекта, поэтому надо проверить их наличие и привязку на `Git`-е перед обновлением.
 - При [добавлении участника](https://stackoverflow.com/questions/7920320/adding-a-collaborator-to-my-free-github-account) его активность на `GitHub`-е (если она ему так важна и нужна) <span style="color:red;"> не видна ни у него, ни у остальных </span>.
 - При подготовке изменений желательно делать [Commit](https://en.wikipedia.org/wiki/Commit_(version_control))-ы на определенных стадиях готовности, чтобы не было сложностей со сведением изменений. В итоге предложить [Pull Request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request) на заранее оговоренной оперативной ветке. Пока изменение принимают и вносят, новые изменения там же не делать.
 - На репозиториях оригиналов подмодулей значек <span style="color:Green">"Used by ..."</span> пока не появляется с включенным графом зависимостей или без него (см. [статью](https://stackoverflow.com/questions/56888176/how-to-configure-github-used-by-feature-for-java-projects)).
 - Синхронизировать подмодули на репозитории и его клонах средствами `GitHub`-а не получится (там только неактивные ссылки), потому что они асинхронно импортированы внутри среды разработки в проект как дубликаты (импортируются и синхронизируются с их оригиналами в окошке терминала командами `git submodules ...`) и соответственно не отслеживаются на `Git`-е (не дублируются дважды) для экономии места на репозитории. Свои подмодули не импортирую (они у меня есть).
 - При смене или переименовании недоменной учетки или при смене локального пароля на `Windows`, а также смене учетки на `Google` плагин `Git`-а в `pyCharm`-е не синхронизирует проект с `GitHub`-ом и не видит историю изменений. Пишет, что срабатывает второй и третий фактор проверки владения репозиторием (см. прилагаемый снимок экрана ниже) и придется переезжать на новую учетку на `GitHub`-е. Выход из ситуации - команда `git config --global --add safe.directory ...` , но она не всегда срабатывает или срабатывает на один сеанс работы с проектом. Эта активность на GitHub-е не видна.

![pyCharm - Ошибка синхронизации с GitHub-ом (другая учетка)](https://user-images.githubusercontent.com/104857185/216789558-ea500396-740e-4977-a426-22d01753f799.png)

![pyCharm - git submodule add](https://github.com/tsv19su254052/tsv19su254052/assets/104857185/239cc5e3-8c76-4c03-8629-acb14e9fef99)

<!--
```diff
+ this text is highlighted in green
- this text is highlighted in red
```

```json
   // Code for coloring
```
```html
   // Code for coloring
```
```js
   // Code for coloring
```
```css
   // Code for coloring
```
-->

Текущая версия `pyCharm` пока не гармонирует со своим плагином для интеграции с [TortoiseGIT](https://en.wikipedia.org/wiki/TortoiseGit)

![TortoiseGit Plugin for pyCharm Установка с диска](https://github.com/tsv19su254052/tsv19su254052/assets/104857185/bf1d5fb9-0a03-4da8-a15b-b7477875ea55)

## Объемы работ (эскизы, прототипы, архитектурные решения)

по [**прикладному программированию**](https://en.wikipedia.org/wiki/Application_software) для [централизованных](https://en.wikipedia.org/wiki/Centralized_computing) и [распределенных](https://en.wikipedia.org/wiki/Distributed_computing) вычислений на [серверах](https://en.wikipedia.org/wiki/Windows_Server "Windows Server - на сегодняшний момент из имеющихся в наличии самая лучшая ОС. По-моему уже хватит мучить Linux-ы и тем более BSD . Прикладные пакеты на Linux (Debian-ы и RedHat-совместимые) делают индийские и бразильские студенты. Аппаратные сбои в электронике Linux просто не видит или не определяется их источники. Согласно сплетням еще в 2007-м году разработчики из NetBSD и из OpenBSD перебежали в M$ и в Google"), а также для [децентрализованных](https://en.wikipedia.org/wiki/Decentralized_computing) вычислений на [клиентах](https://en.wikipedia.org/wiki/Microsoft_Windows "Они как бы больше заточены под офисное прикладное программное обеспечение, поэтому для них в основном предусматриваются графические оболочки и вход через ВЭБ-мордочки"):

Разработка склоняется к циклу [SDLC](https://en.wikipedia.org/wiki/Systems_development_life_cycle). Для удобства [внесения изменений](https://en.wikipedia.org/wiki/CI/CD) по мере надобности и в зависимости от раскладки приоритетов оставляем все на стадии рабочего эволюционного и инкрементного прототипа (аналог фазы 2 в [Среде разработки требований (REE)](https://en.wikipedia.org/wiki/Software_prototyping) от [Римской лаборатории](https://en.wikipedia.org/wiki/Rome_Laboratory)) согласно методе "Эволюционной быстрой разработки (ERD)" от [DARPA](https://en.wikipedia.org/wiki/DARPA) (см. [русскоязычную адаптацию](http://sewiki.ru/Systems_Engineering_Thinking_Wiki:%D0%9E%D0%BF%D0%B8%D1%81%D0%B0%D0%BD%D0%B8%D0%B5) с легким уклоном в [гностику](https://en.wikipedia.org/wiki/Gnosticism)).

В [3-х слойной архитектуре](https://en.wikipedia.org/wiki/Multitier_architecture#Three-tier_architecture) сбоку от второго слоя я бы добавил
слой ввода-вывода от первичной и вторичной аппаратуры как **второй дополнительный слой**, так как через людей на офисах ходит только часть данных.

## Первый слой - моделирование данных по состоянию и поведению

Базы данных в проектах - наиболее трудоемкая часть разработки. Делаются, администрируются, правятся, хранятся, бэкапятся на сервере СУБД и привязаны к его системным настройкам. `GitHub` на такое не заточен, соответственно эта работа на нем не отслеживается.

**[SQL](https://en.wikipedia.org/wiki/SQL)** и **[XML](https://en.wikipedia.org/wiki/XML)** [💬](http://www.chernyshov.com/SPPO_6/theory/wt_xml.htm "Описание") по отдельности имеют много разной критики, но по полноте функционала замены им на горизонте пока не наблюдается.

[**не-SQL-ные СУБД**](https://en.wikipedia.org/wiki/NoSQL "Есть мнение в разных источниках, что они быстрее SQL-ных баз"), числу которых сейчас нет счета, по сравнению с **SQL-ными** имеют столько преимуществ сколько и неудобств. Какая-то одна в чем-то лучше и в чем-то хуже какой-то другой. Вообще то говоря это даже не базы данных, а некая шапка из вложенных одна в другую хэш-таблиц как правило в формате [JSON](https://en.wikipedia.org/wiki/JSON) со ссылками на разнотипные записи в том числе двоичные поля и [BLOB](https://en.wikipedia.org/wiki/Binary_large_object)-ы где-то в файловой системе. Видимо в сознании разработчиков преобладали старые догмы, принесенные из предыдущих работ. Запросы на прикладном уровне писать сложно, потому что на момент написания запроса не известна структура данных.

И кстати опять же не заменят XML, так как `*.dat, *.ini, *.json, *.yaml` - словарь, конфигурация, настройка, а `*.xml` - ветвление, топология, структура.

[**Объектно-ориентированные базы данных (сокращенно ООБД)**](https://en.wikipedia.org/wiki/Object_database) в виде составных и пользовательских типов данных с неограниченной гибкостью - списки, словари, [DataFrame](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.html)-ы как главный козырь [Pandas](https://en.wikipedia.org/wiki/Pandas_(software)), их срезы, классы с их композицией и наследованием, к которым подводят мысль во многих книгах как продолжение темы [**объектно-ориентированного программирования (сокращенно ООП)**](https://en.wikipedia.org/wiki/Object-oriented_programming). Было много духовных исканий, чтобы выделить память данных от прикладного ПО в отдельные полноценные ООСУБД с 1980-х годов. Перебирали разные языки программирования, изобретали новые языки запросов и перемычки между ними. Но не хватило идейного наполнения. Используются в университетской среде насколько позволяет оперативная память операционной системы в основном в однопользовательском режиме, так как с транзакциями и отказоустойчивостью у них не очень. Само собой работать с ними может только их разработчик.

Есть коммерческие платформы для работы с данными непонятно на чем, например [MarkLogic](https://www.marklogic.com/), но они сами в себе

## Второй слой - логика, расчеты, математическое моделирование, анализ, нейросетки (машинное обучение), искусственный интеллект

Если нужно что-то для нечастого использования вручную с ключами, с путями и с последовательным вводом-выводом или для вторичных вызовов как функция, [API](https://en.wikipedia.org/wiki/API)-шка или [хранимая процедура](https://en.wikipedia.org/wiki/Stored_procedure) для работы с базами и структурами данных, то пишем [скрипт](https://timeweb.com/ru/community/articles/chto-takoe-skript):
 - на `SQL` с помощью среды разработки [SQL Server Management Studio](https://en.wikipedia.org/wiki/SQL_Server_Management_Studio),
 - на `XPath & XQuery`с помощью среды управления [BaseX](https://en.wikipedia.org/wiki/BaseX) [💬](https://docs.basex.org/wiki/XQuery_Update "Статья на сайте разработчиков"), [Oxygen XML](https://en.wikipedia.org/wiki/Oxygen_XML_Editor) [💬](https://www.oxygenxml.com/doc/versions/25.0/ug-editor/topics/preferences-xslt-saxon8.html) или [Raptor XML](https://www.altova.com/raptorxml),
 - на `SQL` со вставками на `XPath & XQuery`,
 - на `Python`-е с помощью среды разработки [pyCharm](https://en.wikipedia.org/wiki/PyCharm),
 - то же с уже проверенными вставками на `SQL` + `XPath & XQuery`.

Если ничего не предпринимать дополнительно, то [SQL Server](https://en.wikipedia.org/wiki/Microsoft_SQL_Server) при возрастании нагрузки с клиентов не собирает запросы от прикладного уровня в очередь, а откидывает их в том числе по взаимоблокировке и недогружается.

Для `SQL`-ных полей есть библиотека [SQLAlchemy](https://docs.sqlalchemy.org/en/14/dialects/mssql.html#module-sqlalchemy.dialects.mssql.pyodbc) в режиме [Core](https://docs.sqlalchemy.org/en/20/core) как слой абстракции.

Для `XML`-ных полей есть интересные возможности у библиотек:
 - [lxml](https://lxml.de/apidoc/lxml.isoschematron.html "Статья от разработчиков") [💬](https://pypi.org/project/lxml "Статья на зеркале с библиотекой со ссылками на GitHub"),
 - [xml.dom](https://docs.python.org/3.9/library/xml.dom.minidom.html "DOM") и [xml.etree](https://docs.python.org/3.7/library/xml.etree.elementtree.html "SAX"),
 - [bs4](https://www.crummy.com/software/BeautifulSoup/bs4/doc/), 

которые предполагается использовать для парса сайтов в основном как [DOM](https://en.wikipedia.org/wiki/Document_Object_Model), но все они используют те же типы данных (пространства имен).

Для `XML`-ных структур данных применяются:
 - [XSD](https://en.wikipedia.org/wiki/XML_Schema_(W3C)) [💬](https://bdpx.github.io/xml/lab3/xsd.html "Описание") и [Relax NG](https://en.wikipedia.org/wiki/RELAX_NG) (определение входной информации на соответствие),
 - [XLink](https://en.wikipedia.org/wiki/XLink) (привязка ссылок на внешние ресурсы),
 - [XInclude](https://en.wikipedia.org/wiki/XInclude) [💬](https://www.w3.org/TR/xinclude/) (привязка внешних файлов, в том числе других структур данных),
 - [XPointer](https://en.wikipedia.org/wiki/XPointer) (индексация по подветкам и по узлам),
 - [XPath](https://en.wikipedia.org/wiki/XPath) [💬](https://www.w3.org/TR/xpath-functions/#maps-and-arrays) & [XQuery](https://en.wikipedia.org/wiki/XQuery) [💬](http://xmlhack.ru/texts/03/xquery/what.is.xquery.html) [💬](https://documentation.softwareag.com/webmethods/compendiums/v10-5/C_API_Management/index.html#page/api-mgmt-comp%2Fco-portlet_custom_search_write_xquery.html%23) и [EXPath](http://expath.org/) (написание запросов вручную),
 - [XQL](http://www.ibiblio.org/xql/xql-proposal.html) [💬](https://www.w3.org/TandS/QL/QL98/pp/xql.html) (написание запросов частично программно и частично вручную),
 - [XProc](https://en.wikipedia.org/wiki/XProc), [XSpec](https://github.com/expath/xspec/tree/master) и [OPML](https://en.wikipedia.org/wiki/OPML) (выполнение запроса в прикладном слое),
 - [XSLT](https://en.wikipedia.org/wiki/XSLT), [EXSLT](https://en.wikipedia.org/wiki/EXSLT) и [XMark](https://projects.cwi.nl/xmark/index.html) (оформление результата запроса).

 Есть [тонкости 💬](https://en.wikipedia.org/wiki/Object%E2%80%93relational_impedance_mismatch "Вступительная часть по освещению данной темы") в передаче входных данных на вход функции (хранимой процедуры) и в возврате результата из нее обратно. Надо внимательно смотреть на преобразование типов данных в пространствах имен по цепочке `Python <-> SQL <-> XML <-> XPath & XQuery` [XDM](https://en.wikipedia.org/wiki/XQuery_and_XPath_Data_Model), так как те аскетичнее этих и не перекрываются полностью. Можно применить пользовательские пространства имен посложнее, которые неплохо бы держать где-нибудь на внешнем ресурсе `xmlns:x__="http://www._____ ..."` .

 [Saxon](https://www.saxonica.com/about/about.xml) и [Schematron](https://en.wikipedia.org/wiki/Schematron) сейчас из самостоятельного прикладного ПО перешли в плагины для сред разработки.

Множество разрозненных наработок только на **XML** только для работы с данными недоведены, устарели и стали историей.

![007 001 001](https://user-images.githubusercontent.com/104857185/209877366-3c1a9309-736c-49ce-9bb3-709e16110020.jpg)

С развитием и распространением персональной вычислительной техники в начале 1990-х годов многие [эмпирические методы](https://en.wikipedia.org/wiki/Empirical_research) в прикладной математике с [номограммами](https://en.wikipedia.org/wiki/Nomogram) получили свое практическое подтверждение путем расчета аналитических формул напрямую, используя [конечно-разностные формы](https://ru.wikipedia.org/wiki/%D0%A0%D0%B0%D0%B7%D0%BD%D0%BE%D1%81%D1%82%D0%BD%D0%B0%D1%8F_%D1%81%D1%85%D0%B5%D0%BC%D0%B0) их записи в определенных пределах интегрирования или дифференцирования. Для удобства восприятия решение как правило стремились получить в виде экстремума градиента на поверхности или на облаке точек, подбирая диапазоны итерации и шаги приращения вручную или более осторожно методом последовательного приближения. Посчитали различные задачи оптимизации, которые ждали своего решения еще с 1960-х годов.

![лекции по МОСУ у Кудряшева](https://github.com/tsv19su254052/tsv19su254052/assets/104857185/a5459d73-51ee-471a-8e2f-7a01471c1d2a)

## Второй дополнительный слой - ввод-вывод с аппаратуры АСУТП

Различные диалекты [ассемблера](https://en.wikipedia.org/wiki/Assembly_language#Assembler) и [C++](https://en.wikipedia.org/wiki/C%2B%2B "Еще в ходу и в настоящее время в основном используется для написания операционных систем, драйверов, игрушек и прочего коммерческого программного обеспечения и в источниках уже не упоминается как язык высокого уровня"), адаптированнные фирмами-изготовителями первичной аппаратуры для:
 - конфигурирования,
 - программирования,
 - каскадного обновления прошивок,
 - заливки файлов соответствия `код события -> строка сообщения о событии`,
 - импорта топологии,
 - экспорта собранной информации как правило файлами типа <span color:Green>`*.xml`</span> в серверную компоненту [SCADA-системы](https://en.wikipedia.org/wiki/SCADA).

![IMG_5250](https://user-images.githubusercontent.com/104857185/215399246-d87eb515-82ea-4dd5-977b-c039426b1d20.JPG)

![Правый стенд на Cerberus Pro](https://user-images.githubusercontent.com/104857185/215399494-165b2e5d-c15b-4a3d-9199-4c0c2f7185e5.JPG)

![IMG_3176](https://github.com/tsv19su254052/tsv19su254052/assets/104857185/a2e1bbfb-1f9a-418a-814d-0bce3e07ed11)

[API](https://en.wikipedia.org/wiki/API)-шки в широком понимании модели [Клиент - Сервер](https://en.wikipedia.org/wiki/Client%E2%80%93server_model) в сопряжении с автоматикой смежных систем локально или по сети применяются для облегчения внесения изменений и для обеспечения единообразия в повторном применении исходных текстов <span style="color:green">(функции, интерфейсы, статические и динамические библиотеки)</span> на всех клиентах в обращениях к службам, предоставляемым серверными компонентами в [Сервисном слое](https://en.wikipedia.org/wiki/Service_layer), который сопоставляется с прикладным слоем в [Модели OSI](https://en.wikipedia.org/wiki/OSI_model), а точнее располагается в 3-й уровне абстракции [ее 8-ого надслоя](https://en.wikipedia.org/wiki/Layer_8) в разной степени гибкости [Сервис-ориентированной архитектуры](https://en.wikipedia.org/wiki/Service-oriented_architecture) и который пока относят к стороннему (часто закрытому) программному обеспечению, дописанному дополнительно к общеизвестным прикладным протоколам. Этот слой в полном варианте состоит из пары:
- сервер состояний <span style="color:Orange">(в идеале внешний сервер СУБД)</span>,
- сервер поведения <!-- сообщений о событиях --> <span style="color:Orange">(например [OPC-сервер](https://ru.wikipedia.org/wiki/OPC))</span>

![009 001](https://user-images.githubusercontent.com/104857185/211207093-d0c7b9b9-5594-4dcd-a3e3-b7f81757ff6f.jpg)

Фирмы-изготовители оборудования и программного обеспечения для работы с ним, к которому они **не прилагают**:
 - исчерпывающее описание состояний и событий,
 - свои [DDK](https://ru.wikipedia.org/wiki/DDK) и [SDK](https://en.wikipedia.org/wiki/Software_development_kit),
 - исходные тексты **для написания прикладных API-шек с нуля или поверх комплектных от фирмы-изготовителя**, в эту идею к сожалению **не вписываются**, так как этим **исключают интеграцию с ними прикладных задач** 🤔

<!--
Они закрываются, применяя сертификаты, программные и аппаратные ключи, смарт-лицензии и активацию по сети, а к широкому сообществу обращаются лишь раз от разу при потребности в свежих идеях, которых это сообщество без глубокого вовлечения вероятно дает недостаточно. Они чрезмерно увлеклись переносом функционала на [Облака](https://en.wikipedia.org/wiki/Cloud_computing) :thought_balloon:, увеличивая вероятность отказов при разрывах соединения с первичным оборудованием 🤔 Таким образом, без проникновения концепции [Open Source](https://en.wikipedia.org/wiki/Open_source) технический прогресс в этой отрасли смещается в сторону налаживания межоблачного взаимодействия и наблюдается замедление в развитии программной части для первичного оборудования (прошивки, операционные системы, языки программирования, конфигураторы) и соответственно самого первичного оборудования :confused: Ситуация вынуждает опытных разработчиков искать простора для полета их творческой мысли в стартапах на более мелких задачах :unamused: Требуется политическое решение
-->

Прошивки и конфигурация аппаратуры, топология локальных сетей, настройки коммутаторов и маршрутизаторов (адреса, шлюзы, серверы DHCP и DNS, vlan-ы и остальное) хранятся в своих папках на файловом сервере, откуда их можно открыть и прочитать на аппаратуре или в конфигураторах аппаратуры. Пути до них указаны в текстовой части на репозиториях. На `GitHub`-е также не отслеживаются - он их не понимает.

## Третий слой - оболочки

Если нужно что-то для многопользовательского и многократного повторного применения с одновременным графическим и текстовым вводом-выводом, ваяем [интерактивную оболочку](https://en.wikipedia.org/wiki/User_interface_design) на `Python`-е.

Если требуется что-то явить миру, дополнительно поверх серверной или отдельной клиентской компоненты подымаем и пробрасываем во внешку [ВЭБ-мордочку](https://en.wikipedia.org/wiki/Website "Версия для компьютера и мобильная версия") как [третий слой](https://en.wikipedia.org/wiki/Multitier_architecture#Three-tier_architecture), которая рисуется отдельно как внешняя разработка и в объем данных репозиториев может входить в виде подмодуля. [ВЭБ-разработка](https://en.wikipedia.org/wiki/Web_development "Разметка, верстка, дизайн, маркетинг, групповая психология ...") как часть [Internet-технологии](https://webonto.ru/internet-tehnologii-chto-eto-takoe/) в отличие от прикладного программирования - это отдельная трудоемкая отрасль. Исторически сложилось, что она росла сама по себе. Ее идея - в итоге с локальной инфраструктуры раскидать:
 - сайты,
 - структуры и базы данных,
 - запросы к ним,
 - схемы,
 - пространства имен с типами данных

по ресурсам на внешних адресах для удобства доступа к ним широкой публики с помощью обозревателя Интернета на толстых клиентах (смартфоны, планшеты). Для этого на `HTML + XML` чего только не наизобретали, но все-таки не все (прикладное и системное программирование вне досягаемости). Решили прикрутить к сайтам запросы к базам данных напрямую или через процедурные языки программирования, потом разнести части проекта по разнопрофильным облакам. Добавилась проблемка - наладить взаимодействие проекта на платформе с облаками например с СУБД (выбор опций на тарифе, учет траффика, управление учетками на проекте, токены, сертификаты, квоты, API-шки и многое другое). [💬](https://www.codeproject.com/Articles/5283291/Examples-of-Layered-Application-Architecture-Based "Первая статья - переложение лекций из Голландии (устаревшая, но в целом правильная точка зрения)") [💬](https://www.codeproject.com/Articles/5317447/Layered-Application-Architecture-with-a-Homogeneou "Вторая статья того же автора") Местами еще остались энтузиасты и последователи эпохи [бума доткомов](https://en.wikipedia.org/wiki/Dot-com_bubble), предлагающие как вариант перенести локальное ПО на сайты. Но гонять движущуюся пиксельную графику через провайдеров - не совсем здорово. К сайту можно прикрутить и раздать [мобильные приложухи](https://en.wikipedia.org/wiki/Mobile_app). Само собой при этом учетки Windows, которые привязаны к именам входа на СУБД, заменяются на что-то другое через таблицу соответствия.

[Tcl](https://www.tcl.tk/about/language.html "Делал некоторые графические оболочки с помощью среды разработки tkBuilder") [💬](https://en.wikipedia.org/wiki/Tcl "Описание") хорошо применялся в конце 1990-х и в начале 2000-х на [ORACLE Solaris](https://en.wikipedia.org/wiki/Oracle_Solaris) для написания скриптов-обработчиков виджетов в пользовательских и системных утилитах с графической оболочкой внутри среды разработки [tkBuilder](https://sourceforge.net/projects/tkbuilder84/) (см. снимок экрана ниже), [Komodo](https://www.activestate.com/products/komodo-ide/) и [GUI Builder](https://spectcl.sourceforge.net/).

![tkBuilder Начало 4](https://user-images.githubusercontent.com/104857185/219376538-1686668f-58e8-41e1-b9ff-a7f55ed34eaf.png)

[Java](https://en.wikipedia.org/wiki/Java_(programming_language) "Начал изучать его вместе с Python-ом и вскоре понял, что Python значительно лучше и полностью перешел на него.") по-тихому уходит в прошлое :chart_with_downwards_trend: Его поддержка на разных уровнях устаревает и засыхает :hourglass_flowing_sand: Проект на нем - как правило вязанка папок с файлами, в том числе `jar`-иками (сразу не сообразишь, где точка входа на исполнение). В основном допиливают и перепиливают наработки начала 2000-х, когда он перехватил инициативу и хорошо вписался в ВЭБ-разработку, а позднее в районе 7-ой версии переехал в мобильную разработку на [Android](https://en.wikipedia.org/wiki/Android_(operating_system)) :iphone:

[R](https://en.wikipedia.org/wiki/R_(programming_language) "Пробовал его для расчетов данных с SQL Server-а") - простенький предметно-ориентированный язык с бедным набором типов данных, рассчитанный на математиков и экономистов. В [Data Science](https://en.wikipedia.org/wiki/Data_science) с разным успехом применяют богатые возможности [DataFrame](https://www.rdocumentation.org/packages/base/versions/3.6.2/topics/data.frame)-ов для импорта моментальных снимков баз данных и анализа их срезов, но перегонять снимок в память - это круто даже для их серверов. Есть особенность - все числовые переменные векторные, поэтому операции над ними работают не по правилам арифметики, а по правилам действий с векторами и матрицами (векторно-скалярные преобразования и обратно). Графических приложений на нем не предвидится. Пока только скрипты, которые можно исполнять на интерпретаторе или внутри среды разработки [R Studio](https://en.wikipedia.org/wiki/RStudio "Еще сырая. Если зависает скрипт или одна вкладка, то виснет все. Если кодировка не ASCII и не win-1251, то лепит краказябру. В кадре терминала черным и красным шрифтом вываливает все, что надо и не надо. При занятости сервера СУБД его драйвер ждет несколько секунд и сбрасывает соединение. Для сравнения драйвер Python-а ждет часами и сутками"). Документации много. Есть много видео. Примеры узкоспециализированные, в основном от частного к общему (как и принято в США), что затрудняет понимание и перенос на другие примеры.

[Python](https://www.python.org/ "Есть мнение, что в математических расчетах он медленнее C++, но не прилагаются замеры. Когда делал прикладные программы на C++, то в журналах были горы ошибок и предупреждений, на Python-е - там пусто. Установленные интерпретаторы и библиотеки по отдельности лучше не обновлять - возможны глюки. Виртуальное окружение (интерпретатор и библиотеки указанных в файле `requirements.txt` версий) во многопользовательской системе - временная вынужденная мера, от которой по возможности надо уходить, потому что пользователям на клиентах дается ярлык (символическая или мягкая ссылка) на скрипт с файлового сервера, ставятся интерпретатор и используемые с ним библиотеки, но раздавать или делать дубликаты виртуального окружения со всеми переделками разработчика всем клиентам как-то не по фэншую") [💬](https://en.wikipedia.org/wiki/Python_(programming_language) "Описание") 🇳🇱 имеет необъятные возможности благодаря богатству типов данных и разработанным под него библиотекам, теперь надежно доминирует :chart_with_upwards_trend: :bar_chart: Очень много написано про его хорошие стороны. Дополнительно ко всему сказанному и написанному хочу отметить, что скрипты на нем меньше лезут в операционную систему как **C++** и больше работает в профиле пользователя.

[Mojo](https://en.wikipedia.org/wiki/Mojo_(programming_language)) [💬](https://docs.modular.com/mojo/programming-manual.html) [💬](https://www.kdnuggets.com/2023/05/mojo-lang-new-programming-language.html) [💬](https://habr.com/ru/articles/733896/) обещает повышенное быстродействие и упрощенное развертывание. Значимых наработок на нем пока нет.

## Библиотеки, [FrameWork](https://en.wikipedia.org/wiki/Software_framework)-и и среды разработки:

[tk, ttk и ttk+](https://en.wikipedia.org/wiki/Tk_(software)) используется на [twm](https://en.wikipedia.org/wiki/Twm) [💬](https://gitlab.freedesktop.org/xorg/app/twm "Исходники") в виде комплектной библиотеки [tkinter](https://en.wikipedia.org/wiki/Tkinter) с ограниченными по нынешним временам возможностями для творчества, которая содержит встроенный интерпретатор `tcl`, а также `ttk` (`tk` с темами, как и обещали на `Tcl 8.5`, с помощью [tk-builder](https://pypi.org/project/tk-builder) 🗯️).

[pySimpleGUI](https://www.pysimplegui.org/en/latest/) прост, интересен, имеет наборы стилей, внешне напоминает ВЭБ-разработку, но на нем мало примеров. 

[Gtk и Gtk+](https://en.wikipedia.org/wiki/GTK "В настоящее время имеют ошибки") используются в `Linux`-е в оконном мэнэджере [Gnome](https://en.wikipedia.org/wiki/GNOME). Библиотека [pyGTK](https://en.wikipedia.org/wiki/PyGTK) закрыта в 2011-м, на `Windows` пока не ставится, переехала на [pyGObject](https://pygobject.readthedocs.io/en/latest/) и начиная с версии 3 `GTK+` имеет ошибки. Есть открытые и коммерческие дизайнеры, в том числе [GTK Builder](https://docs.gtk.org/gtk3/class.Builder.html).

[wxPython](https://en.wikipedia.org/wiki/WxPython) неправильно отображает кодировки и не пропорцинально отображает виждеты в разных сочетаниях

[pyQt](https://en.wikipedia.org/wiki/Qt_(software)) позволяет вставлять не только комплектные виджеты, но также виджеты и графику из других фрэймворков. Есть комплектный [QtDesigner](https://doc.qt.io/qt-6/qtdesigner-manual.html) для рисования макетов и записи их отдельным ресурсным файлом :floppy_disk: для вставки их в проект внутри среды разработки [pyCharm](https://en.wikipedia.org/wiki/PyCharm) :netherlands: , которая просто идеальна :books:

## Замена бумажного и электронного документооборота, а также замена коммерческих консультантов

Руководящие документы (государственные и отраслевые):
 - Руководства,
 - Нормативы,
 - Стандарты,
 - Приказы,
 - Инструкции

необходимо перестать распечатывать на бумаге, а также гонять их копии разной давности с ЭЦП и без по электронной почте, ватсапам, телегам и соцсетям.

Необходимо:
 - **Дать доступ к ним** из единственного авторитетного источника в виде чистого императива, который может определенно и однозначно восприниматься прикладными программами для принятия решений и возврата отчетов о выполнении.
 - **Перенести** повествовательную часть в комментарии.
 - **Продумать** их структуру ветвления с данными, параметрами и ссылками на другие источники в зависимости от типа документа и его отрасли.
 - **Записать** их в поля `XML(CONTENT dbo.XSD-схема)` таблиц баз данных, которые можно **парсить** как [DOM](https://ru.wikipedia.org/wiki/Document_Object_Model) или даже как [SAX](https://en.wikipedia.org/wiki/Simple_API_for_XML) запросами вручную и программно в прикладных задачах :hibiscus: :four_leaf_clover:

![1 001 001](https://user-images.githubusercontent.com/104857185/167037090-9cd548c0-9643-4903-adce-13e2a039226d.jpg)

Таким образом документы и вносимые в них изменения смогут быстро и просто исполняться без:
 - перечитывания их текста,
 - сравнения с предыдущими редакциями,
 - трактования их разными людьми в разных контекстах и ситуациях.

<!--
## Интеграция проектов с [CORBA](https://en.wikipedia.org/wiki/Common_Object_Request_Broker_Architecture)

(раздел в процессе разработки)
-->

----
Связаться со мной можно в обсуждениях на репозиториях. К критике отношусь конструктивно. Буду благодарен за замечания.

Облагодетельствовать :sparkling_heart: можно на карточку :credit_card: <span style="color:Green">VISA</span> СберБанка 4276 3000 3587 2715
