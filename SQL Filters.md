# Applying Filters to SQL Queries

## Project description

The given scenario are as follows:  

*You are a security professional at a large organization. Part of your job is to investigate security issues to help keep the system secure. You recently discovered some potential security issues that involve login attempts and employee machines.*

*Your task is to examine the organization’s data in their employees and log_in_attempts tables. You’ll need to use SQL filters to retrieve records from different datasets and investigate the potential security issues.*

## Retrieve after hours failed login attempts

![image](https://github.com/jhung-cybersecurity/Portfolio-Activity_6-SQL-Query-Filters/assets/139807613/8d4f5df8-18de-4659-8d81-1558a4444573)

**Steps taken to get the results above:**  

1. I use `Select *` to include all contents in the database followed by `From log_in_attempts` to specify the extact table.
2. I use `Where login_time > '18:00' and success = 0;` in order to identify all failed login attempts that occured after 18:00. `success = 0` is used to filter attempts which resulted in a failure. If I'd like to filter a successful attempt, I'd use `success = 1`.


## Retrieve login attempts on specific dates

![image](https://github.com/jhung-cybersecurity/Portfolio-Activity_6-SQL-Query-Filters/assets/139807613/c593a0c1-e079-479b-b62e-02a2f7d0de96)

**Steps taken to get the results above:**  

1. In order to filter login attempts between two specified dates, I start my query by using `Select *` followed by `From log_in_attempts`.
2. I procceed to use `Where login_date = '2022-05-09' or login_date = '2022-05-08`. The reason why I use `OR` instead of `AND` is because I am looking for individual data that falls under those specified dates, not together.
3. Lastly, I use `Order by login_date` simply to tidy up the table for ease of reading.

```
Note: Only the top of part of the table is shown here due to the size of the full table.
```


## Retrieve login attempts outside of Mexico

![image](https://github.com/jhung-cybersecurity/Portfolio-Activity_6-SQL-Query-Filters/assets/139807613/462cd29b-410e-4c26-b756-3dd9d77e529b)

**Steps taken to get the results above:**  

1. The team has determined that this suspicious activitty didn't orginate in Mexico so I start my query by using `Select *` followed by `From log_in_attempts`.
2. Then I use `Where NOT country LIKE 'MEX%';
3. The `NOT` operator works to filter out whatever I put in the argument, in this case, it will filter out anything that's from `MEX`.
4. `LIKE 'MEX%'` is used in the command line to indicate any country that begins with `MEX` and end with anything will be filtered out. In this case, `MEXICO` and `MEX` are both used, so we apply the wildcard `%`.


## Retrieve employees in Marketing

![image](https://github.com/jhung-cybersecurity/Portfolio-Activity_6-SQL-Query-Filters/assets/139807613/f13f6001-b9ec-4e08-af5f-4453857f470a)


**Steps taken to get the results above:**  

1. My team wants to perform security updates on specific employee PCs in the Marketing department so I need to provide those information to my team. I start my query with `Select *` and `From employees`.
2. Then I use `Where department = Marketing and office like 'East%'`
3. The first part of the query line was explained simliarly in the prior steps.
4. `...and office like 'East%'` is used here because these employees work from different buldings. We narrow it down by using the wild card `%` after `East`. 

## Retrieve employees in Finance or Sales

![image](https://github.com/jhung-cybersecurity/Portfolio-Activity_6-SQL-Query-Filters/assets/139807613/650a1eb6-361a-4946-a0dc-7a6ed07d43a4)

**Steps taken to get the results above:**  

1. In order to query employees in the Finance or Sales, I follow similar steps by using `Select *` and `From employees`.
2. Then I use `Where department = 'Finance' or department = 'Sales`.
3. I applied `OR` instead of `AND` because I am looking for seperate answers and not merged answer.

## Retrieve all employees not in IT

![image](https://github.com/jhung-cybersecurity/Portfolio-Activity_6-SQL-Query-Filters/assets/139807613/82567ace-4e66-492c-99e3-3d883265b625)

**Steps taken to get the results above:**  

1. In order to query anyone not in the Information Technology department, I use `Select *` and `From employees`.
2. Then I use `Where not department = 'Information Technology';`.
3. The query line above will return a result without any employees from the Information Technology department.  


## Summary 

In This portfolio activity, I performed different filtering queries mainly through `AND`, `OR` AND `LIKE` to extract a specified employee or employees in order to perform verious tasks. 
