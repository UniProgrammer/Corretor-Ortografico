
#Sistemas de Informação Inteligentes
##Corretor Ortografico
###Lendo as Strings

```

package br.com.sii;

import java.io.BufferedReader;
import java.io.File;
import java.io.FileReader;
import java.io.IOException;
import java.util.ArrayList;

import javax.swing.SingleSelectionModel;

public class Ler {
	public static void main(String[] args) throws IOException {

		ArrayList<String> a = new ArrayList<>();

		a = linha("Informaçãi");
		for (int i = 0; i < a.size(); i++) {
			System.out.println(a.get(i));
		}
	}

	public static ArrayList<String> linha(String word) throws IOException {
		File dir = new File("C:\\Users\\KLEBER\\Desktop\\apps\\03_corretorOrtografico\\"
				+ "corretor\\src\\br\\com\\teste2\\arquivo");
		File arq = new File(dir, "User.txt");

		// Indicamos o arquivo que será lido

		FileReader fileReader = new FileReader(arq);

		// Criamos o objeto bufferReader que nos
		// oferece o método de leitura readLine()

		BufferedReader bufferedReader = new BufferedReader(fileReader);

		// String que irá receber cada linha do arquivo

		String linha = "";
		String linhaArray[];
		ArrayList<String> linhaArray2 = new ArrayList<>();

		// Fazemos um loop linha a linha no arquivo,

		while ((linha = bufferedReader.readLine()) != null) {
			linhaArray = linha.split(" ");
			int d = 0;

			forExterno: for (int i = 0; i < linhaArray.length; i++) {

				if (word.equals(linhaArray[i])) {

					linhaArray2.clear();
					linhaArray2.add(0, "ok");
					return linhaArray2;
				}
				if (word.length() == linhaArray[i].length()) {
					if (word.charAt(0) == linhaArray[i].charAt(0))
						for (int i1 = 0; i1 < word.length(); i1++) {
							if (word.charAt(i1) == linhaArray[i].charAt(i1)) {
								d++;
							}
						}
					if (linhaArray[i].length() * 0.7 < d + 0.9) {
						linhaArray2.add(linhaArray[i]);
					}
					d = 0;
				}

			}

		}
		fileReader.close();
		bufferedReader.close();
		return linhaArray2;
	}

}



```
