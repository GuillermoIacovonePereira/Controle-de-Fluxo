# Exemplo de um Controle de Fluxo

### Classe Contador
~~~
import java.util.Scanner;

public class Contador {
	public static void main(String[] args) {
        
        //Capturando o input do usuário
	Scanner terminal = new Scanner(System.in);
	System.out.println("Digite o primeiro parâmetro");
	int parametroUm = terminal.nextInt();
	System.out.println("Digite o segundo parâmetro");
	int parametroDois = terminal.nextInt();
		
	try {
	//Chamando o método contendo a lógica de contagem
	contar(parametroUm, parametroDois);
		
	}catch (ParametrosInvalidosException exception) {
	//Imprimindo a mensagem de erro caso o parametroDois for menor que o parametroUm
	System.out.println("O segundo parâmetro deve ser maior que o primeiro");
	}
}

	static void contar(int parametroUm, int parametroDois ) throws ParametrosInvalidosException {

	//Validando se parametroUm é MAIOR que parametroDois e lançando a exceção
	if(parametroUm > parametroDois){
            throw new ParametrosInvalidosException();
        }else{
            int contagem = parametroDois - parametroUm;
	    //Realizando o for para imprimir os números com base na variável contagem
            for(int i = 0; i < contagem; i++){
                System.out.println("Imprindo n° " + (i+1));
            }
        }
    }
}
~~~

### Classe ParametrosInvalidosException

~~~
public class ParametrosInvalidosException extends Exception {
    //Exceção personalizada
}
~~~
