# 🐧 Void Linux do Zero

Um guia completo e amigável para iniciantes sobre como instalar, configurar e dominar o **Void Linux** — do zero até um sistema totalmente personalizado.  
Este projeto foi criado para documentar minha jornada pessoal configurando o Void Linux e ajudar outras pessoas que queiram explorar essa incrível distribuição *rolling release*.

---

## 📖 Índice
- [Sobre este projeto](#-sobre-este-projeto)
- [Por que Void Linux?](#-por-que-void-linux)
- [Requisitos do sistema](#-requisitos-do-sistema)
- [Instalação](#-instalação)
- [Pós-instalação](#-pós-instalação)
- [Drivers e Hardware](#-drivers-e-hardware)
- [Ambientes gráficos](#-ambientes-gráficos)
- [Ferramentas essenciais](#-ferramentas-essenciais)
- [Dicas e truques](#-dicas-e-truques)
- [Solução de problemas](#-solução-de-problemas)
- [Contribuindo](#-contribuindo)
- [Licença](#-licença)

---

## 🧠 Sobre este projeto
Este repositório serve como um **tutorial passo a passo** para instalar e configurar o Void Linux — incluindo rede, drivers, ambientes gráficos e ferramentas de desenvolvimento.  
Todas as explicações são escritas de forma **clara e direta**, para que qualquer pessoa consiga acompanhar com facilidade.

> 📝 Estou documentando tudo o que faço — desde o primeiro boot até as personalizações avançadas.

---

## 💡 Por que Void Linux?
O Void Linux é uma distribuição leve e independente, conhecida por seu:
- 🧩 **RunIt**, sistema de inicialização rápido e simples  
- ⚡ Modelo **rolling release**  
- 🧘 **Minimalismo e controle total**  
- 💻 **Desempenho e estabilidade**

Se você quer aprender como o Linux realmente funciona por dentro, o Void Linux é uma excelente escolha.  
Este projeto também serve para mostrar o **potencial do i3wm** — um *tiling window manager* minimalista, rápido e poderoso, que transforma a forma como você interage com seu sistema.

---

## ⚙️ Requisitos do sistema
| Componente | Mínimo | Recomendado |
|-------------|--------|--------------|
| CPU | Processador 64-bit | Dual-core ou superior |
| RAM | 1 GB | 4 GB+ |
| Armazenamento | 5 GB | 20 GB+ |
| Internet | Opcional | Recomendado para instalar pacotes |

---

## 🧩 Instalação

Nesta seção, você aprenderá a preparar e instalar o **Void Linux** passo a passo — desde o download da ISO até o boot inicial do sistema.

---

### 🖥️ 1. Download da ISO

Você pode baixar a imagem do Void Linux de duas formas:

- 🌐 **Site oficial:** [voidlinux.org/download](https://voidlinux.org/download/)

> ⚙️ Para este guia, utilize a **Live Image base** do Void Linux — ela vem minimalista e é perfeita para aprender cada etapa da configuração.

---

### 💾 2. Criação do Pendrive Bootável

Para criar o pendrive bootável, você pode usar qualquer ferramenta de sua preferência.  
Pessoalmente, eu recomendo o **Ventoy**, pois ele permite adicionar várias ISOs no mesmo pendrive de forma simples.

🔗 **Tutorial em vídeo (YouTube):**  
[Como criar um pendrive bootável com Ventoy](https://youtu.be/11CkqZQ3scE?si=4x_zx6tQhr5wKBks)

> 💡 Existem diversos tutoriais no YouTube sobre o processo — então não vou me estender muito nesta parte.

---

### 🚀 3. Bootando o Pendrive e Iniciando a Instalação do Void Linux

✨ Próximo passo: iniciar o instalador do Void Linux a partir do pendrive bootável.

🧠 Passos:

Reinicie o computador e acesse a BIOS/UEFI.

Geralmente, as teclas usadas são Del ou F2 (você pode tentar ambas).

Altere a ordem de boot para que o pendrive seja o primeiro da lista.

Salve e saia da BIOS.
Seu sistema agora iniciará com a tela do Ventoy, como o exemplo abaixo:

<p align="center"> <img src="https://ubunlog.com/wp-content/uploads/2024/04/ventoy-1-0-97-novedades-2024-imagen-contenido-blog-ubunlog.jpeg" alt="Ventoy USB Multiboot" width="700"> </p> <p align="center"><i>💡 Imagem ilustrativa — sua tela pode variar levemente.</i></p>

Após o Ventoy carregar, selecione a ISO do Void Linux e, em seguida, escolha a opção mostrada na imagem abaixo:

<p align="center"> <img src="https://www.ventoy.net/static/img/secondary_menu1.png" alt="Ventoy Secondary Boot Menu" width="700"> </p> <p align="center"><i>🧩 Menu secundário do Ventoy — selecione para iniciar a instalação.</i></p>

---
### 🚀 4. Início da Instalação do Void Linux

Após passar pelos menus anteriores, você verá o seguinte menu:  
Basta selecionar a **mesma opção** mostrada na imagem abaixo 👇

<p align="center">
  <img src="images/inital-install-void.png" alt="Tela de instalação do Void Linux" width="700">
</p>

---
ㅤ
ㅤ
### 🧑‍💻 Login do sistema live**

Feito isso, ele irá pedir o login do **void-live**.  
As credenciais são as seguintes:

```
Login: root
Senha: voidlinux
```

---

✅ E pronto!  
A imagem ISO já estará ativa e você poderá começar a instalação do seu Void Linux. 🐧

---
ㅤ
ㅤ
### 🌐 Conexão com a internet

É de suma importância ter conexão à internet.  
Se possível, utilize **rede cabeada**, pois é mais rápida e estável.  
Caso não tenha, siga os passos abaixo para conectar via Wi-Fi:

1️⃣ **🧠 Entrar no modo interativo do iwctl**
```bash
iwctl
```
>Vai aparecer algo tipo:

```
[iwd]#
```
2️⃣ **📶 Ver as interfaces disponíveis**

>Dentro do iwctl, digita:

```
[iwd]# device list
```

Procura algo como wlan0 ou wlp2s0.
Esse é o nome da tua placa Wi-Fi

3️⃣ **🔍 Ver redes disponíveis**

>Ainda dentro do iwctl:

```
[iwd]# station wlan0 scan
[iwd]# station wlan0 get-networks
```
>(substitui wlan0 pelo nome real do teu dispositivo)

4️⃣ **🔑 Conectar à rede**

```
[iwd]# station wlan0 connect NOME_DA_REDE
```
Se tiver senha, ele vai pedir pra digitar.

>Exemplo:

```
[iwd]# station wlan0 connect MinhaRedeWiFi
```


5️⃣ **🌐 Testar a conexão**

Sai do iwctl com:

```
[iwd]# exit
```
Depois testa com:

```
# ping voidlinux.org
```

ele apresentara um retorno assim:

```
>PING voidlinux.org (159.69.226.196) 56(84) bytes of data.
>64 bytes from 159.69.226.196: icmp_seq=1 ttl=51 time=23.4 ms
>64 bytes from 159.69.226.196: icmp_seq=2 ttl=51 time=22.8 ms
>64 bytes from 159.69.226.196: icmp_seq=3 ttl=51 time=23.1 ms
```

feito isso, tudo certo : ) vamos para a proxima etapa
ㅤ
ㅤ

---
ㅤ
ㅤ
## Instalação

>Você pode utilizar o instalador automatizado do void, mas particularmente eu nao gosto muito, e recomendo você fazer a instalação via chroot que é como ajudarei a fazer neste tutorial

>bom a primeira coisa que precisamos fazer, é particionar o nosso disco, eu particularmente gosto muito de utilizar o cfdisk, então nesse tutorial irei utilizar ele, para isso você precisará digitar:

```
# lsblk
```

>Você verá algo do tipo:

<p align="center">
  <img src="images/menu-lsblk.png" alt="Tela de instalação do Void Linux" width="700">
  <i>Imagem apenas ilustrativa, você vera listar seu ssd ou hd</i>
</p>

>Agora você irá digitar:

```
# cfdisk /dev/sda
```

>Você deverá substituir esse sda pelo nome do seu disco, se fosse um ssd nvme, iria listar como: 'nvme1n1' algo do tipo...

>Após isso voce vera um menu como esse:

<p align="center">
  <img src="images/menu-cfdisk.png" alt="Tela de instalação do Void Linux" width="700">
</p>

>Como estamos em um sistema UEFI usaremos o sistema gpt msm

>feito isso você verá a seguinte tela:

<p align="center">
  <img src="images/menu-de-particao.png" alt="Tela de instalação do Void Linux" width="700">
</p>

>Dai você clica 'ENTER', e ele ira perguntar o tamanho da partição dai você poe exatamente:

```
# 1G
```

>Esse '1G' é para partição de boot onde logicamente irá ter 1GB, depois de digitar 1G aperte 'ENTER'

>Novamente você irá até a sessão onde esta o espaço livre, e aperte 'ENTER', e ele ira perguntar o tamanho da partição dai você poe exatamente:

```
# 4G
```

>Esse '4G' é para uma partição SWAP, você não precisa fazer essa se nao quiser uma partição swap, mas particulamente sempre fiz, então vai da sua escolha.

>Novamente você irá até a sessão onde esta o espaço livre, e aperte 'ENTER' DUAS VEZES para utilizar o total do espaço restante para sua partição root, voce deverá obter algo parecido com isso:

<p align="center">
  <img src="images/menu-particao2.png" alt="Tela de instalação do Void Linux" width="700">
</p>

>Dai você navege até onde esta escrito 'Write' aperte enter, e obrigatoriamente você deverá escrever 'yes' dessa mesma forma, dai aperte 'ENTER', e depois pode sair indo até 'quit' e apertando 'ENTER'

>Após sair digite:

```
# lsblk
```

>Para confirmar tudo isso... você verá algo parecido com isso:

<p align="center">
  <img src="images/menu-lsblk2.png" alt="Tela de instalação do Void Linux" width="700">
</p>

>Vamos prosseguir para criar esses sistemas de arquivos, digite os seguintes comandos:

```
# mkfs.ext4 /dev/sda3
```

>Pronto agora temos nosso sistema de arquivos root configurado

>OBS: sempre trocando o 'sda' pelo nome do seu dispositivo

>E agora para nosso sistema de arquvios de inicialização, digite:

```
# mkfs.fat -F 32 /dev/sda1
```

>E para o nosso swap digite:

```
# mkswap /dev/sda2
```
>E pronto, vamos montar essas unidades agora

>Para nosso sistema raiz, faça:

```
# mount /dev/sda3 /mnt
```
>Para nossa partição de inicialização, faça:

```
# mount --mkdir /dev/sda1 /mnt/boot/efi
```

>Para nosso swap, faça:

```
# swapon /dev/sda2
```

>Vamos confirmar tudo isso novamente com:

```
# lsblk
```

>Você verá algo parecido com isso:

>Para confirmar tudo isso... você verá algo parecido com isso:

<p align="center">
  <img src="images/menu-lsblk3.png" alt="Tela de instalação do Void Linux" width="700">
</p>

>Com isso temos nossa partição raiz, temos nossa partição de inicialização, e temos nosso swap, agora estamos prontos para instalar o void linux de fato.

---
ㅤ
ㅤ

## 🪄 Pós-instalação
Após instalar o Void, veremos como:
- Configurar a rede (Wi-Fi, Ethernet)  
- Criar usuários  
- Ativar serviços do RunIt  
- Instalar ferramentas básicas de terminal  
- Gerenciar pacotes com `xbps`  

Essa etapa garante que o sistema esteja funcional e pronto para receber o ambiente gráfico i3wm.
ㅤ
ㅤ

---
ㅤ
ㅤ

## 🧰 Drivers e Hardware
Tutoriais para configurar:
- Drivers de vídeo **NVIDIA / AMD / Intel**  
- Áudio (**PipeWire**, **ALSA**)  
- Bluetooth  
- Touchpad e periféricos  

Cada parte será explicada em detalhes, com foco na **compatibilidade e estabilidade** do sistema.
ㅤ
ㅤ

---
ㅤ
ㅤ
## 🎨 Ambientes gráficos
Este guia será voltado especialmente para o **i3wm**, um *tiling window manager* conhecido por sua leveza e produtividade.  
Vamos aprender a:
- Instalar e configurar o i3wm  
- Personalizar atalhos, barras e temas  
- Integrar ferramentas como `rofi`, `polybar` e `picom`  
- Melhorar a experiência visual e funcional do sistema  

> 🧱 O objetivo é mostrar como o i3wm pode ser uma alternativa poderosa e minimalista aos ambientes gráficos tradicionais.
>
ㅤ
ㅤ

---

## 🧰 Ferramentas essenciais
Uma seleção de ferramentas úteis para o dia a dia:
- **neovim** — editor de texto avançado  
- **git** — controle de versão  
- **htop / btop** — monitoramento do sistema  
- **ranger** — gerenciador de arquivos em terminal  
- **firefox / brave** — navegação web  

Cada ferramenta será explicada com sua função e motivo de uso no Void Linux.

---

## 🧠 Dicas e truques
Pequenos ajustes que fazem grande diferença:
- Alias úteis no `.bashrc` ou `.zshrc`  
- Temas e fontes personalizadas  
- Otimização de desempenho  
- Scripts automáticos com `RunIt`  

---

## 🧩 Solução de problemas
Resolução de erros comuns:
- Falhas de boot  
- Wi-Fi não detectado  
- Sem áudio ou microfone  
- Tela preta no i3wm  

> 🧰 Cada erro documentado virá com a causa e a solução testada.

---

## 🤝 Contribuindo
Contribuições são bem-vindas!  
Se você quiser ajudar a melhorar este guia:
1. Faça um **fork** do repositório  
2. Crie uma **branch** com suas alterações  
3. Envie um **pull request** explicando suas modificações  

---

## 📜 Licença
Este projeto é licenciado sob a [MIT License](LICENSE).

---

> 🧭 *Feito com dedicação e curiosidade — por alguém que acredita no poder do aprendizado através da prática.*
