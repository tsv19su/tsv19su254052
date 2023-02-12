[Объемы выполняемых работ и способы их выполнения](https://github.com/tsv19su254052/tsv19su254052/blob/main/Works.md)

[Применяемые языки программирования и их библиотеки](https://github.com/tsv19su254052/tsv19su254052/blob/main/Languages.md)

Репозитории индувидуальной разработки здесь и в организациях являются так сказать неполными **бэкапами с оригиналов проектов** (только отслеживаемые на `Git`-е файлы проекта).

Функция `GitHub`-а на репозитории ограничена возможностью:
 - выбрать текущую ветку,
 - почитать текстовые и графические пояснения к проекту,
 - ознакомиться с математическим обеспечением,
 - посмотреть исходники,
 - почитать объемы доработок,
 - предложить правку с помощью `Pull Request`-а, предварительно уточнив ветку для внесения правок,
 - склонировать исходники себе или ответвить их у себя (непрактично, так как клон или ветка со временем устареет или разойдется с оригиналом и будет конфликт слияния).

Суммируя обращения к документации по `GitHub`-у и учитывая некоторый практический опыт работы с ним в том числе, дополнительно отмечу некоторые моменты:
 - На репозиториях оригиналов подмодулей значек <span style="color:Green">"Used by ..."</span> пока не появляется с включенным графом зависимостей или без него (см. [статью](https://stackoverflow.com/questions/56888176/how-to-configure-github-used-by-feature-for-java-projects)).
 - Синхронизировать подмодули на репозитории и его клонах средствами `GitHub`-а не получится (там только неактивные ссылки), потому что они асинхронно импортированы внутри среды разработки в проект как дубликаты (импортируются и синхронизируются с их оригиналами в окошке терминала командами `git submodules ...`) и соответственно не отслеживаются на `Git`-е (не дублируются дважды) для экономии места на репозитории. Свои подмодули не импортирую (они у меня есть).
 - Перетасовывать папки и файлы внутри папки проекта ([Git](https://en.wikipedia.org/wiki/Git) и [SVN](https://en.wikipedia.org/wiki/Apache_Subversion) это допускают в отличие от [CVS](https://en.wikipedia.org/wiki/Concurrent_Versions_System)) нежелательно. При обновлении кое-что можеть улететь на репозитории и в проекте, поэтому их надо проверить и перепривязать в `Git`-е снова.
 - При добавлении участника в `Contributor`-ы его активность на `GitHub`-е (если она ему так важна и нужна) не видна ни у него, ни у остальных.
 - Делать `Commit`-ы желательно почаще, чтобы не было сложностей со сведением `Pull Request`-ов на оперативной ветке.
 - При смене или переименовании недоменной учетки (а также локального пароля) на `Windows`, а также смене учетки на `Google` плагин `Git`-а в `pyCharm`-е не синхронизирует проект с `GitHub`-ом. Пишет, что срабатывает второй и третий фактор проверки владения репозиторием (см. прилагаемый снимок экрана ниже) и придется переезжать на новую учетку на `GitHub`-е. Есть длинная команда `git config ...` , но она к сожалению не срабатывает ... .

![pyCharm - Ошибка синхронизации с GitHub-ом (другая учетка)](https://user-images.githubusercontent.com/104857185/216789558-ea500396-740e-4977-a426-22d01753f799.png)

Само собой только функционала `GitHub`-а для автономной самостоятельной работы недостаточно и если проект с ВЭБ-сайтом на платформе, то можно попробовать совместную работу на [coda.io](https://coda.io/workspaces/ws-ga7Eabm46u/folders/fl-7OkuhzSo66?source=doc-title-bar) с пре-коммитами [Terraform](https://en.wikipedia.org/wiki/Terraform_(software)) на инфраструктуре облака. Но там уже надо по-серьезному рисовать проект, писать конфиги и все полностью закидывать туда. Для остальных случаев есть терминальный сервер в своей папке проекта мимо `GitHub`-а. Оригиналы проектов хранятся в сетевой папке на нем, полностью функциональны только внутри инфраструктуры и могут запускаться на исполнение:
 - из внешней сети или в локальной подсетке по RDP на терминальном сервере (один набор интерпретаторов и их библиотек для всех пользователей),
 - в локальной подсетке на клиенте c подключенной сетевой папки (интерпретатор и библиотеки, устанавливаются на каждом клиенте дополнительно).

Можно применять комбинированный подход, но самое основное и для проверки сделанного - лучше первым способом. Глюков быть не должно.

Базы данных и их бэкапы хранятся на сервере СУБД и привязаны к его системным настройкам.

Конфигурация и топология аппаратуры, прошивки аппаратуры, настройки локальной сети (адреса, шлюзы, сервера, vlan-ы и остальное) хранятся в своих папках на файловом сервере (пути до них указаны в репозиториях), откуда их можно открыть и прочитать на аппаратуре или в конфигураторе аппаратуры.

Клиенты в локальной подсетке сидят на изолированных портах коммутатора.

----
Связаться со мной можно в обсуждениях на репозиториях. К критике отношусь конструктивно. Буду благодарен за замечания.

Облагодетельствовать :sparkling_heart: можно на карточку :credit_card: <span style="color:Green">VISA</span> СберБанка 4276 3000 3587 2715
