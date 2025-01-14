<a href="https://github.com/AdaoG0n" style="pointer-events: none;"> <img src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/Followbutton.png" width="130" align="right"/></a>

# <a href="#" style="pointer-events: none;"><img src="https://img.shields.io/github/last-commit/AdaoG0n/GDB_-GNU_Debugger-?style=flat-square&color=%2312bab9" /> </a>

<div align="center"> 
<img width="200"  src="https://github.com/AdaoG0n/GDB_-GNU_Debugger-/blob/main/GDB_Archer_Fish_by_Andreas_Arnez.svg.png">
</div>

![](https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/bar.png)
<div align="center"> 

  # Como Instalar o GDB (GNU Debugger)
</div>

O processo de instalação do GDB (GNU Debugger) varia conforme o sistema operacional que está a ser utilizado. Abaixo estão as instruções para os sistemas operacionais mais comuns.

![](https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/bar.png)
<div align="center"> 

  ## 1. Linux (Debian/Ubuntu e derivados)
</div>

No Linux, o GDB pode ser instalado facilmente usando o gerenciador de pacotes.

Abrir o terminal e executar o seguinte comando:
```bash
sudo apt update  
sudo apt install gdb
```

![](https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/bar.png)
<div align="center"> 

  ## 2. Linux (Fedora/RHEL/CentOS)
</div>

No Fedora, RHEL, ou CentOS, usar o `dnf` ou `yum`:
```bash
sudo dnf install gdb   # Fedora
```
Ou, para RHEL/CentOS:
```bash
sudo yum install gdb
```

![](https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/bar.png)
<div align="center"> 

  ## 3. Linux (Arch Linux)
</div>

No Arch Linux ou derivados (como Manjaro), usar o `pacman`:
```bash
sudo pacman -S gdb
```

![](https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/bar.png)
<div align="center"> 

  ## 4. macOS
</div>

No macOS, o GDB pode ser instalado usando o Homebrew. 
Primeiro, certificar-se de ter o Homebrew instalado. Se não estiver, instalar com o seguinte comando:
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
Depois, instalar o GDB com o Homebrew:
```bash
brew install gdb
```

![](https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/bar.png)
<div align="center"> 

  ## 5. Windows
</div>

No Windows, o GDB é fornecido como parte do MinGW (Minimalist GNU for Windows) ou do Cygwin. Aqui estão duas maneiras de instalá-lo:

### Usando MinGW:

1. Baixar o MinGW Installer do site oficial: [MinGW](https://sourceforge.net/projects/mingw/)
2. Durante a instalação, **certificar-se de selecionar** o `GDB` como parte dos pacotes a serem instalados.
3. Após a instalação, adicionar o diretório do MinGW à variável de ambiente PATH.

### Usando Cygwin:

1. Baixar o instalador do Cygwin em: [Cygwin](https://www.cygwin.com/)
2. Durante a instalação, procurar por `gdb` na seleção de pacotes e selecionar para instalação.
3. Após a instalação, usar o terminal do Cygwin para rodar o GDB.


![](https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/bar.png)
<div align="center"> 

  ## 6. Verificação da Instalação
</div>

Depois de instalar o GDB, pode-se verificar se ele foi instalado corretamente com o comando:
```bash
gdb --version
```

Este comando deve mostrar a versão do GDB instalada no seu sistema.



![](https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/animated%20gifs/madeby.gif)
