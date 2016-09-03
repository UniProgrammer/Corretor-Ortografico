
#Sistemas de Informação Inteligentes
##Corretor Ortografico
###Lendo as Strings

```

package br.com.sii;

import java.io.BufferedReader;
import java.io.File;
import java.io.FileReader;
import java.io.IOException;
import java.util.Scanner;

public class Ler {

	static Scanner input = new Scanner(System.in);

	public static void main(String[] args) {

		System.out.println("Digete uma palavra: ");
		String word = input.next();

		ler(word);
	}

	private static void ler(String word) {
		File dir = new File("C:\\Users\\KLEBER\\Desktop\\apps\\03_corretorOrtografico\\"
				+ "corretor\\src\\br\\com\\teste2\\arquivo");
		File arq = new File(dir, "User.txt");

		try {

			// Indicamos o arquivo que será lido

			FileReader fileReader = new FileReader(arq);

			// Criamos o objeto bufferReader que nos
			// oferece o método de leitura readLine()

			BufferedReader bufferedReader = new BufferedReader(fileReader);

			// String que irá receber cada linha do arquivo

			String linha = "";

			// Fazemos um loop linha a linha no arquivo,

			while ((linha = bufferedReader.readLine()) != null) {

				// Aqui imprimimos a linha
				System.out.println(linha);

			}

			fileReader.close();
			bufferedReader.close();
		} catch (IOException e) {
			e.printStackTrace();
		}
	}

}


```
