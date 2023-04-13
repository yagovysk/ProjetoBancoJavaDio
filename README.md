# ProjetoBancoJavaDio
um programa para bancos feito em Java
pega do usuario a agencia da qual o banco é,
numero do cadastro do usuario e por fim mostra seu saldo,
isso é a primeira parte do código, a segunda é fazer
transferencia entre as contas, saber qual está transferindo,
calcular o valor de saida da conta X, para o valor de entrada na conta Y.
public abstract class Conta implements IConta{
	protected static final int AGENCIA_PADRAO = 1;

	private static int SEQUENCIAL = 1;

	protected int agencia;
	protected int numero;
	protected double saldo;
	
	public Conta(){
	agencia = Conta.AGENCIA_PADRAO
	numero = SEQUENCIAL++;
	}

	public void sacar(double valor){
		saldo = saldo - valor;
	}
	
	public void depositar(double valor){
		saldo = saldo + valor;
	}

	public void transferir(double valor, Conta contaDestino){
		this.sacar(valor);
		contaDestino.depositar(valor);
	}

	public int getAgencia(){
		return agencia;
	}

	public int getNumero(){
		return numero;
	}
	protected void imprimirInfosComuns(){
	System.out.println(String.format("Agencia: %d", agencia));
	System.out.println(String.format("Numero: %d", numero));
	System.out.println(String.format("Saldo: %.2f", saldo));
	}
}
