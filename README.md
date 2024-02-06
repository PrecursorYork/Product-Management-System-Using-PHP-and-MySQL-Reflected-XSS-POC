# Product Management System Using PHP and MySQL Reflected-XSS POC

+ Exploit Author: YU Ke
  
  # Vendor Homepage

+ https://www.sourcecodester.com/php/17148/product-management-system-using-php-and-mysql-source-code.html
  
  # Overview

+ Product Management System Using PHP and MySQL Reflected-XSS POC is susceptible to a significant security vulnerability that arises from insufficient protection on the 'supplier_name' & 'supplier_contact' parameters in the supplier.php & /endpoint/add_supplier.php file. Attackers can inject malicious JavaScript code into website databases, and when victim users extract and load this JavaScript code, they will be attacked.
  
  # Vulnerability Details

+ Affected Version: Product Management System Using PHP and MySQL with Source Code V1.0

+ Vulnerable File: /supplier.php

+ Parameter Names: 'supplier_name' & 'supplier_contact'

+ # Description

+ Due to the lack of proper input validation and purification for the 'supplier_name' & 'supplier_contact' parameter, attackers can save malicious JavaScript code in the database by inputting it. When the victim accesses the database, malicious code will be loaded, causing the visitor to be attacked. And more importantly, the administrator account and password of the system are written in a fixed way in the source code, which can be easily discovered and accessed by attackers.

# Proof of Concept (PoC) :

+ Found fixed administrator account and password in the source code:
  ![image](https://github.com/PrecursorYork/Product-Management-System-Using-PHP-and-MySQL-Reflected-XSS-POC/raw/main/1.png)

+ Login the system. Simulate inputting certain malicious JavaScript code in add_supplier.php and submit the results to save in the database:

![image](https://github.com/PrecursorYork/Product-Management-System-Using-PHP-and-MySQL-Reflected-XSS-POC/raw/main/2.png)

+ When refreshing the page again, the JavaScript code will be triggered because the malicious code in the database is extracted, displayed, and loaded by the browser:
  ![image](https://github.com/PrecursorYork/Product-Management-System-Using-PHP-and-MySQL-Reflected-XSS-POC/raw/main/3.png)
  ![image](https://github.com/PrecursorYork/Product-Management-System-Using-PHP-and-MySQL-Reflected-XSS-POC/raw/main/4.png)
  ![image](https://github.com/PrecursorYork/Product-Management-System-Using-PHP-and-MySQL-Reflected-XSS-POC/raw/main/5.png)
