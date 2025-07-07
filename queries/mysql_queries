CREATE DATABASE employees_db
USE employees_db

SELECT * FROM employee_data

SELECT employee_id, COUNT(*) AS count
FROM employee_data
GROUP BY employee_id
HAVING count > 1;


SELECT * FROM employee_data WHERE first_name IS NULL OR first_name = '';

SET SQL_SAFE_UPDATES = 0;

UPDATE employee_data
SET date_of_exit = 'PRESENT'
WHERE date_of_exit IS NULL;

SET SQL_SAFE_UPDATES = 1;

-- Aadhaar Validation
SELECT 
  employee_id,
  first_name,
  last_name,
  aadhaar_number,
  pan_number,
  department_id,
  date_of_joining,
  date_of_exit,
  'Invalid' AS status,
  'Aadhaar Error' AS serror_flag,
  CASE
    WHEN aadhaar_number REGEXP '[A-Za-z]' THEN 'Alphanumeric'
    WHEN LENGTH(REPLACE(REPLACE(aadhaar_number, ' ', ''), '-', '')) != 12 THEN 'Incorrect digit count'
    ELSE 'Valid'
  END AS comments
FROM employee_data
WHERE 
  aadhaar_number REGEXP '[A-Za-z]'
  OR LENGTH(REPLACE(REPLACE(aadhaar_number, ' ', ''), '-', '')) != 12

UNION ALL

-- PAN Validation
SELECT 
  employee_id,
  first_name,
  last_name,
  aadhaar_number,
  pan_number,
  department_id,
  date_of_joining,
  date_of_exit,
  'Invalid' AS status,
  'PAN Error' AS serror_flag,
  CASE
    WHEN CHAR_LENGTH(pan_number) != 10 AND pan_number NOT REGEXP '^[A-Z]{5}[0-9]{4}[A-Z]$' 
      THEN 'Length and Format Incorrect'
    WHEN pan_number NOT REGEXP '^[A-Z]{5}[0-9]{4}[A-Z]$' 
      THEN 'Format not correct'
    WHEN SUBSTRING(pan_number, 5, 1) != UPPER(
         CASE 
           WHEN last_name IS NOT NULL AND last_name != '' THEN LEFT(last_name, 1)
           ELSE LEFT(first_name, 1)
         END) 
      THEN '5th character not matching'
    ELSE 'Valid'
  END AS comments
FROM employee_data
WHERE 
  CHAR_LENGTH(pan_number) != 10 
  OR pan_number NOT REGEXP '^[A-Z]{5}[0-9]{4}[A-Z]$'
  OR SUBSTRING(pan_number, 5, 1) != UPPER(
         CASE 
           WHEN last_name IS NOT NULL AND last_name != '' THEN LEFT(last_name, 1)
           ELSE LEFT(first_name, 1)
         END)

ORDER BY employee_id, FIELD(serror_flag, 'Aadhaar Error', 'PAN Error');



-- employee_data and departments_table
SELECT e.employee_id, e.first_name, e.last_name,
	    d.department_id, d.department_name
FROM employee_data e
INNER JOIN
departments_table d
ON e.department_id = d.department_id;


SELECT *
FROM departments_table
GROUP BY department_id
HAVING COUNT(*) > 1;


-- employee_data and show attendance_id with check_in_time and check_out_time
SELECT e.employee_id, e.first_name, e.last_name,
	     a.check_in_time, a.check_out_time
FROM employee_data e
INNER JOIN
attendance_table a
ON e.employee_id = a.employee_id;


-- employee_data and show over_time_record with ot_date and hours_worked
SELECT e.employee_id, e.first_name, e.last_name,
	     o.ot_date, o.hours_worked
FROM employee_data e
INNER JOIN
overtime_records o
ON e.employee_id = o.employee_id;

SELECT department_id,COUNT(*) FROM employee_data GROUP BY department_id;

SELECT gender FROM employee_data where gender = 'Male'

SELECT gender,COUNT(*) FROM employee_data GROUP BY gender;
