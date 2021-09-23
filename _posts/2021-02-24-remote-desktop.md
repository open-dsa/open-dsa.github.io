---
title: "Remote Desktop"
excerpt_separator: "<!--more-->"
tags: [python, pycharm, jupyter, package, pandas]

#layout: post
#title: Jupyter Notebook
#subtitle: Exercícios e Referências
#tags: [python, pycharm, jupyter, package]
#image: /img/posts/jupyter_icon.png
#bigimg: /img/posts/jupyter_big.png
#gh-repo: michelmetran/package_jupyter
#gh-badge: [follow, star, watch, fork]
#comments: true

---



## No Ubuntu 20.04, conectar-se ao Windows 10

Inicialmente é necessário habilitar a opção de *Área de Trabalho Remota* no Windows 10. Importante ressaltar que essa opção está disponível apenas nas versões do Windows 10 Pro. Versão Home não possibilita habilitar essa opção, sendo necessário fazer o upgrade do Windows.

Usei o Remmina para se conectar. Observei que o remmina não aceitou o hostname

<div class="alert alert-warning">
<b>OBSERVAÇÃO</b><br/>
    Esse <i>post</i> tem a finalidade de mostrar os comandos básicos e me deixar com uma "cola" rápida para meu uso cotidiano.<br/>
    Todas os códigos são exemplificativos e podem/devem ser alterados, indicando o nome dos arquivos e diretórios corretamente.
</div>


**Referências**

- [Conexão de área de trabalho remota do Windows no Linux com clientes RDP](https://kamarada.github.io/pt/2020/04/11/conexao-de-area-de-trabalho-remota-do-windows-no-linux-com-clientes-rdp/#.XzaSuxlv_AI)
- [**YouTube**: Como Mudar do Windows Home para o Pro, sem Precisar FORMATAR o PC!](https://www.youtube.com/watch?v=uAW83G0Vxis)



## No Windows 10, conectar-se ao Ubuntu 20.04


Inicialmente é necessário que o Linux tenha o **xrdp** instalado.

```bash
sudo apt-get install xrdp
```

<br>

Uma vez instalado, basta conectar-se ao Ubuntu, atráves do Windows, usando o comando ```mstsc```, utilizando o **Executar**.

<div class="alert alert-info">
<b>INFORMAÇÃO</b><br/>
    <ol>
    <li>É possível acessar esse <i>post</i> em formato <a href="https://rawcdn.githack.com/michelmetran/package_juypter/master/docs/juypter.html" target="_blank"><i><b>html</b></i></a>, que possibilita ter uma visualização rápida do código;</li>
    <li>Diretamente por meio do <a href="https://github.com/michelmetran/package_juypter" target="_blank"><b>repositório</b></a>, onde está disponível este arquivo <i><b>.ipynb</b></i>, que permite fazer edições no código;</li>
    <li>Ou ainda, de maneira interativa, usando o <a href="https://mybinder.org/v2/gh/michelmetran/package_juypter/master" target="_blank"><i><b>MyBinder</b></i></a>, que possibilita rodar e editar o código sem a necessidade de instalar nada.</li>
    </ol>
</div>
<br>

**Referências**

- [Como conectar à um servidor Linux via Remote Desktop (Windows)](https://medium.com/@fabianosarmento/como-conectar-%C3%A0-um-servidor-linux-via-remote-desktop-windows-aa5ce95405e8)
- [Como se conectar a partir do Windows no Ubuntu usando o Remote Desktop](https://www.vivaolinux.com.br/dica/Como-se-conectar-a-partir-do-Windows-no-Ubuntu-usando-o-Remote-Desktop)



## XfreeRDP

Instalar

```bash
sudo apt-get install freerdp2-x11 
```
<br>

Usar

```bash
xfreerdp /multimon /u: <username> /v:<remote windows machine name>
xfreerdp /multimon /u:michel /v:192.168.0.106 -wallpaper
xfreerdp /multimon /u:michel /v:asus-i5-mp
xfreerdp /multimon /gu:workgroup\michel /v:asus-i5-mp
xfreerdp /u:pecege /v:192.168.0.107
```

<br>

Tecla para alternar entre Remote e Host

```
CTRL + ALT + Enter
```

<br>

**Referências**:

- [Linux : Remote desktop multiple monitor support](https://medium.com/analytics-vidhya/linux-remote-desktop-multiple-monitor-support-840974e9eb73)

