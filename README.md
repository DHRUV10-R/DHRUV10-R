- 👋 Hi, I’m DHRUV.RATHOD
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
DHRUV10-R/DHRUV10-R is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->

-----------------------1-----------------------


package handlingexce;
import javax.swing.*;
import javax.swing.event.*;
import java.awt.*;

class List1 extends JFrame implements ListSelectionListener{

    JList lst1;
    JPanel p1;
    Color clr[]={Color.RED,Color.GREEN,Color.BLUE};
    List1()
    {
        setTitle("ListBox Demo");
        setSize(400,400);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        
        setVisible(true);
        String str[]={"RED","GREEN","BLUE"};
        
        lst1=new JList (str);
        p1=new JPanel();
        lst1.setBounds(100,200,50,40);
        p1.add(lst1);
        add(p1,BorderLayout.CENTER);
        p1.setBackground(Color.RED);
        lst1.addListSelectionListener(this);
    }
    public void valueChanged(ListSelectionEvent e)
    {
        p1.setBackground(clr[lst1.getSelectedIndex()]);
        
    }
    public static void main(String args[]) {
        new List1();
    }
}

-------------------------2---------------------


package handlingexce;

import java.sql.*;
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

public class Jdbcswingp2 extends JFrame implements ActionListener 
    

 
{
    JLabel lblRollno,lblName,lblAddr;
    JTextField txtRollno,txtName,txtAddr;
    JButton btnInsert,btnDisplay;
    JTextArea txt1;
    JPanel p1,p2;

    Connection con;
    Statement s;
    PreparedStatement pst;
    ResultSet rs;
    Jdbcswingp2()
    {
	setTitle("JDBC using Swing");
	setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
	setSize(300,300);
	setVisible(true);

	lblRollno=new JLabel("Enter RollNo");
        txtRollno=new JTextField(20);
        lblName=new JLabel("Enter Name");
        txtName=new JTextField(20);
        lblAddr=new JLabel("Enter Address");
        txtAddr=new JTextField(20);
		
	btnInsert=new JButton("  Insert  ");
        btnDisplay=new JButton("  Display  ");
	
        txt1=new JTextArea(80,20);

        p1=new JPanel();
        p1.setLayout(new GridLayout(4,2));
	p2=new JPanel();
        
        p1.add(lblRollno);
	p1.add(txtRollno);
        p1.add(lblName);
	p1.add(txtName);
        p1.add(lblAddr);
	p1.add(txtAddr);
        p1.add(btnInsert);
        p1.add(btnDisplay);
        
	p2.add(txt1);

	add(p1,BorderLayout.NORTH);
        add(p2,BorderLayout.CENTER);
        
        btnInsert.addActionListener(this);
	btnDisplay.addActionListener(this);
    }
    public void actionPerformed(ActionEvent ae)
    {
	try
	{
            Class.forName("com.mysql.cj.jdbc.Driver");
	}
	catch(ClassNotFoundException ce)
	{
            System.out.println(ce);
	}
        if(ae.getSource()==btnInsert)
        {
            String str1,str2,str3;
            int r;
            str1=txtRollno.getText();
            str2=txtName.getText();
            str3=txtAddr.getText();
            r=Integer.parseInt(str1);
            try 
            {
                String url="jdbc:mysql://localhost:3305/sycs34";
                con=DriverManager.getConnection(url,"root","123456");
                s=con.createStatement();
                
                String q="insert into Student values(?,?,?)";
                
                pst=con.prepareStatement(q);
                pst.setInt(1, r);
                pst.setString(2, str2);
                pst.setString(3, str3);
                
                pst.executeUpdate();
                
                JOptionPane.showMessageDialog(this,"Record inserted properly");
                txtRollno.setText("");
                txtName.setText("");
                txtAddr.setText("");
            } 
            catch(SQLException e)
            {
                
            }
        }
	if(ae.getSource()==btnDisplay)
	{
            try
            {
		String url="jdbc:mysql://localhost:3305/sycs34";
	 	con=DriverManager.getConnection(url,"root","123456");
		s=con.createStatement();
		
                txt1.setText("");
		rs=s.executeQuery("select * from student");
		txt1.append("ROLL_NO\tNAME\tADDRESS\n");
                while(rs.next())
                {
                    txt1.append(rs.getInt(1)+"\t"+rs.getString(2)+"\t"+rs.getString(3)+"\n");
                }
                    rs.close();
            } 
            catch(SQLException ce)
            {
            	System.out.println(ce);
            }
	}
    }
    public static void main(final String [] args)
    {
	new Jdbcswingp2();
    }
}

-------------------------3---------------------


package handlingexce;
import javax.swing.JOptionPane;


public class Loginform  extends javax.swing.JFrame
{
    public Loginform(){
        init Components();
    }
    private void btnsubmitActionPerformed(java.awt.event.ActionEvent evt){
        chan[] txt=txtpwd.getPassword();
        String str1=txtname.getText();
        String str2= new String(txt);
             if(str1.equals("sycs")&&str2.equals("abc12"))
             {
                JOptionPane.showMessageDialog(null, "Login Successful","Welcome",1);
             }
             else{
                  JOptionPane.showMessageDialog(null, "Login UnSuccessful","Sorry",2);
                  txtname.setText(" ")
                  txtpwd.setText(" ")
             }
    }
    private void btnsubmitActionPerformed(java.awt.event.ActionEvent evt){
        System.exit(0);
    }
}


-------------------------4---------------------


import java.util.Scanner;

public class Exception3 {
    public static void main(String[] args)
    {
        try
        {
            int a[]=new int[5];
            a[10]=30/3;
                       
        }
        catch(ArithmeticException e)
        {
            System.out.println("Arithmetic Exception occurs");
        }
        catch(ArrayIndexOutOfBoundsException e)
        {
            System.out.println("ArrayIndexOutOfBounds Exception occurs");
        }
        catch(Exception e)
        {
            System.out.println("Parent Exception occurs");
        }
        System.out.println("REST OF THE CODE.......!");
    }
    
}
