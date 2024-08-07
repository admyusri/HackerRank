# 004 - New Companies
## Problem

Amber's conglomerate corporation just acquired some new companies. Each of the companies follows this hierarchy:

*Founder -> Lead Manager -> Senior Manager -> Manager -> Employee*

Given the table schemas below, write a query to print the company_code, founder name, total number of lead managers, total number of senior managers, total number of managers, and total number of employees. Order your output by ascending company_code.

**Note:**
- The tables may contain duplicate records.
- The company_code is string, so the sorting should not be **numeric**. For example, if the company_codes are C_1, C_2, and C_10, then the ascending company_codes will be C_1, C_10, and C_2.

## INPUT FORMAT
The following tables contain company data:
- Company: The company_code is the code of the company and founder is the founder of the company.
  
| Column | Type    |
|--------|---------|
| company_code | string |
| founder	     | string |

- Lead_Manager: The lead_manager_code is the code of the lead manager, and the company_code is the code of the working company.
  
| Column | Type    |
|--------|---------|
| lead_manager_code | string |
| company_code    | string |

- Senior_Manager: The senior_manager_code is the code of the senior manager, the lead_manager_code is the code of its lead manager, and the company_code is the code of the working company.
  
| Column | Type    |
|--------|---------|
| senior_manager_code | string |
| lead_manager_code | string |
| company_code    | string |

- Manager: The manager_code is the code of the manager, the senior_manager_code is the code of its senior manager, the lead_manager_code is the code of its lead manager, and the company_code is the code of the working company.
  
| Column | Type    |
|--------|---------|
| manager_code | string |
| senior_manager_code | string |
| lead_manager_code | string |
| company_code    | string |

- Employee: The employee_code is the code of the employee, the manager_code is the code of its manager, the senior_manager_code is the code of its senior manager, the lead_manager_code is the code of its lead manager, and the company_code is the code of the working company.
  
| Column | Type    |
|--------|---------|
| employee_code | string |
| manager_code | string |
| senior_manager_code | string |
| lead_manager_code | string |
| company_code    | string |

## Sample Input

Company Table:
| company_code | founder    |
|--------|---------|
| C1 | Monika |
| C2	     | Samantha |

Lead_Manager Table:
| lead_manager_code | company_code    |
|--------|---------|
| LM1 | C1 |
| LM2 | C2 |

Senior_Manager Table:
| senior_manager_code | lead_manager_code |company_code    |
|--------|---------|---------|
|SM1 | LM1 | C1 |
|SM2 | LM1 | C1 |
|SM3 | LM2 | C2 |

Manager Table:
| manager_code | senior_manager_code | lead_manager_code |company_code    |
|--------|--------|---------|---------|
|M1 |SM1 | LM1 | C1 |
|M2 |SM3 | LM2 | C2 |
|M3 |SM3 | LM2 | C2 |

Employee Table:
|employee_code| manager_code | senior_manager_code | lead_manager_code |company_code    |
|--------|--------|--------|---------|---------|
|E1|M1 |SM1 | LM1 | C1 |
|E2|M1 |SM1 | LM1 | C1 |
|E3|M2 |SM3 | LM2 | C2 |
|E4|M3 |SM3 | LM2 | C2 |

## Sample Output

```
C1 Monika 1 2 1 2
C2 Samantha 1 1 2 2
```
## Explanation

In company C1, the only lead manager is LM1. There are two senior managers, SM1 and SM2, under LM1. There is one manager, M1, under senior manager SM1. There are two employees, E1 and E2, under manager M1.

In company C2, the only lead manager is LM2. There is one senior manager, SM3, under LM2. There are two managers, M2 and M3, under senior manager SM3. There is one employee, E3, under manager M2, and another employee, E4, under manager, M3.

## Solution
```sql
select c.company_code, c.founder,
       count(distinct l.lead_manager_code),
       count(distinct s.senior_manager_code),
       count(distinct m.manager_code),
       count(distinct e.employee_code)
from Company as c 
join Lead_Manager as l 
on c.company_code = l.company_code
join Senior_Manager as s
on l.lead_manager_code = s.lead_manager_code
join Manager as m 
on m.senior_manager_code = s.senior_manager_code
join Employee as e
on e.manager_code = m.manager_code
group by c.company_code, c.founder
order by c.company_code;
```

