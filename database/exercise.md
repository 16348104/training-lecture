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

## PART I

- \# 1. 查找部门30中员工的详细信息。

```sql
SELECT *
FROM scott.emp
WHERE DEPTNO = 30
```

- \# 2. 找出从事clerk工作的员工的编号、姓名、部门号。

```sql
SELECT
  EMPNO,
  ENAME,
  DEPTNO
FROM scott.emp
WHERE JOB = 'clerk'
```

- \# 3. 检索出奖金多于基本工资的员工信息。

```sql
SELECT *
FROM scott.emp
WHERE COMM > SAL
```

- \# 4. 检索出奖金多于基本工资60%的员工信息。

```sql
SELECT *
FROM scott.emp
WHERE COMM > SAL * 0.3
```

- \# 5. 希望看到10部门的经理或者20部门的职员(clerk)的信息。

```sql
SELECT *
FROM scott.emp
WHERE (DEPTNO = 10 AND JOB = 'manager') OR (DEPTNO = 20 AND JOB = 'clerk')
```

- \# 6. 找出10部门的经理、20部门的职员或者既不是经理也不是职员但是工资(基本工资 + 奖金)高于2000元的员工信息。

```sql
SELECT *
FROM scott.emp
WHERE (DEPTNO = 10 AND JOB = 'manager') OR (DEPTNO = 20 AND JOB = 'clerk') OR
      (JOB NOT IN ('manager', 'clerk') AND (sal + ifnull(COMM, 0)) > 2000)
```

- \# 7. 找出获得奖金的员工的工作。

```sql
SELECT DISTINCT job
FROM scott.emp
WHERE COMM > 0
```

- \# 8. 找出奖金少于100或者没有获得奖金的员工的信息。

```sql
SELECT *
FROM scott.emp
WHERE COMM < 100 OR COMM IS NULL
```

- \# 9. 查找员工雇佣日期中当月的最后一天雇佣的。

```sql
SELECT *
FROM scott.emp
WHERE HIREDATE = last_day(HIREDATE);
```

- \# 10. 检索出雇佣年限超过12年的员工信息。

```sql
SELECT *
FROM scott.emp
WHERE date_add(HIREDATE, INTERVAL 1 YEAR) > now();

UPDATE scott.emp
SET HIREDATE = '2014-11-22
WHERE ENAME = 'king';
```

- \# 11. 找出姓名以A、B、S开始的员工信息。

```sql
SELECT *
FROM scott.emp
WHERE substr(ENAME, 1, 1) IN ('a', 'b', 's');

SELECT *
FROM scott.emp;
```

- \# 12. 找到名字长度为7个字符的员工信息。

```sql
SELECT *
FROM scott.emp
WHERE length(ENAME) = 4;
```

- \# 13. 名字中不包含R字符的员工信息。

```sql
SELECT *
FROM scott.emp
WHERE ENAME NOT LIKE '%r%';
```

- \# 14. 找出员工名字的前3个字符。

```sql
SELECT substr(ename, 1, 3)
FROM scott.emp;
```

- \# 15. 将名字中A改为a。

```sql
SELECT replace(ename, 'A', 'a')
FROM scott.emp;
```

- \# 16. 将员工的雇佣日期拖后10年。

```sql
SELECT date_add(hiredate, INTERVAL 10 YEAR)
FROM scott.emp;
```

- \# 17. 返回员工的详细信息并按姓名排序。

```sql
SELECT *
FROM scott.emp
ORDER BY ENAME;
```

- \# 18. 返回员工的信息并按员工的工作年限降序排列。

```sql
SELECT *
FROM scott.emp
ORDER BY HIREDATE;
```

- \# 19. 返回员工的信息并按工作降序工资升序排列。

```sql
SELECT *
FROM scott.emp
ORDER BY JOB DESC, SAL + ifnull(COMM, 0);
```

- \# 20. 返回员工的姓名、雇佣年份和月份并且按月份和雇佣日期排序。

```sql
SELECT
  ename,
  hiredate,
  extract(YEAR FROM hiredate)  year,
  extract(MONTH FROM hiredate) month
FROM scott.emp
ORDER BY extract(MONTH FROM hiredate), HIREDATE;
```

- \# 21. 计算员工的日薪(按30天)。

```sql
SELECT round((sal + ifnull(COMM, 0)) / 30, 2)
FROM scott.emp;
```

- \# 22. 找出2月份雇佣的员工。

```sql
SELECT *
FROM scott.emp
WHERE extract(MONTH FROM HIREDATE) = 2;
```

- \# 23. 至今为止，员工被雇佣的天数。

```sql
SELECT datediff(now(), hiredate)
FROM scott.emp;
```

- \# 24. 找出姓名中包含A的员工信息。

```sql
SELECT *
FROM scott.emp
WHERE ENAME LIKE '%a%';
```

- \# 25. 计算出员工被雇佣了多少年、多少月、多少日。

```sql
# ?
```

## PART II

- \# 1. 返回拥有员工的部门名、部门号。

```sql
SELECT DISTINCT
  d.DEPTNO,
  d.DNAME
FROM scott.dept d, scott.emp e
WHERE e.DEPTNO = d.DEPTNO;
```

- \# 2. 工资水平多于smith的员工信息。

```sql
SELECT *
FROM scott.emp
WHERE sal + ifnull(COMM, 0) >
      (
        SELECT sal + ifnull(COMM, 0)
        FROM scott.emp
        WHERE ENAME = 'scott'
      );
```

- \# 3. 返回员工和所属经理的姓名。

```sql
SELECT
  e1.ENAME,
  e2.ENAME
FROM scott.emp e1, scott.emp e2
WHERE e1.MGR = e2.EMPNO;
```

- \# 4. 返回雇员的雇佣日期早于其经理雇佣日期的员工及其经理姓名。

```sql
SELECT
  e1.ENAME,
  e2.ENAME
FROM scott.emp e1, scott.emp e2
WHERE e1.MGR = e2.EMPNO AND e1.HIREDATE < e2.HIREDATE;
```

- \# 5. 返回员工姓名及其所在的部门名称。

```sql
SELECT
  e.ename,
  d.dname
FROM scott.emp e, scott.dept d
WHERE e.DEPTNO = d.DEPTNO;
```

- \# 6. 返回从事clerk工作的员工姓名和所在部门名称。

```sql
SELECT
  e.ename,
  d.dname
FROM scott.emp e, scott.dept d
WHERE e.DEPTNO = d.DEPTNO AND JOB = 'clerk';
```

- \# 7. 返回部门号及其本部门的最低工资。

```sql
SELECT
  deptno,
  min(sal + ifnull(comm, 0))
FROM scott.emp
GROUP BY DEPTNO;
```

- \# 8. 返回销售部sales所有员工的姓名。

```sql
SELECT e.ename
FROM scott.emp e, scott.dept d
WHERE e.DEPTNO = d.DEPTNO AND d.DNAME = 'sales';
```

- \# 9. 返回工资水平多于平均工资的员工。

```sql
SELECT *
FROM scott.emp
WHERE sal + ifnull(COMM, 0) >
      (
        SELECT avg(sal + ifnull(COMM, 0))
        FROM scott.emp
      );
```

- \# 10. 返回与SCOTT从事相同工作的员工。

```sql
SELECT *
FROM scott.emp
WHERE job =
      (
        SELECT job
        FROM scott.emp
        WHERE ENAME = 'scott'
      );
```

- \# 11. 返回与30部门员工工资水平相同的员工姓名与工资。

```sql
SELECT
  ENAME,
  sal + ifnull(COMM, 0)
FROM scott.emp
WHERE sal + ifnull(COMM, 0) = (
  SELECT avg(sal + ifnull(COMM, 0))
  FROM scott.emp
  WHERE DEPTNO = 30
);
```

- \# 12. 返回工资高于30部门所有员工工资水平的员工信息。

```sql
SELECT *
FROM scott.emp
WHERE sal + ifnull(COMM, 0) > (
  SELECT avg(sal + ifnull(COMM, 0))
  FROM scott.emp
  WHERE DEPTNO = 30
);
```

- \# 13. 返回部门号、部门名、部门所在位置及其每个部门的员工总数。

```sql
SELECT
  d.deptno,
  d.dname,
  d.loc,
  count(e.deptno)
FROM scott.emp e RIGHT OUTER JOIN scott.dept d
    ON e.DEPTNO = d.DEPTNO
GROUP BY e.DEPTNO;
```

- \# 14. 返回员工的姓名、所在部门名及其工资。

```sql
SELECT
  e.ename,
  d.dname,
  e.sal + ifnull(e.comm, 0)
FROM scott.emp e, scott.dept d
WHERE e.DEPTNO = d.DEPTNO;
```

- \# 15. 返回雇员表中不在同一部门但是从事相同工作的员工信息。

```sql
SELECT
  e1.ename,
  e1.job,
  e1.deptno,
  e2.ename,
  e2.job,
  e2.deptno
FROM scott.emp e1, scott.emp e2
WHERE e1.DEPTNO <> e2.DEPTNO AND e1.JOB = e2.JOB;
```

- \# 16. 返回员工的详细信息，包括部门名。

```sql
SELECT
  e.*,
  d.dname
FROM scott.emp e, scott.dept d
WHERE e.DEPTNO = d.DEPTNO;
```

- \# 17. 返回员工工作及其从事此工作的最低工资。

```sql
SELECT
  job,
  min(sal + ifnull(comm, 0))
FROM scott.emp
GROUP BY JOB;
```

- \# 18. 返回不同部门经理的最低工资。

```sql
SELECT min(sal + ifnull(comm, 0))
FROM scott.emp
WHERE JOB = 'manager'
GROUP BY DEPTNO;
```

- \# 19. 计算出员工的年薪，并且以年薪排序。

```sql
SELECT (sal + ifnull(comm, 0)) * 12
FROM scott.emp
ORDER BY 1;
```

- \# 20. 返回工资处于第四级别的员工的姓名。

```sql
SELECT
  e.ename,
  e.sal + ifnull(e.comm, 0),
  s.LOSAL,
  s.HISAL
FROM scott.emp e, scott.salgrade s
WHERE e.sal + ifnull(e.comm, 0) BETWEEN s.LOSAL AND s.HISAL AND s.GRADE = 4;
```
