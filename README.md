### 1. Compilação com Debug Symbols

Para usar o **GDB**, é necessário compilar o programa com informações de depuração. Usar a flag `-g` ao compilar:

```bash
gcc -g -o programa programa.c
```
>[!Note]
> ##### Este comando cria um executável com as informações necessárias para depuração.
> ##### Substituir `programa` pelo nome do programa que irá ser testado!


### 2. Iniciar o GDB

Executar o **GDB** com o programa compilado:

```bash
gdb -tui ./programa
```
>[!Note]
> ##### Abrirá o GDB diretamente no modo `TUI`, mostra o código-fonte e o prompt de comandos simultaneamente..
> ##### Para sair do TUI dentro do GDB usar `tui disable`;
> ##### Para voltar ao TUI usar `tui enable`


### 3. Inserir Argumentos de Linha de Comando

Caso o main use argumentos (argc e argv), é preciso definir os argumentos antes de rodar o programa no GDB. Usar o comando set args:
```bash
set args "abcd" "abdc"
```
>[!Note]
> ##### Aqui, "abcd" será av[1] e "abdc" será av[2].

### 4. Colocar Breakpoints

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

### 5. Rodar o Programa

Após a configuração dos breakpoints, iniciar a execução do programa com:
```bash
run
```
>[!Note]
>##### O programa será executado até o primeiro breakpoint. O GDB mostrará a linha do código onde ele parou.

### 6. Inspecionar Variáveis

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

### 7. Continuar a Execução

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

### 8. Inspecionar Fluxo no Laço

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

### 9. Finalizar a Depuração

Para sair do GDB, usar o comando:
```bash
quit
```

### Resumo de Comandos Úteis
|Comando             | Descrição                                       |
| ------------------ | ----------------------------------------------- |
| `break <linha> `   | Define um breakpoint em uma linha específica.   |
| `run`              | Executa o programa.                             |
| `continue`         | Continua até o próximo breakpoint.              |
| `next`             | Executa a próxima linha (sem entrar em funções).|
| `step`             | Executa a próxima linha (entrando em funções).  |
| `print <variável>` | Exibe o valor de uma variável.                  |
| `quit`             | Sai do GDB.                                     |
