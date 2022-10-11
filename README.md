# Aula de Java
package jogo;

import java.util.Scanner;

public class Jogo {
 public static void main(String[] args) {
     String nomePersonagem;
     int energiaPersonagem;
     
     Scanner teclado = new Scanner(System.in);
     
     System.out.println("Digite o nome do personagem: ");
     nomePersonagem = teclado.nextLine();
     
     Scanner teclado2 = new Scanner(System.in);
     
     System.out.println("Digite a energia do personagem: ");
     energiaPersonagem = teclado2.nextInt();
     
     Personagens criando = new Personagens(nomePersonagem, energiaPersonagem);
     
//     criando.nome = "Cassio Ramos";
//     criando.energia = 10;
//     criando.fome = 3;
//     criando.sono = 5;
     
     criando.cacar();
     criando.comer();
     criando.dormir(); 
    } 
}
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++


package jogo;
public class Personagens {
    String nome;
    int energia, fome, sono;
    
    Personagens(String nome, int energia){
        this.nome = nome;
        this.energia = energia;
    }
    
    
    
    void cacar(){
        if (energia < 2){
            System.out.println(nome + " Não consegue caçar");
        }
        else{
            System.out.println(nome + " Consegue caçar");
            energia -= 2;  
            fome =+ 1;
            sono =+ 1;
            } 
    }
    
    void comer(){
        if(fome >= 1){
            System.out.println(nome + " Consegue comer");
            
            fome = 0;
            sono =+ 2;
            energia =- 1; 
            
        } else{
            System.out.println(nome + " está sem fome");
        }
    }
    
    void dormir(){
        if(sono > 3){
            System.out.println(nome + " Consegue dormi");
            
            energia = 10;
            fome =+ 2;
            sono = 0;
        } else{
            System.out.println(nome + " está sem sono");
        }
      
    }
}
