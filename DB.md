# Базы данных

## Термины и определения

**Database (DB)** -

1. A **collection** of **interrelated** data stored together in one or more computerized files (ISO-IEC-IEEE 24765-2010);
2. A **collection** of data **organized according to a conceptual structure** describing the characteristics of the data and the relationships among their corresponding entities, supporting one or more application areas (ISO/IEC 2382-1:1993);
3. **Collection** of data **describing a specific target area** that is used and updated by one or more applications (ISO/IEC 29881:2008).

**Database Management System (DBMS)** - system, based on hardware and software, for defining, creating, manipulating, controlling, managing, and using databases. The software for using a database may be part of the database management system or may be stand-alone (ISO/IEC 2382:2015).

На основе этих определений можно выделить следующие признаки БД:

1. БД - коллекция данных;
2. В БД данные взаимосвязаны;
3. В БД данные организованы согласно определенной структуре (модели);ntl
4. В **рамках всей** БД данные объединены по определенному признаку;
5. БД управляется сторонними приложениями.

## Системы управления базами данных (СУБД)

### Архитектура СУБД

**Модель данных (data model)** - представление, **описывающее исходные данные** о реальном объекте (object).

Для разработки модели данных необходимы следующие компоненты:

1. Реальный объект (real object) (менеджер, клиент);
2. Аттрибуты (attributes) реального объекта (имя, фамилия, телефон):
3. Отношения (relationships) между объектами (одному менеджеру несколько клиентов)
4. Ограничения (constraints), накладываемые на исходные данные об объекте (телефон клиента должен состоять только из цифр)

### Типы СУБД

<table>
  <tr style="text-align: center">
    <td colspan="3">Type of DBMS</td>
    <td>DBMS</td>
    <td>Application</td>
    <td>Pros</td>
    <td>Cons</td>
  </tr>
  <tr>
    <td rowspan="8" style="writing-mode: vertical-lr; transform:scale(-1); text-align: center">By Data Model</td>
    <td colspan="2">Relational (SQL)</td>
    <td>MySQL, PostgreSQL, Oracle, MS SQL Server</td>
    <td>E-commerce, CRM</td>
    <td>
      • Data integrity<br/>
      • ACID compliance<br/>
      • Widely adopted
    </td>
    <td>
      • Rigid schema<br/>
      • No horizontal scaling
    </td> 
  </tr>
  <tr>
    <td rowspan="4" style="writing-mode: vertical-lr; transform:scale(-1); text-align: center">Non-relational (noSQL)</td>
    <td>Key-value</td>
    <td>Memcached, Redis, Amazon DynamoDB</td>
    <td>Caching user sessions, message brokers, IoT</td>
    <td rowspan="4">
      • Flexible<br/>
      • Handle various data structures<br/>
      • Manage large distributed datasets<br/>
      • Supports various data models
    </td>
    <td rowspan="4">
      • Lack of standards<br/>
      • Slow for simple queries
    </td>
  </tr>
  <tr>
    <td>Graph</td>
    <td>Neo4j, JanusGraph, Amazon Neptune</td>
    <td>Social network, recommender systems, fraud detection</td>
  </tr>
  <tr>
    <td>Wide-column</td>
    <td>Apache Cassandra, HBase, ScyllaDB</td>
    <td>Business interlligence, data warehouding, IoT</td>
  </tr>
  <tr>
    <td>Document-oriented</td>
    <td>MongoDB, Couchbase, Amazon Documnet DB</td>
    <td>CMS, social networks, catalogs, user profiles, gaming</td>
  </tr>
  <tr>
    <td colspan="2">Object-oriented</td>
    <td>db4o, ObjectDB, InterSystems Cache</td>
    <td>CRM, CAD, game design , navigation systems</td>
    <td>
      • Easy to model real-world problems<br/>
      • Reusable data models
    </td>
    <td>
      • Lack of standards<br/>
      • Slow for simple queries
    </td>
  </tr>
  <tr>
    <td colspan="2">Hierarchinal</td>
    <td>IBM Information Managment System</td>
    <td>IMS, financial record-keeping</td>
    <td>
      • Very simple<br/>
      • Data consistensy
    </td>
    <td>
      • Highly rigid<br/>
      • Vendor lock-in
    </td>
  </tr>
  <tr>
    <td colspan="2">Network</td>
    <td>IDMS, RaimaDB</td>
    <td>Telecommunication systems</td>
    <td>Flexibility compared to hierarchical DB</td>
    <td>
      • No query<br/>
      • Vendor lock-in
    </td>
  </tr>
  <tr>
    <td rowspan="2" style="writing-mode: vertical-lr; transform:scale(-1); text-align: center">By Data Storage</td>
    <td colspan="2">Row-based</td>
    <td>MySQL, PostgreSQL, Oracle, IBM Db2</td>
    <td>E-commerce, CRM, transaction apps</td>
    <td>
      • Fast CRUID<br/>
      • ACID compliance<br/>
      • Mature ecosystem
    </td>
    <td>
      • Slow data aggregation<br/>
      • Insufficient compression
    </td>
  </tr>
  <tr>
    <td colspan="2">Columnar</td>
    <td>Monet DB, Apache Cassandra, ClickHouse</td>
    <td>Business reporting, BPM</td>
    <td>
      • Easy compression<br/>
      • Fast aggregation
    </td>
    <td>
      • Slow CRUID<br/>
      • Not effective for real-time data processing
    </td>
  </tr>
  <tr>
    <td rowspan="3" style="writing-mode: vertical-lr; transform:scale(-1); text-align: center">By Purpose</td>
    <td colspan="2">OnLine Transaction Processing (OLTP)</td>
    <td>MySQL, PostgreSQL, Oracle</td>
    <td>CRUID operations, high transaction volumes</td>
    <td rowspan="3">Perfect for their goals</td>
    <td rowspan="3">Limited by definition</td>
  </tr>
  <tr>
    <td colspan="2">Online Analytical Processing (OLAP)</td>
    <td>Apache Pinot, DuckDB, ClickHouse</td>
    <td>Data analysis</td>
  </tr>
  <tr>
    <td colspan="2">Time-series</td>
    <td>InfluxDB, Prometheus, TimescaleDB</td>
    <td>Performance monitoring, sensor data collection, user activity logs</td>
  </tr>
  <tr>
    <td rowspan="2" style="writing-mode: vertical-lr; transform:scale(-1); text-align: center">By Deployment</td>
    <td colspan="2">Centralized</td>
    <td>MS SQL Server, Oracle DB, PostgreSQL</td>
    <td>Small to medium-sized org., single location</td>
    <td>Data security and integrity</td>
    <td>Traffic is high, efficiency is low</td>
    <tr>
      <td colspan="2">Distributed</td>
      <td>Apache Cassandra, Amazon DynamoDB, MongoDB</td>
      <td>eCommerce platforms, real-time analytics, cloud services</td>
      <td>
        • Easy to scale<br/>
        • Data available even in one locations
      </td>
      <td>
        • Data duplication<br/>
        • Security issues
      </td>
    </tr>
  </tr>
</table>

### Архитектура базы данных

**Транзакция** — серия из одной или нескольких операций над данными. Транзакции должны удовлетворять условиям ACID (atomicity, consistency, isolation, durability):

1. Атомарность (atomicity) - транзакция осуществляется в соответствии с принципом "все или ничего", т.е. должна быть выполнена либо вся целиком, либо не выполнена вовсе;
2. Согласованность (consistency) - транзакция фиксирует только допустимые результаты;
3. Изолированность (isolation) - транзакция выполняется таким образом, словно в тот же момент времени других транзакций не существует;
4. Устойчивость (durability) - результат выполнения транзакции не должен быть утрачен ни при каких условиях.

В 1975 году подкомитет Standards Planning And Requirements Committee (SPARC), входящий в институт ANSI (American National Standards Institute), предложил архитектуру ANSI-SPARC: трехуровневую модель абстракции данных ANSI-SPARC при проектировании СУБД:

![](/ANSI.svg)

Стандарт ANSI-SPARC не стал общепринятым, тем не менее идея независимости логики широко применяется в современных СУБД.

### Реляционные СУБД

#### Элементы реляционной алгебры

**Упорядоченное множестве \(S\)** — множество, с заданным на нем **бинарным** отношением \(≻\) («выше» или «следует за»), называемое **отношением порядка** и удовлетворяющее следующим условиям:

1. Транзитивность, то есть \(∀(a,b,c∈M)\ a≻b∩b≻c→a≻c\)
2. Антисимметричность, то есть \(∀(a,b,c∈M)\ a≻b∩b≻a→a=b\)

Таким образом упорядоченное множество является алгебраической системой \((M,≻)\).
Упорядоченное множество обозначается в круглых \(()\) или угловых \(⟨⟩\) скобках:

$$
(a_1, a_2, ... a_n)\\
⟨a_1, a_2, ... a_n⟩
$$

**Кортеж (tuple) \(T\) длины (размерности) \(n\)** — упорядоченное множество мощностью \(n\).

**Прямым (декартовым) произведением** множеств \(G_1,G_2\ ... \ G_n\) называется множество всех кортежей длины \(n\), элементы которых принадлежат этим множествам:

$$G_1×…×G_n=\{{(g_1,…,g_n )\ |\ g_i∈G_i,i=\overline{1,n}\}}$$

**Отношением \(R\) арности \(n\) (степени \(n\))** над множествами \(G_1\), \(G_2\) ... \(G_n\) называется подмножество прямого декартова произведения \(G_1×G_2× ... ×G_n\).

$$R⊆G_1×G_2×…×G_n\ или\ R(G_1,G_2...\ G_n)$$

**Кардианльное число \(k\)** отношения \(R\) — количество кортежей в отношении \(R\).

**Атрибутом (attribute) \(A_i\)** отношения \(R\) называется **имя (идентификатор)**, обозначающее какой-то аспект данной предметной области. Например,

$$A_1 = surname, A_2 = age, A_3 = gender.$$

<table>
<tr>
  <td>💡</td>
  <td>Aтрибуты должны быть уникальны в пределах одного отношения.</td>
</tr>
</table>


В реляционной модели данных также вводится понятие **домен (domains)** \(D_i\) — множество допустимых значений для данного атрибута \(A_{D_i}\). Понятие **домен** близко понятию **тип данных** (целое число, строка, перечисление и т. п.) с той разницей, что **тип данных** кроме множества допустимых значений включает в себя ещё и множество операций, которые заданы на данном множестве допустимых значений. Например, доменом может быть множество целых чисел \(\N\), множество всех слов на латинском алфавите \(\Sigma^{+}\). Также домен можно задать произвольно по аналогии с пользовательским типом данных. Например, домен возможных цветов:

$$COLOR=\{green, orange, black \}$$

Каждому атрибуту \(A_i\) ставится в соответствие только один домен \(D_{A_i}\) (наподобии, как в ЯП объявляется переменная с идентификатором \(A_i\) и типом данных \(D_{A_i}\)). Иногда домен \(D_{A_i}\) атрибута \(A_i\) обозначают через отображение \(dom(A_i)\):

$$dom: A_i \rightarrow D_{A_i}$$

<table>
<tr>
  <td>💡</td>
  <td>
    Один атрибут определен только на одном домене (один к одному).</br>
    На одном домене могут быть определены несколько атрибутов (один ко многим).
  </td>
</tr>
</table>

В реляционной модели данных отношение \(R\) состоит из схемы (scheme) \(\mathcal{S}\) и тела (body) \(\mathcal{B}\).

**Схемой (scheme) \(\mathcal{S}\)** отношения \(R\) называется совокупность **имени отношения** \(R\) и **кортеж** пар атрибут-домен \((A_i,D_{A_i})\). Схема \(\mathcal{S}\) отношения \(R\) обозначается следующим образом:

$$
\begin{array}{l}
\mathcal{S}=R\big(⟨A_1,D_{A_1}⟩,⟨A_2,D_{A_2}⟩,...⟨A_n,D_{A_n}⟩\big)\\[0.5em]
\mathcal{S}=R\big((A_1:D_{A_1}), (A_2:D_{A_2}),...(A_n:D_{A_n})\big)
\end{array}
$$

По сути схема \(\mathcal{S}\) отношения \(R\) есть отношение на множествах, состоящих из одной пары \((A_i,D_{A_i})\).

$$
\mathcal{S} \subseteq \prod_{i=1}^n(A_i,D_{A_i})=(A_1,D_{A_1})\times(A_2,D_{A_2})\times...\times(A_n,D_{A_n})
$$

Например,

$$
\begin{array}{l}
\mathcal{S}_1=R\big(⟨name,string⟩,⟨surname,string⟩,⟨age,int⟩\big)\\[0.5em]
\mathcal{S}_2=R\big((color:COLOR),(length:float),(width:float)\big)
\end{array}
$$

Иногда в схеме \(\mathcal{S}\) опускают множество доменов \(D_{A_i}\), так как всё равно существует отображение \(dom(A_i)\). Тогда схему \(\mathcal{S}\) отношения \(R\) записывают сокращенно:

$$\mathcal{S}=R(A_1, A_2,...A_n)$$

Например,

$$STUDENT(name,\ surname,\ age,\ rating)$$

**Полем (field) \(f_i\)** отношения \(R\) называется пара атрибут-значение \(⟨A_i,v_i⟩\), где значение \(v_i\) принадлежит соответствующему домену \(D_{A_i}\).

$$f_i=⟨A_i,v_i⟩,\ v_i∈D_{A_i},i=\overline{1,n}$$

**Телом (body) \(\mathcal{B}\)** отношения \(R\) называется множество кортежей \(t_i\), состоящих из полей \(f_i=⟨A_i,v_i⟩\):

$$
\begin{array}{l}
\mathcal{B}=\{t_1,t_2,...t_n\}\\[0.5em]
\mathcal{B}=\{(f_1, f_2,...f_n):f_i\in t_i,\ i=\overline{1,n}\}\\[0.5em]
\mathcal{B}=\Big\{\big(⟨A_1,v_1⟩, ⟨A_2,v_2⟩,...⟨A_n,v_n⟩\big):v_i∈D_{A_i},i=\overline{1,n}\Big\}
\end{array}
$$

<table>
<tr>
  <td>💡</td>
  <td>
    Порядок кортежей не имеет значение
  </td>
</tr>
</table>

**Иногда в реляционной алгбере термином тело \(\mathcal{B}\) отношения \(R\) называют непосредственно само отношение \(R\).**

Тем не мнее данное отношение \(R\) можно представить в виде таблицы:

<img src="/pics/relation.svg" style="width: 600px">


В связи с этим существует соотвествие между математическими и табличными терминами:

|Математический термин|Табличный термин|
|---|---|
|Отношение|Таблица|
|Схема отношения|Заголовок таблицы|
|Арность (степень) отношение|Число столбцов|
|Кардинальность отношения|Число строк|
|Атрибут|Имя столбца|
|Домен|Множество допустимых значений для столбца|
|Кортеж|Строка|
|Поле|Ячейка таблицы|

#### Операции реляционной алгебры

В реляционной алгебре существует следующие операции над отношениями:

<img src="/pics/operators.svg" style="width: 700px"/>

Для математического описания данных операций необходимо ввести ряд терминов и определений из алгебры предикатов (раздел алгебры логики).

**Булевым множеством \(E_2\)** называется множество вида:
 
$$E_2 = \{0,1\}$$


**Предикатом (\(n\)-местным) \(\varphi\)** называется функция (отображение) декартового произведения множеств \(G_1\times G_2 \times ... \times G_n\) в булево множество \(E_2\):

$$ \varphi: G_1\times G_2 \times ... \times G_n \rightarrow E_2$$

Таким образом, каждый набор элементов (кортеж) из \(G_1\times G_2 \times ... \times G_n\)  характеризуется либо как «истинный», либо как «ложный». 

Например, функция сравнения \(\le\) на множестве \(\Reals\) является двухместным предикатом:

$$\le:\Reals \times \Reals \rightarrow E_2$$


##### Выборка (Select)

Выборкой (Select) \(\sigma_\varphi\) с предикатом \(\varphi\) на отношении \(R\) называется операция вида:

$$
\boxed{\sigma_{\varphi}: R \rightarrow r,\ где\ r\in R,\ \varphi(R)=1}
$$




---


## Structured Query Language (SQL)

SQL является непроцедурным языком и не языком общего назначения.
Если необходимо реализовать процедурную логику нужен другой язык, такой как Python, C#, Java и т.п.

- **DDL** (Data Definiotion Language): CREATE, ALTER, DROP
- **DML** (Data Manipulation Language): SELECT, INSERT, UPDATE, DELETE
- **TCL** (Transaction Control Language): COMMIT, ROLLBACK, SAVEPOINT
- **DCL** (Data Control Language): GRANT, REVOKE, DENY

Стандарт SQL - ANSI SQL-92.

В популярных СУБД используется **диалект** SQL (расширенный вариант стандартного SQL):

- **PL/pgSQL** в PostgreSQL;
- **PL/SQL** в Oracle;
- **T-SQL** в MS SQL.
