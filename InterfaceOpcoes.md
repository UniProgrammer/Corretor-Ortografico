#Sistemas de Informação Inteligentes
##Corretor Ortografico
###Lendo as Strings

```

package br.com.sii.visao;

import java.awt.EventQueue;
import java.awt.Font;
import java.util.ArrayList;

import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JList;
import javax.swing.JPanel;
import javax.swing.border.EmptyBorder;

import br.com.sii.Escrever;

import java.awt.event.ActionListener;
import java.awt.event.ActionEvent;
import javax.swing.JTextField;

public class VisaoOpcoes extends JFrame {

	
	private JPanel contentPane;
	JList list;
	JTextField textFieldAdd;

	/**
	 * Launch the application.
	 */
	public void setList(ArrayList<String> list){
		this.list.setListData(list.toArray());
	}
	public static void main(String[] args) {
		EventQueue.invokeLater(new Runnable() {
			public void run() {
				try {
					VisaoOpcoes frame = new VisaoOpcoes();
					frame.setVisible(true);
				} catch (Exception e) {
					e.printStackTrace();
				}
			}
		});
	}

	/**
	 * Create the frame.
	 */
	public VisaoOpcoes() {
		setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		setBounds(100, 100, 558, 400);
		contentPane = new JPanel();
		contentPane.setBorder(new EmptyBorder(5, 5, 5, 5));
		setContentPane(contentPane);
		contentPane.setLayout(null);
		
		list = new JList();
		list.setBounds(10, 179, 522, 171);
		contentPane.add(list);
		
		JButton btnAdicionar = new JButton("adicionar");
		btnAdicionar.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent arg0) {
				Escrever.escrever(textFieldAdd.getText());
				new Visao().setVisible(true);
				dispose();
			}
		});
		btnAdicionar.setFont(new Font("Tahoma", Font.PLAIN, 18));
		btnAdicionar.setBounds(316, 26, 161, 43);
		contentPane.add(btnAdicionar);
		
		JLabel lblVoceQuisDizer = new JLabel("voce quis dizer: ");
		lblVoceQuisDizer.setFont(new Font("Tahoma", Font.PLAIN, 18));
		lblVoceQuisDizer.setBounds(174, 121, 161, 25);
		contentPane.add(lblVoceQuisDizer);
		
		textFieldAdd = new JTextField();
		textFieldAdd.setBounds(43, 26, 193, 43);
		contentPane.add(textFieldAdd);
		textFieldAdd.setColumns(10);
	}
}


```