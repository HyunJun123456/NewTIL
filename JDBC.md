JDBC(Java DataBase Connectivity)
자바에서 데이터베이스에 접근할 수 있게 해주는 Programming API

JDBC 사용 객체
DriverManager
데이터 원본에 JDBC드라이버를 통하여 커넥션을 만드는 역할
Class.forName() 메소드를 통해 생성되며 반드시 예외처리를 해야 함
직접 객체 생성이 불가능하고 getConnection() 메소드를 사용하여 객체 생성 가능

Connection
특정 데이터 원본과 연결된 커넥션을 나타내며 Statement 객체를 생성할 때도
Connection 객체를 사용하여 createStatement() 메소드를 호출하여 생성
SQL 문장을 실행시키기 전에 우선 Connection 객체가 있어야 함

Statement
Connection 객체에 의해 프로그램에 리턴되는 객체에 의해 구현되는 일종의 메소드 집합 정의
Connection클래스의 createStatement() 메소드를 호출하여 얻어지며 
생성된 Statement객체로 질의문장을 String객체에 담아 인자로 전달하여
executeQuery() 메소드를 호출하여 SQL 질의 수행
