- 👋 Hi, I’m DHRUV.RATHOD
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
DHRUV10-R/DHRUV10-R is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->

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