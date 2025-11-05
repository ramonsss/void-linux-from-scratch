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

🧑‍💻 **Login do sistema live**

Feito isso, ele irá pedir o login do **void-live**.  
As credenciais são as seguintes:

>Login: root
--
>Senha: voidlinux

---

✅ E pronto!  
A imagem ISO já estará ativa e você poderá começar a instalação do seu Void Linux. 🐧

---

## 🪄 Pós-instalação
Após instalar o Void, veremos como:
- Configurar a rede (Wi-Fi, Ethernet)  
- Criar usuários  
- Ativar serviços do RunIt  
- Instalar ferramentas básicas de terminal  
- Gerenciar pacotes com `xbps`  

Essa etapa garante que o sistema esteja funcional e pronto para receber o ambiente gráfico i3wm.

---

## 🧰 Drivers e Hardware
Tutoriais para configurar:
- Drivers de vídeo **NVIDIA / AMD / Intel**  
- Áudio (**PipeWire**, **ALSA**)  
- Bluetooth  
- Touchpad e periféricos  

Cada parte será explicada em detalhes, com foco na **compatibilidade e estabilidade** do sistema.

---

## 🎨 Ambientes gráficos
Este guia será voltado especialmente para o **i3wm**, um *tiling window manager* conhecido por sua leveza e produtividade.  
Vamos aprender a:
- Instalar e configurar o i3wm  
- Personalizar atalhos, barras e temas  
- Integrar ferramentas como `rofi`, `polybar` e `picom`  
- Melhorar a experiência visual e funcional do sistema  

> 🧱 O objetivo é mostrar como o i3wm pode ser uma alternativa poderosa e minimalista aos ambientes gráficos tradicionais.

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
