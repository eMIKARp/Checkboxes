# Checkboxes
a piece of code that displays a frame with checkboxes on it which change the font of displaied sentence
    
    package checkboxes;

    import javax.swing.*;
    import java.awt.*;
    import java.awt.event.*;

    public class Main extends JFrame{

    public Main()
    {
        initComponents();
    }
    
    public void initComponents()
    {
        this.setTitle("Pola wyboru");
        this.setBounds(200,200,400,200);  
        
        etykieta.setFont(new Font("Monospaced", Font.PLAIN, 20));
                
        ActionListener sluchacz = new CheckBoxHandler();
        pogrubiony.addActionListener(sluchacz);
        pochylony.addActionListener(sluchacz);
        
        panel1.add(pogrubiony);
        panel1.add(pochylony);
        
        panel2.add(etykieta);
        
        this.getContentPane().add(panel1, BorderLayout.NORTH);
        this.getContentPane().add(panel2, BorderLayout.CENTER);
             
        this.setDefaultCloseOperation(3);
    }
    
        
      JPanel panel1 = new JPanel();
      JPanel panel2 = new JPanel();
      JCheckBox pogrubiony = new JCheckBox("Pogrubiony");
      JCheckBox pochylony = new JCheckBox("Pochylony");

      
      JLabel etykieta = new JLabel("Przykładowe zdanie");
    
    public class CheckBoxHandler implements ActionListener
    {

        @Override
        public void actionPerformed(ActionEvent e) {
            
            
            int style = Font.PLAIN;
            if (pogrubiony.isSelected()) style += Font.BOLD;
            if (pochylony.isSelected()) style += Font.ITALIC;
                    
            etykieta.setFont(new Font(etykieta.getFont().getFamily(), style, etykieta.getFont().getSize()));     
                    
          
        }
        
    }

    public static void main(String[] args) {
        new  Main().setVisible(true);
        
    }
    
    }
