
#Sistemas de Informação Inteligentes
##Corretor Ortografico
###Lendo as Strings

```

package br.com.sii.visao;

import java.awt.EventQueue;
import java.awt.Font;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.util.ArrayList;

import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JOptionPane;
import javax.swing.JPanel;
import javax.swing.JTextField;
import javax.swing.border.EmptyBorder;

import br.com.sii.Ler;
import javax.swing.JList;
import javax.swing.event.AncestorListener;
import javax.swing.event.AncestorEvent;

public class Visao extends JFrame {

	private JPanel contentPane;
	private JTextField textFieldWord;
	private JTextField textFieldAnswer;

	/**
	 * 
	 * Launch the application.
	 * 
	 */
	public static void main(String[] args) {
		EventQueue.invokeLater(new Runnable() {
			public void run() {
				try {
					Visao frame = new Visao();
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
	public Visao() {
		setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		setBounds(100, 100, 559, 409);
		contentPane = new JPanel();
		contentPane.setBorder(new EmptyBorder(5, 5, 5, 5));
		setContentPane(contentPane);
		contentPane.setLayout(null);

		JLabel lblCorretorOrtografico = new JLabel("Corretor Ortografico");
		lblCorretorOrtografico.setFont(new Font("Tahoma", Font.PLAIN, 16));
		lblCorretorOrtografico.setBounds(214, 38, 183, 29);
		contentPane.add(lblCorretorOrtografico);

		textFieldWord = new JTextField();
		textFieldWord.setBounds(113, 98, 366, 53);
		contentPane.add(textFieldWord);
		textFieldWord.setColumns(10);

		JButton btnNewButtonVerifica = new JButton("Verificar Palavra\r\n");
		btnNewButtonVerifica.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {

				VisaoOpcoes visao2 = new VisaoOpcoes();
				String word, linha;
				try {
					word = textFieldWord.getText();

					ArrayList<String> opcoes = Ler.linha(word);

					if (opcoes.get(0).equals("ok")) {

						textFieldAnswer.setText("A palavra esta correta");

					} else {

						visao2.list.setListData(opcoes.toArray());
						visao2.textFieldAdd.setText(word);
						visao2.setVisible(true);
						dispose();

					}

				} catch (Exception e1) {
					JOptionPane.showMessageDialog(null, e1);
				}
			}
		});
		btnNewButtonVerifica.setFont(new Font("Tahoma", Font.PLAIN, 16));
		btnNewButtonVerifica.setBounds(214, 193, 151, 47);
		contentPane.add(btnNewButtonVerifica);

		textFieldAnswer = new JTextField();
		textFieldAnswer.setBounds(113, 289, 366, 53);
		contentPane.add(textFieldAnswer);
		textFieldAnswer.setColumns(10);
	}
}

```