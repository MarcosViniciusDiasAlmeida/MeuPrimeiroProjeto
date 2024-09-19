# Pedra Papel e Tesoura:

![Passo a Passo](https://github.com/user-attachments/assets/8f037750-d938-4d92-b2c8-f0d6644d5099)
![Passo a Passo 2](https://github.com/user-attachments/assets/908551b4-1689-4492-b1cd-d3dd1d13a144)
![Passo a Passo 3](https://github.com/user-attachments/assets/4cbc7527-ed8f-4c04-96a9-ad7631e343b9)




# Instruções do jogo:

## 1- O que é?

Um jogo de pedra,papel e tesoura.

## 2- Como funciona?
 
 Você escolhe uma das três opções (pedra,papel e tesoura) e o programa irá escolher também uma das 3 opções aleatoriamente também.

## 3- Como construir o jogo?
 
 Devemos usar o programa .NET em linguagem c# do tipo console

### 1. Importação da Biblioteca
```
using System;
```
Este comando importa a biblioteca System, que contém classes e funções essenciais, como Console e Random. A biblioteca é usada para manipulação de entrada/saída (como Console.ReadLine e Console.WriteLine), bem como para gerar números aleatórios.

### 2. Definição da Classe "PedraPapelTesoura"
 ```
public class PedraPapelTesoura
{
    public static void Main()
    {
        // Código aqui...
    }
}
```
public class PedraPapelTesoura: Define uma classe chamada PedraPapelTesoura, onde todo o código do jogo será executado.

public static void Main(): O método Main é o ponto de entrada do programa. É onde a execução do programa começa.

### 3. Declaração das Escolhas
```
string[] escolhas = { "pedra", "papel", "tesoura" };
```
Cria um array (escolhas) que contém as três opções que o usuário pode escolher: "pedra", "papel" e "tesoura". O array armazena essas três strings, e o computador selecionará uma delas aleatoriamente.

### 4. Criação de um Objeto Random
```
Random random = new Random();
```
Cria uma instância da classe Random, que é usada para gerar um número aleatório. Esse número será usado para a escolha do computador (entre "pedra", "papel" ou "tesoura").

### 5. Estrutura de Repetição (while)
```
while (true)
{
    // Código aqui...
}
```
Um loop while que executa indefinidamente até que o jogador digite "sair". Dentro desse loop está a lógica do jogo.
O loop permite que o jogador jogue várias rodadas seguidas até que ele decida parar.

### 6. Entrada do Usuário
```
Console.Write("Escolha: pedra, papel ou tesoura (ou 'sair' para encerrar): ");
string escolhaUsuario = Console.ReadLine().ToLower();
```
O jogo pede ao usuário que faça uma escolha entre "pedra", "papel" ou "tesoura". O Console.ReadLine() lê a entrada do usuário e a função ToLower() converte a entrada para letras minúsculas (evitando problemas com maiúsculas/minúsculas).

A entrada do usuário é armazenada na variável escolhaUsuario.

### 7. Verificação de Saída
```
if (escolhaUsuario == "sair")
    break;
```
Se o jogador digitar "sair", o jogo interrompe o loop while com o comando break e termina a execução.

### 8. Validação da Escolha do Usuário
```
if (Array.IndexOf(escolhas, escolhaUsuario) == -1)
{
    Console.WriteLine("Escolha inválida. Tente novamente.");
    continue;
}
```
Aqui, o código verifica se a escolha do usuário é válida (ou seja, se está dentro do array escolhas).
Se a escolha não for uma das opções válidas, uma mensagem de erro é exibida, e o loop continue é usado para reiniciar a rodada, ignorando o restante do código dessa iteração.

### 9. Escolha Aleatória do Computador
```
string escolhaComputador = escolhas[random.Next(escolhas.Length)];
Console.WriteLine($"Computador escolheu: {escolhaComputador}");
```
random.Next(escolhas.Length) gera um número aleatório entre 0 e 2 (já que escolhas.Length é 3).
Usando esse número aleatório como índice, o programa escolhe uma das opções no array escolhas.
O jogo então imprime a escolha do computador.

### 10. Comparação e Determinação do Vencedor
```
if (escolhaUsuario == escolhaComputador)
{
    Console.WriteLine("Empate!");
}
else if ((escolhaUsuario == "pedra" && escolhaComputador == "tesoura") ||
         (escolhaUsuario == "papel" && escolhaComputador == "pedra") ||
         (escolhaUsuario == "tesoura" && escolhaComputador == "papel"))
{
    Console.WriteLine("Você venceu!");
}
else
{
    Console.WriteLine("Você perdeu!");
}
```
O código compara a escolha do usuário com a escolha do computador para determinar o resultado.

Empate: Se as escolhas forem iguais, a mensagem "Empate!" é exibida.

Vitória do Usuário: Se o usuário fizer uma escolha que vence a do computador (por exemplo, "pedra" vence "tesoura"), o código imprime "Você venceu!".

Derrota do Usuário: Caso contrário, o jogo imprime "Você perdeu!".

A lógica segue as regras clássicas:

Pedra vence Tesoura.
Papel vence Pedra.
Tesoura vence Papel.

### 11. Separador Entre Rodadas
```
Console.WriteLine(); // Linha em branco para separar as rodadas
```
Insere uma linha em branco no console para tornar o jogo mais legível entre as rodadas.

### 12. Mensagem de Encerramento
```
Console.WriteLine("Obrigado por jogar!");
```
Quando o usuário escolhe "sair", o loop se encerra, e o jogo exibe uma mensagem de agradecimento antes de terminar.
