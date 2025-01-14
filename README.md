<a href="https://github.com/AdaoG0n" style="pointer-events: none;"> <img src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/Followbutton.png" width="130" align="right"/></a>

# <a href="#" style="pointer-events: none;"><img src="https://img.shields.io/github/last-commit/AdaoG0n/GDB_-GNU_Debugger-?style=flat-square&color=%2312bab9" /> </a>

<p align="center">
  <a href="#1-compilação-com-gdb">Compilação com GDB</a>  •  
  <a href="#2-iniciar-o-gdb">Iniciar o GDB</a>  •  
  <a href="#3-inserir-argumentos-de-linha-de-comando">Argumentos</a>  •  
  <a href="#4-colocar-breakpoints">Breakpoints</a>  •  
  <a href="#5-rodar-o-programa">Rodar o Programa</a>  </br>
  <a href="#6-inspecionar-variáveis">Inspecionar Variáveis</a>  •  
  <a href="#7-continuar-a-execução">Continuar a Execução</a>  •  
  <a href="#8-inspecionar-fluxo-no-laço">Inspecionar Fluxo no Loop</a>  •  
  <a href="#9-finalizar-a-depuração">Finalizar a Depuração</a>
</p>

![](https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/bar.png)
<div align="center"> 
  
### 1. Compilação com GDB
</div>

![](https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/bar.png)
Para usar o **GDB**, é necessário compilar o programa com informações de depuração. Usar a flag `-g` ao compilar:

```bash
gcc -g -o programa programa.c
```
>[!Note]
> ##### Este comando cria um executável com as informações necessárias para depuração.
> ##### Substituir `programa` pelo nome do programa que irá ser testado!

![](https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/bar.png)
<div align="center"> 
  
### 2. Iniciar o GDB
</div>

![](https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/bar.png)
Executar o **GDB** com o programa compilado:

```bash
gdb -tui ./programa
```
>[!Note]
> ##### Abrirá o GDB diretamente no modo `TUI`, mostra o código-fonte e o prompt de comandos simultaneamente..
> ##### Para sair do TUI dentro do GDB usar `tui disable`;
> ##### Para voltar ao TUI usar `tui enable`

![](https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/bar.png)
<div align="center"> 
  
### 3. Inserir Argumentos de Linha de Comando
</div>

![](https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/bar.png)
Caso o main use argumentos (argc e argv), é preciso definir os argumentos antes de rodar o programa no GDB. Usar o comando set args:
```bash
set args "abcd" "abdc"
```
>[!Note]
> ##### Aqui, "abcd" será av[1] e "abdc" será av[2].

![](https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/bar.png)
<div align="center"> 
  
### 4. Colocar Breakpoints
</div>

![](https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/bar.png)
Breakpoints permitem que se pause a execução em linhas específicas do código para inspecionar variáveis e o fluxo do programa. 
Para definir um breakpoint no início da função main, usar:
```bash
break main
```

Se for necessário um breakpoint em uma linha específica, por exemplo, a linha onde um loop começa:
```bash
break linha
```
>[!Note]
> ##### Substituir `linha` pelo numero da linha.

![](https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/bar.png)
<div align="center"> 
  
### 5. Rodar o Programa
</div>

![](https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/bar.png)
Após a configuração dos breakpoints, iniciar a execução do programa com:
```bash
run
```
>[!Note]
>##### O programa será executado até o primeiro breakpoint. O GDB mostrará a linha do código onde ele parou.

![](https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/bar.png)
<div align="center"> 
  
### 6. Inspecionar Variáveis
</div>

![](https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/bar.png)
Para verificar os valores das variáveis no momento da execução, usar o comando print:
Exibir o valor de uma variável:
```bash
print nome_variavel
```

Exibir o conteúdo de um ponteiro (como s1 ou s2):
```bash
print s1
print *s1
```

Se s1 é uma string, pode-se imprimir a string inteira:
```bash
print s1
```
![](https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/bar.png)
<div align="center"> 
  
### 7. Continuar a Execução
</div>

![](https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/bar.png)
Depois de inspecionar variáveis, você pode continuar a execução do programa:

Continuar até o próximo breakpoint:
```bash
continue
```

Executar a próxima linha do código, entrando em funções chamadas:
```bash
step
```

Executar a próxima linha do código, pulando funções chamadas:
```bash
next
```
![](https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/bar.png)
<div align="center"> 
  
### 8. Inspecionar Fluxo no Laço
</div>

![](https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/bar.png)
No código, pode ser necessário inspecionar o comportamento dentro dos laços. Colocar um breakpoint dentro dos laços, por exemplo, onde `if (s1[i] == s2[k])` ocorre:

```bash
break 22
```
Agora, quando o programa atingir essa linha, ele pausará e sera possível inspecionar os valores das variáveis:
```bash
exemplo:
print i
print k
print s1[i]
print s2[k]
```
![](https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/bar.png)
<div align="center"> 
  
### 9. Finalizar a Depuração
</div>

![](https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/bar.png)
Para sair do GDB, usar o comando:
```bash
quit
```
![](https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/bar.png)
<div align="center"> 
  
### Resumo de Comandos Úteis

![](https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/bar.png)

|Comando             | Descrição                                       |
| ------------------ | ----------------------------------------------- |
| `break <linha> `   | Define um breakpoint em uma linha específica.   |
| `run`              | Executa o programa.                             |
| `continue`         | Continua até o próximo breakpoint.              |
| `next`             | Executa a próxima linha (sem entrar em funções).|
| `step`             | Executa a próxima linha (entrando em funções).  |
| `print <variável>` | Exibe o valor de uma variável.                  |
| `quit`             | Sai do GDB.                                     |


![](https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/animated%20gifs/madeby.gif)

![Endpoint Badge](https://img.shields.io/endpoint?url=https%3A%2F%2Fhits.dwyl.com%2FAdaoG0n%2FGDB_-GNU_Debugger-.json&style=flat-square&labelColor=black&color=blue)
