
#Sistemas de Informação Inteligentes
##Corretor Ortografico
###Lendo as Strings

```

package br.com.sii;

import java.io.File;
import java.io.FileWriter;
import java.io.IOException;
import java.io.PrintWriter;

import br.com.teste2.User;

public class Escrever {
	public static void escrever(String add) {
		File dir = new File("C:\\Users\\KLEBER\\Desktop\\apps\\03_corretorOrtografico\\"
				+ "corretor\\src\\br\\com\\teste2\\arquivo");
		File arq = new File(dir, "User.txt");

		try {

			// neste ponto criamos o arquivo fisicamente
			arq.createNewFile();

			// Devemos passar no construtor do FileWriter qual arquivo
			// vamos manipular.
			// Esse construtor aceita dois tipos de parâmetros,
			// File ou String.
			// O parâmetro true indica que reescrevemos no arquivo
			// sem apagar o que já existe.
			// O false apagaria o conteúdo do arquivo e escreveria
			// o novo conteúdo.
			// Se não usar o 2° parâmetro, ele por padrão será false.
			// O mais importante, essa linha abre o fluxo do arquivo
			FileWriter fileWriter = new FileWriter(arq, true);

			// Agora vamos usar a classe PrintWriter para escrever
			// fisicamente no arquivo.
			// Precisamos passar o objeto FileReader em seu construtor
			PrintWriter printWriter = new PrintWriter(fileWriter);

			// Agora vamos escrever no arquivo com o método println(),
			// que nos permite escrever linha a linha no arquivo

			printWriter.println(add);

			// o método flush libera a escrita no arquivo
			printWriter.flush();

			// No final precisamos fechar o arquivo
			printWriter.close();

		} catch (IOException e) {
			e.printStackTrace();
		}

	}
}

```
