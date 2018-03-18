# Avion
import sun.print.ServiceDialog;

import javax.swing.*;
import javax.swing.border.Border;
import javax.swing.border.TitledBorder;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class Practice1 extends  JFrame{

    //Declarar Button
    private  JButton buttonE;
    private  JButton buttonR;
    private  JButton buttonO;
    private  JButton buttonP;
    private  JButton buttonO2;
    private  JButton buttonB;

    public  Practice1() {

        super("AVIÓN");
        //Se crea el panel 1 para meter dentro contentPane
        JPanel pan1 = new JPanel();

        //Hacer uso de una imagen para el Avión
        JLabel Picture = new JLabel(new ImageIcon("src/plane.png"));

        //Creación de botones con sus posiciones
        buttonR = new JButton("Registrar Pasajero");
        pan1.add(buttonR);

        buttonE = new JButton("Eliminar Pasajero");
        pan1.add(buttonE);

        buttonB = new JButton("Buscar Pasajero");
        pan1.add(buttonB);

        buttonP = new JButton("Porcentaje Ocupación");
        pan1.add(buttonP);

        buttonO = new JButton("Opción 1");
        pan1.add(buttonO);

        buttonO2 = new JButton("Opción 2");
        pan1.add(buttonO2);

        //Dar color de fondo al panel 1
        pan1.setBackground(Color.GRAY);

        //Darle un Grid Layout de 2 filas con 3 columnas para los botones
        pan1.setLayout(new GridLayout(2,3));
        //Crear Un borde Al rededor de los botones creados
        pan1.setBorder(BorderFactory.createEmptyBorder(5,5,5,5));


        //Agregar Panel´s en ContentPane Principal
        getContentPane().add(pan1,BorderLayout.NORTH);
        getContentPane().add(Picture,BorderLayout.SOUTH);

        //crear botones de avión
        ActionListener oyenteBtnReg =new ActionButtons();
        ActionListener oyenteBtnElim = new ActionButtons();
        ActionListener oyenteBtnBusc = new ActionButtons();
        ActionListener oyenteBtnO = new ActionButtons();
        ActionListener oyenteBtnO2= new ActionButtons();
        ActionListener oyenteBtnPor = new ActionButtons();

        //vinculo de boton con click
        buttonR.addActionListener(oyenteBtnReg);
        buttonE.addActionListener(oyenteBtnElim);
        buttonB.addActionListener(oyenteBtnBusc);
        buttonO.addActionListener(oyenteBtnO);
        buttonO2.addActionListener(oyenteBtnO2);
        buttonP.addActionListener(oyenteBtnPor);

      }


      class ActionButtons implements ActionListener
      {
          @Override
          public void actionPerformed(ActionEvent e) {

              System.out.println("Presionaste el boton : "+((JButton)e.getSource()).getText());

              if (((JButton)e.getSource())== buttonB)
              {
                JOptionPane.showMessageDialog(null,"Buscar Pasajero","Buscar",JOptionPane.PLAIN_MESSAGE);
              }
              else if (((JButton)e.getSource())== buttonR)
              {
                  JOptionPane.showMessageDialog(null,"Registrar Pasajero","Registrar",JOptionPane.PLAIN_MESSAGE);
              }
              else if(((JButton)e.getSource())== buttonE)
              {
                  JOptionPane.showMessageDialog(null,"Eliminar Pasajero","Eliminar",JOptionPane.PLAIN_MESSAGE);
              }
              else if (((JButton)e.getSource())== buttonP)
              {
                  JOptionPane.showMessageDialog(null,"Porcentaje Ocupación","Porcentaje",JOptionPane.PLAIN_MESSAGE);
              }
              else if (((JButton)e.getSource())== buttonO)
              {
                  JOptionPane.showMessageDialog(null,"Opción 1","Option",JOptionPane.PLAIN_MESSAGE);
              }
              else if (((JButton)e.getSource())== buttonO2)
              {
                  JOptionPane.showMessageDialog(null,"Opción 2","Option",JOptionPane.PLAIN_MESSAGE);
              }
          }
      }

    public static void main (String[]args) {
        Practice1 prueba = new Practice1();
        prueba.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        prueba.pack();
        prueba.setLocation(500,30);
        prueba.setVisible(true);

    }


}

