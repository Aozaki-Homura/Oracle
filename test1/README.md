# test1
## 查询1:
```SQL
SELECT d.department_name，count(e.job_id)as "部门总人数"，
avg(e.salary)as "平均工资"
from hr.departments d，hr.employees e
where d.department_id = e.department_id
and d.department_name in ('IT'，'Sales')
GROUP BY department_name;
```
- 分析：该语句的目的是先通过部门名得到部门id，通过部门id找到对应的员工，再计算人数和工资，最后通过部门名称排序。
## 查询2：
```SQL
SELECT d.department_name，count(e.job_id)as "部门总人数"，
avg(e.salary)as "平均工资"
FROM hr.departments d，hr.employees e
WHERE d.department_id = e.department_id
GROUP BY department_name
HAVING d.department_name in ('IT'，'Sales');
```
- 分析：该语句先查询出每个部门的员工，人数和平均工资，再按部门名排序，然后找出it和sales的部门。
## 我的查询：
```SQL
SELECT d.department_name as"部门名称",e.phone_number as"电话号码",
e.salary as"工资"
from hr.departments d,hr.employees e
where d.department_id = e.department_id
and e.employee_id in ('100','101')
ORDER BY employee_id;
- 分析:我的查询语句是查找到id为100和101的员工，再找到他们的电话号码，部门名称以及工资。
