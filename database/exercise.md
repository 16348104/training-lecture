# 附：练习题

## Sample database structure

> Table `emp`

 Field    | Type        | Null | Key | Default | Extra
----------|-------------|------|-----|---------|-------
 EMPNO    | int(4)      | NO   | PRI | NULL    |       
 ENAME    | varchar(10) | YES  |     | NULL    |       
 JOB      | varchar(9)  | YES  |     | NULL    |       
 MGR      | int(4)      | YES  |     | NULL    |       
 HIREDATE | date        | YES  |     | NULL    |       
 SAL      | double(7,2) | YES  |     | NULL    |       
 COMM     | double(7,2) | YES  |     | NULL    |       
 DEPTNO   | int(2)      | YES  | MUL | NULL    |       

> Table `dept`

 Field  | Type        | Null | Key | Default | Extra 
--------|-------------|------|-----|---------|-------
 DEPTNO | int(2)      | NO   | PRI | NULL    |       
 DNAME  | varchar(14) | YES  |     | NULL    |       
 LOC    | varchar(13) | YES  |     | NULL    |       

> Table `salgrade`

 Field | Type    | Null | Key | Default | Extra 
-------|---------|------|-----|---------|-------
 GRADE | int(11) | YES  |     | NULL    |       
 LOSAL | int(11) | YES  |     | NULL    |      
 HISAL | int(11) | YES  |     | NULL    |      


> 工资 = 基本工资 + 奖金

## PART I

- \# 1. 查找部门30中员工的详细信息。

```sql
SELECT * -- tiger
FROM emp
WHERE DEPTNO = 30;
```

- \# 2. 找出从事clerk工作的员工的编号、姓名、部门号。

```sql
SELECT
  EMPNO,
  ENAME,
  DEPTNO
FROM emp
WHERE JOB = 'clerk';
```

- \# 3. 检索出奖金多于基本工资的员工信息。

```sql
SELECT *
FROM emp
WHERE COMM > SAL; -- ?

SELECT COMM
FROM emp
ORDER BY COMM;
```

- \# 4. 检索出奖金多于基本工资60%的员工信息。

```sql
SELECT *
FROM emp
WHERE COMM > emp.SAL * 0.3;
```

- \# 5. 希望看到10部门的经理或者20部门的职员(clerk)的信息。

```sql
SELECT *
FROM emp
WHERE (DEPTNO = 10 AND JOB = 'manager') OR (DEPTNO = 20 AND JOB = 'clerk');
```

- \# 6. 找出10部门的经理、20部门的职员或者既不是经理也不是职员但是高于2000元的员工信息。

```sql
SELECT *
FROM emp
WHERE (DEPTNO = 10 AND JOB = 'manager') OR (DEPTNO = 20 AND JOB = 'clerk')
      OR (JOB NOT IN ('manager', 'clerk') AND sal + ifnull(COMM, 0) > 2000);
```

- \# 7. 找出获得奖金的员工的工作。

```sql
SELECT
  job,
  COMM
FROM emp
WHERE COMM IS NOT NULL;
```

- \# 8. 找出奖金少于100或者没有获得奖金的员工的信息。

```sql
SELECT *
FROM emp
WHERE COMM IS NULL OR emp.COMM < 100;
```

- \# 9. 查找员工雇佣日期中当月的最后一天雇佣的。

```sql
SELECT *
FROM emp
WHERE HIREDATE = last_day(HIREDATE);

UPDATE emp
SET HIREDATE = last_day(HIREDATE)
WHERE ENAME = 'king';
```

- \# 10. 检索出雇佣年限超过35年的员工信息。

```sql
SELECT
  ENAME,
  HIREDATE
FROM emp
WHERE date_sub(current_date, INTERVAL 35 YEAR) > emp.HIREDATE;
```

- \# 11. 找出姓名以A、B、S开始的员工信息。

```sql
SELECT *
FROM emp
WHERE ENAME REGEXP '[absg]$';
```

- \# 12. 找到名字长度为7个字符的员工信息。

```sql
SELECT *
FROM emp
WHERE length(ENAME) = 4;
```

- \# 13. 名字中不包含R字符的员工信息。

```sql
SELECT *
FROM emp
WHERE ENAME NOT LIKE '%r%';
```

- \# 14. 找出员工名字的前3个字符。

```sql
SELECT substr(ENAME, 1, 3)
FROM emp;
```

- \# 15. 将名字中A改为a。

```sql
SELECT replace(ENAME, 'A', 'a')
FROM emp;
```

- \# 16. 将员工的雇佣日期拖后10年。

```sql
SELECT
  HIREDATE,
  date_add(HIREDATE, INTERVAL 10 YEAR)
FROM emp;
```

- \# 17. 返回员工的详细信息并按姓名排序。

```sql
SELECT *
FROM emp
ORDER BY ENAME;
```

- \# 18. 返回员工的信息并按员工的工作年限降序排列。

```sql
SELECT *
FROM emp
ORDER BY HIREDATE;
```

- \# 19. 返回员工的信息并按工作降序工资升序排列。

```sql
SELECT *
FROM emp
ORDER BY JOB DESC, sal + ifnull(COMM, 0);
```

- \# 20. 返回员工的姓名、雇佣年份和月份并且按月份和雇佣日期排序。

```sql
SELECT
  ENAME,
  HIREDATE,
  extract(YEAR FROM HIREDATE),
  extract(MONTH FROM HIREDATE)
FROM emp
ORDER BY extract(MONTH FROM HIREDATE), extract(DAY FROM HIREDATE);
```

- \# 21. 计算员工的日薪(按30天)。

```sql
SELECT
  ename,
  round((SAL + ifnull(COMM, 0)) / 30, 2)
FROM emp;
```

- \# 22. 找出2月份雇佣的员工。

```sql
SELECT *
FROM emp
WHERE extract(MONTH FROM HIREDATE) = 2;
```

- \# 23. 至今为止，员工被雇佣的天数。

```sql
SELECT
  ENAME,
  HIREDATE,
  datediff(current_date, HIREDATE)
FROM emp;
```

- \# 24. 找出姓名中包含A的员工信息。

```sql
SELECT *
FROM emp
WHERE ENAME LIKE '%a%';
```

- \# 25. 计算出员工被雇佣了多少年、多少月、多少日。

```sql
SELECT
  ENAME,
  HIREDATE,
  date_format(from_days(datediff(current_date, HIREDATE)), '%y year %m month %d day')
FROM emp;

```

## PART II

- \# 1. 返回拥有员工的部门名、部门号。
- \# 2. 工资水平多于smith的员工信息。
- \# 3. 返回员工和所属经理的姓名。
- \# 4. 返回雇员的雇佣日期早于其经理雇佣日期的员工及其经理姓名。
- \# 5. 返回员工姓名及其所在的部门名称。
- \# 6. 返回从事clerk工作的员工姓名和所在部门名称。
- \# 7. 返回部门号及其本部门的最低工资。
- \# 8. 返回销售部sales所有员工的姓名。
- \# 9. 返回工资水平多于平均工资的员工。
- \# 10. 返回与SCOTT从事相同工作的员工。
- \# 11. 返回与30部门员工工资水平相同的员工姓名与工资。
- \# 12. 返回工资高于30部门所有员工工资水平的员工信息。
- \# 13. 返回部门号、部门名、部门所在位置及其每个部门的员工总数。
- \# 14. 返回员工的姓名、所在部门名及其工资。
- \# 15. 返回雇员表中不在同一部门但是从事相同工作的员工信息。
- \# 16. 返回员工的详细信息，包括部门名。
- \# 17. 返回员工工作及其从事此工作的最低工资。
- \# 18. 返回不同部门经理的最低工资。
- \# 19. 计算出员工的年薪，并且以年薪排序。
- \# 20. 返回工资处于第四级别的员工的姓名。