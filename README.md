Тарасов Сергей Владимирович
----------------------------

 - Прототипирование
 - Расчеты и математическое моделирование
 - Прикладное программирование на **[C++](https://en.wikipedia.org/wiki/C%2B%2B)**, **[Tcl/Tk](https://en.wikipedia.org/wiki/Tcl)**, **[Python](https://en.wikipedia.org/wiki/Python_(programming_language))** (Текстовые приложения, Графические оболочки, API-шки)
 - Разработка и администрирование баз данных на **MS SQL Server**-е в части **[SQL](https://en.wikipedia.org/wiki/SQL) + [XML](https://en.wikipedia.org/wiki/XML)** [описание](http://www.chernyshov.com/SPPO_6/theory/wt_xml.htm) ([XPath](https://en.wikipedia.org/wiki/XPath) & [XQuery](https://en.wikipedia.org/wiki/XQuery), [EXPath](http://expath.org/), [XSD](https://en.wikipedia.org/wiki/XML_Schema_(W3C)) [описание](https://bdpx.github.io/xml/lab3/xsd.html), [XSL](https://ru.wikipedia.org/wiki/XSL), [XSLT](https://en.wikipedia.org/wiki/XSLT). [EXSLT](https://ru.wikipedia.org/wiki/EXSLT), [Relax NG](https://en.wikipedia.org/wiki/RELAX_NG), [XSpec](https://github.com/expath/xspec/tree/master), [XLink](https://en.wikipedia.org/wiki/XLink), [XMark](https://projects.cwi.nl/xmark/index.html), [XInclude](https://www.w3.org/TR/xinclude/), [XProc](https://en.wikipedia.org/wiki/XProc), [OPML](https://en.wikipedia.org/wiki/OPML), [XQL](http://www.ibiblio.org/xql/xql-proposal.html))

![007 001 001](https://user-images.githubusercontent.com/104857185/209877366-3c1a9309-736c-49ce-9bb3-709e16110020.jpg)

Примечания:
SQL и XML по отдельности имеют много разной критики, но по полноте функционала замены пока нет. Есть определенные сложности в преобразовании типов данных Python -> SQL -> XML (типы пространств имен XSD, типы данных XQuery и остальное) и обратно. Есть трудности в передаче результата работы функций и процедур Python -> SQL -> XPath & XQuery и обратно. Поэтому написать, протестировать и отладить в полном объеме - трудная и сложная работа. Идут работы по разработке собственного [функционала](https://docs.sqlalchemy.org/en/14/dialects/mssql.html#module-sqlalchemy.dialects.mssql.pyodbc) для работы с СУБД внутри Python-а. Нет плагина или интеграции [Saxon-а](https://www.saxonica.com/about/about.xml), [Schematron-а](https://en.wikipedia.org/wiki/Schematron) и возможностей [BaseX](https://ru.wikipedia.org/wiki/BaseX) внутри ядра баз данных SQL Server-а
