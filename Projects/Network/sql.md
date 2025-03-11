<div style="display: inline-block;">
  <a href="https://breachopen.github.io/Chas-Riley/">
    <img src="https://img.shields.io/badge/Home-3ba0e6" alt="Home">
  </a>
</div>

<div style="display: inline-block;">
  <a href="https://github.com/BreachOpen/Chas-Riley/" target="_blank">
    <img src="https://img.shields.io/badge/Github_Source-3ba0e6" alt="Github Source">
  </a>
</div>


---

# SQL Failed Login Attempts Investigation

## Scenario
In this scenario, you need to obtain specific information about employees, their machines, and the departments they belong to from the database.<br />
Your team needs data to investigate potential security issues and to update computers.<br />
You are responsible for filtering the required information from the database.<br /><br />
Here’s how you’ll do this task:
- First, you’ll retrieve all failed login attempts after business hours.
- Second, you’ll retrieve all login attempts that occurred on specific dates.
- Third, you’ll retrieve logins that didn't originate in Mexico.
- Fourth, you’ll retrieve information about certain employees in the Marketing department.
- Fifth, you’ll retrieve information about employees in the Finance or the Sales department.
- Finally, you’ll obtain information about employees who are not in the Information Technology department.<br /><br />

## Tasks
First, I needed to log into the organization's SQL database.<br /><br />
Command I used: <br />
sudo mysql organization<br /><br />

![SQL Login](../../assets/img/network/sql/1.png)<br /><br />

**Task 1. Retrieve after hours failed login attempts**<br />
Your team is investigating failed login attempts that were made after business hours. You want to retrieve this information from the login activity. You’ll identify all unsuccessful attempts after 18:00.<br /><br />

Command I used: <br />
SELECT *<br />
FROM log_in_attempts<br />
WHERE login_time > '18:00' AND success = 0;<br /><br />

Question Given: How many failed login attempts occurred after 18:00?<br />
My Answer: 19<br /><br />

![Login Fails](../../assets/img/network/sql/2.png)<br /><br />

**Task 2. Retrieve login attempts on specific dates**<br />
Our team is investigating a suspicious event that occurred on '2022-05-09'. You want to retrieve all login attempts that occurred on this day and the day before ('2022-05-08').<br /><br />

Command I used: <br />
SELECT * <br />
FROM log_in_attempts <br />
WHERE login_date = '2022-05-09' OR login_date = '2022-05-08';<br /><br />

Question Given: How many login attempts were made on these two days?<br />
My Answer: 75<br /><br />

![Login Date Part 1](../../assets/img/network/sql/3.png)<br />
![Login Date Part 2](../../assets/img/network/sql/4.png)<br /><br />

**Task 3. Retrieve login attempts outside of Mexico**<br />
Now, your team is investigating logins that did not originate in Mexico, and you need to find this information. <br />*Note that the country field includes entries with 'MEX' and 'MEXICO'. You should use the NOT and LIKE operators and the matching pattern 'MEX%'.<br /><br />

Command I used: <br />
SELECT * <br />
FROM log_in_attempts<br />
WHERE NOT country LIKE 'MEX%';<br /><br />

Question Given: How many login attempts were made outside of Mexico?<br />
My Answer: 144<br /><br />

![Mex Part 1](../../assets/img/network/sql/5.png)<br />
![Mex Part 2](../../assets/img/network/sql/6.png)<br /><br />

**Task 4. Retrieve employees in Marketing**<br />
Your team is updating employee machines, and you need to obtain the information about employees in the 'Marketing' department who are located in all offices in the East building (such as 'East-170' or 'East-320').<br /><br />

To see which categories (foreign key tables) were located within the database, I needed to view all data listed in the "employees" key.<br /><br />

Command I used: <br />
SELECT * <br />
FROM employees;<br />

![Database Categories](../../assets/img/network/sql/7.png)<br /><br />

Question Given: What is the username of the first employee in the Marketing department in the East building?<br />
My Answer: elarson<br /><br />

![Marketing Dept](../../assets/img/network/sql/8.png)<br /><br />

**Task 5. Retrieve employees in Finance or Sales**<br />
Now, your team needs to perform a different update to the computers of all employees in the 'Finance' or the 'Sales' department, and you need to locate information on these employees.
<br /><br />

Command I used: <br />
SELECT * <br />
FROM employees<br />
WHERE department = 'Finance' OR department = 'Sales';<br /><br />

Question Given: What is the username of the first employee in the Sales department returned by the query?<br />
My Answer: lrodriqu<br /><br />

![1st Employee Listed](../../assets/img/network/sql/9.png)<br /><br />

**Task 6. Retrieve all employees not in IT**<br />
Your team needs to make one more update. This update was already made to employee computers in the 'Information Technology' department. The team needs information about employees who are not in that department. You should use the NOT operator to identify these employees.<br /><br />
Command I used: <br />
SELECT * <br />
FROM employees<br />
WHERE NOT department = 'Information Technology';<br /><br />

Question Given: How many employees are not in the Information Technology department?<br />
My Answer: 161<br /><br />

![Full List Part 1](../../assets/img/network/sql/10.png)<br />
![Full List Part 2](../../assets/img/network/sql/11.png)<br /><br />
--- 
