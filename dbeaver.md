docker start mysql

docker exec -it mysql bash
mysql -u root -p


----------
show databases;
use mysql;
show tables;

create database multi
use multi;
show tables;

-----
CREATE TABLE STUDENTS (
	ID INT,
	NAME VARCHAR(100),
	PHONE CHAR(13),
	ADDRESS VARCHAR(1000)
);

SHOW TABLES;
DESC STUDENTS;

SELECT * FROM STUDENTS;
//*: everything을 의미

INSERT INTO STUDENTS VALUES(1, 'hyunjun', '010-1234-5678', '경기도 고양시');
//한줄한줄이 데이터 하나

ALTER TABLE STUDENTS ADD SUBJECTS VARCHAR(100);
//컬럼이 하나더 늘어남
//테이블 자체가 변경됨

DESC STUDENTS;
SELECT * FROM STUDENTS;
//SUBJECTS는 NULL값으로 채워짐

INSERT INTO STUDENTS VALUES(2, 'WON', '010-1111-2222', '서울시 강남구', 'WEB');

SELECT * FROM STUDENTS;

ALTER TABLE STUDENTS MODIFY SUBJECTS VARCHAR(1000);

DESC STUDENTS;
//테이블 정보보는법 

SELECT ID, NAME FROM STUDENTS;
//가공하는 과정을 거칠 수 있음

--STUDENTS테이블에서 ID가 2인 학생의 모든 정보를 출력하자.
SELECT * FROM STUDENTS WHERE ID=2;

SELECT ID, NAME FROM STUDENTS WHERE ID = 2;

SELECT COUNT(*) FROM STUDENTS;

DROP TABLE STUDENTS;
//지우는거

SHOW TABLES;
//DROP을 해서 테이블이 존재하지 않음

USE MYSQL;

DROP DATABASE MULTI;

SHOW DATABASES;
