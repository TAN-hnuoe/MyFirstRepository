# MyFirstRepository

#本方法是写死的，当 产生变化后就失效了
#封装创建数据库连接的过程
#简化数据库连接

import java.sql.Connection;
import java.sql.DriverManager;

public class Pgcon {
	
	static String driver= "oracle.jdbc.OracleDriver";
	static String url="jdbc:oracle:thin:@192.168.0.248:1521:orcl";
	static String username="qazhis";
	static String password="qazhis";
	
	public static Connection getConnection(){
		
		try {
			Class.forName(driver);
			Connection conn = DriverManager.getConnection(url, username,
					password);
			return conn;
		} catch (Exception e) {
			e.printStackTrace();
			throw new RuntimeException(e);
		}
	}

}
