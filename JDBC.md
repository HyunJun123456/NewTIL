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

예시
try{
    String query = “ SELECT ID, LAST_NAME FROM EMP “;
	//query문 만들어주기
    stmt = conn.createStatement();
	//Statement객체 생성
    rset = stmt.executeQuery(query);
	//Stataement 객체 실행
} catch(SQLException){
    e.printStackTrace();
}
	//finally로 close 해줘야 함

PreparedStatement
Connection 객체의 preparedStatement() 메소드를 사용하여 객체 생성
SQL문장이 미리 컴파일 되고 실행 시간동안 인수 값을 위한 공간을 확보한다는 점에서
Statement와 다름

예시
try{
    String query = “ INSERT INTO MEMBER VALUES(?,?) “;
    pstm = conn.preparedStatement(query);
    pstm.setString(1, id);
    pstm.setString(2, password);
} catch(SQLException e){
    e.printStackTrace();
}
ResultSet
SELECT문을 사용한 질의 성공 시 Result Set 반환
SQL질의에 의해 생성된 테이블을 담고 있으며 커서(cursor)로 특정 행에 대한 참조 조작


Driver 등록 -> DBMS 연결 -> Statement 생성 -> SQL 전송 -> 결과 받기 ->닫기(객체 반환)

Driver 등록
DriverManager에 해당 DBMS Driver 등록
Class.forName(“com.mysql.jdbc.Driver”);
ex)다른 DB설정
Oracle: Class.forName(“oracle.jdbc.driver.OracleDriver”);
반드시 ClassNotFoundException 처리를 해야 함

DBMS 연결
해당 Driver로부터 Connection instance 획득
public static Connection getConnection(String url, String user, String password) throws SQLException
Connection conn = DriverManager.getConnection(“jdbc:mysql://localhost/multi”, ”root”, ”1234”);
반드시 SQLException 처리를 해야 함

Statement 생성
Connection instance로부터 Statement instance 획득
Statement stmt = conn.createStatement();
반드시 SQLException 처리를 해야 함

SQL 전송 -> 결과 받기
Statement method를 이용하여 SQL문 실행
실행결과를 ResultSet(Select) 혹은 int형 변수(DML)로 받아서 처리
String query = “ SELECT ID,, LAST_NAME FROM EMP “;
ResultSet rs = stmt.executeQuery(query);

while(rs.next()){
    System.out.println(rs.getString(“ID”) + “\t” +
    rs.getString(2));
}

String query = “ UPDATE EMP SET LAST_NAME = “KIM”
		+” WHERE ID = ‘10000’”;
int result = stmt.executeUpdate(query);
반드시 SQLException 처리를 해야 함

닫기(객체 반환)
Connection instance로부터 Statement instance 획득
rs.close(); //ResultSet 사용한 경우 반납처리
stmt.close();
con.close();
반드시 SQLException 처리를 해야 함
