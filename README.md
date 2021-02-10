# LG2Arvore

Aluna Giulia Santana dos Anjos SP3025918

TEMA Arvores 

Codigos videoaula 2 e 3


//1- ELEMENTO//

package Lg2Arvore;

public class Elemento<TIPO> {
  private TIPO valor;
  private Elemento<TIPO> esquerda;
  private Elemento<TIPO> direita;
  
  
  public Elemento(TIPO novoValor) {
	  this.valor = novoValor;
	  this.esquerda = null;
	  this.direita = null;
  }

  public TIPO getValor() {
	return valor;
}

  public void setValor(TIPO valor) {
	this.valor = valor;
}

  public Elemento<TIPO> getEsquerda() {
	return esquerda;
}

  public void setEsquerda(Elemento<TIPO> esquerda) {
	this.esquerda = esquerda;
}

  public Elemento<TIPO> getDireita() {
	return direita;
}

  public void setDireita(Elemento<TIPO> direita) {
	this.direita = direita;
}
  
  
}

//2-ARVORE//

package Lg2Arvore;

public class Arvore<TIPO extends Comparable> {
	 private Elemento<TIPO> raiz;
	 
	 public Arvore() {
		 this.raiz = null;
	 }
	 
	 public void adicionar(TIPO valor) {
		 Elemento<TIPO> novoElemento = new Elemento<TIPO>(valor);
		 if (raiz == null) {
			 this.raiz = novoElemento;
		 }
		 else {
			 Elemento<TIPO> atual = this.raiz;
			 while(true) {
				 if(novoElemento.getValor().compareTo(atual.getValor()) == -1) {
					if(atual.getEsquerda() != null) {
					 atual = atual.getEsquerda(); 
				 }
				 else {
					 atual.setEsquerda(novoElemento);
					 break;
				 }
			 }
			 else {
				 if(atual.getDireita() != null) {
					 atual = atual.getDireita(); 
				 }
				 else {
					 atual.setDireita(novoElemento);
					 break;
				 }
			 }
		 }
	 }
	 
	 }
	 
	 public Elemento<TIPO> getRaiz() {
		return raiz;
	}

	 
	public void emOrdem(Elemento<TIPO> atual) {
		 if(atual != null) {
		 emOrdem(atual.getEsquerda());
		 System.out.println(atual.getValor());
		 emOrdem(atual.getDireita());
	 }
	}
		 
	 public void preOrdem(Elemento<TIPO> atual) {
		if(atual != null) {
		System.out.println(atual.getValor());
		preOrdem(atual.getEsquerda());
		preOrdem(atual.getDireita());
		 }
	 }
	 
	 public void posOrdem(Elemento<TIPO> atual) {
		if(atual != null) {
		posOrdem(atual.getEsquerda());
		posOrdem(atual.getDireita());
		System.out.println(atual.getValor());
	 
		}
	 }
}

  //3-ARVORE BINARIA CODIGO//
  
  package Lg2Arvore;

public class ArvoreBinariaCodigo {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		Arvore<Integer> arvore = new Arvore<Integer>();
		arvore.adicionar(10);
		arvore.adicionar(8);
		arvore.adicionar(5);
		arvore.adicionar(9);
		arvore.adicionar(7);
		arvore.adicionar(18);
		arvore.adicionar(13);
		arvore.adicionar(20);
		System.out.println("\n\nEm ordem");
		arvore.emOrdem(arvore.getRaiz());
		
		System.out.println("\n\nPré-ordem");
		arvore.preOrdem(arvore.getRaiz());
		
		System.out.println("\n\nPós-ordem");
		arvore.posOrdem(arvore.getRaiz());
		
	}

}
