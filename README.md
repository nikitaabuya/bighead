# bighead
package group_project;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;

/**
 *
 * @author Nikita Abuya
 */
public class Group_project {
     public static void main(String[] args) {
      
}
    private Connection connection;
    public Connection connect(){
        try{
            Class.forName("com.mysql.jdbc.Driver");
            System.out.println("Connection success");
        }
        catch(ClassNotFoundException cnfe){
            System.out.println("Connection failed"+cnfe);
        }
        String url = "jdbc:mysql://localhost:3306/oop?zeroDateTimeBehavior=convertToNull";
        try{
            connection = (Connection) DriverManager.getConnection(url,"root","");
            System.out.println("Database Connected");
        }
        catch(SQLException se){
            System.out.println("No Database Connected");
        }
        return connection;
    }
}
