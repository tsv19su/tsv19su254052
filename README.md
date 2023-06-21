[Объемы выполняемых работ и способы их выполнения](https://github.com/tsv19su254052/tsv19su254052/blob/main/Works.md)

[Применяемые языки программирования и их библиотеки](https://github.com/tsv19su254052/tsv19su254052/blob/main/Languages.md)

Репозитории индувидуальной разработки здесь и в организациях являются так сказать **неполными бэкапами** отслеживаемых на `Git`-е **файлов и папок проектов**, разработанных в том числе по подсказкам со [StackOverFlow](https://stackoverflow.com/users/15883118/tarasov-sergey "Помогает ориентироваться в огромном разнообразии библиотек и их методов на основе опыта их применения другими опытными разработчиками") и с [ChatGPT](https://openai.com/product/gpt-4 "Ищет ответы на короткие вопросы") и хранящихся в сетевой папке на файловом сервере, которые полностью функциональны внутри инфраструктуры и могут запускаться на исполнение следующими способами:
 - из внешней сети или в локальной подсетке по RDP на терминальном сервере - один набор интерпретаторов и их библиотек для всех пользователей.
 - в локальной подсетке на клиенте по ярлыку (по символьной ссылке) c подключенной сетевой папки - интерпретатор и библиотеки устанавливаются на каждом клиенте дополнительно.

Базы данных и их бэкапы хранятся на сервере СУБД и привязаны к его системным настройкам.

Прошивки и конфигурация аппаратуры, топология локальных сетей и настройки коммутаторов и маршрутизаторов (адреса, шлюзы, сервера, vlan-ы и остальное) хранятся в своих папках на файловом сервере, откуда их можно открыть и прочитать на аппаратуре или в конфигураторах аппаратуры. Пути до них указаны в текстовой части на репозиториях.

Функция `GitHub`-а на репозитории ограничена возможностью:
 - [x] выбрать текущую ветку,
 - [x] почитать текстовые и графические пояснения к проекту,
 - [x] ознакомиться с математическим обеспечением,
 - [x] посмотреть исходники,
 - [x] почитать объемы доработок,
 - [x] предложить правку с помощью `Pull Request`-а, предварительно уточнив ветку для внесения правок,
 - [ ] склонировать исходники себе или ответвить их у себя (непрактично, так как клон или ветка со временем устареет или разойдется с оригиналом и будет конфликт слияния).

Суммируя обращения к документации по `GitHub`-у и учитывая некоторый практический опыт работы с ним в том числе, дополнительно отмечу некоторые моменты:
 - На репозиториях оригиналов подмодулей значек <span style="color:Green">"Used by ..."</span> пока не появляется с включенным графом зависимостей или без него (см. [статью](https://stackoverflow.com/questions/56888176/how-to-configure-github-used-by-feature-for-java-projects)).
 - Синхронизировать подмодули на репозитории и его клонах средствами `GitHub`-а не получится (там только неактивные ссылки), потому что они асинхронно импортированы внутри среды разработки в проект как дубликаты (импортируются и синхронизируются с их оригиналами в окошке терминала командами `git submodules ...`) и соответственно не отслеживаются на `Git`-е (не дублируются дважды) для экономии места на репозитории. Свои подмодули не импортирую (они у меня есть).
 - Перетасовывать папки и файлы внутри папки проекта ([Git](https://en.wikipedia.org/wiki/Git) и [SVN](https://en.wikipedia.org/wiki/Apache_Subversion) это допускают в отличие от [CVS](https://en.wikipedia.org/wiki/Concurrent_Versions_System)) нежелательно. При обновлении кое-что может улететь с репозитория и из проекта, поэтому надо проверить их наличие и привязку на `Git`-е перед обновлением.
 - При добавлении участника в `Contributor`-ы его активность на `GitHub`-е (если она ему так важна и нужна) <span style="color:red;"> не видна ни у него, ни у остальных </span>.
 - Желательно делать `Commit`-ы на определенных стадиях готовности, чтобы не было сложностей со сведением `Pull Request`-ов на оперативной ветке.
 - При смене или переименовании недоменной учетки или при смене локального пароля на `Windows`, а также смене учетки на `Google` плагин `Git`-а в `pyCharm`-е не синхронизирует проект с `GitHub`-ом и не видит историю изменений. Пишет, что срабатывает второй и третий фактор проверки владения репозиторием (см. прилагаемый снимок экрана ниже) и придется переезжать на новую учетку на `GitHub`-е.

![pyCharm - Ошибка синхронизации с GitHub-ом (другая учетка)](https://user-images.githubusercontent.com/104857185/216789558-ea500396-740e-4977-a426-22d01753f799.png)

Выход из ситуации - команда `git config --global --add safe.directory ...` , но она срабатывает на один сеанс работы с проектом.

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

Только `GitHub`-а для самостоятельной работы недостаточно и если проект на платформе с доступом не по RDP, то можно попробовать совместную работу на [coda.io](https://coda.io/workspaces/ws-ga7Eabm46u/folders/fl-7OkuhzSo66?source=doc-title-bar) с пре-коммитами [Terraform](https://en.wikipedia.org/wiki/Terraform_(software)) на инфраструктуре облака. Но там уже надо по-серьезному рисовать проект, писать конфиги и все полностью закидывать туда.

----
Связаться со мной можно в обсуждениях на репозиториях. К критике отношусь конструктивно. Буду благодарен за замечания.

Облагодетельствовать :sparkling_heart: можно на карточку :credit_card: <span style="color:Green">VISA</span> СберБанка 4276 3000 3587 2715
