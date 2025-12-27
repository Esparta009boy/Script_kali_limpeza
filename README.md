# Script_kali_limpeza
Script prático para limpeza de disco no Kali Linux. Recurso complementar do tutorial explicativo do meu canal no YouTube.

# Script_kali_limpeza_disco
Guia interativo sobre automação de limpeza de disco no Kali Linux

![Capa do Projeto](https://itforum.com.br/wp-content/uploads/2019/11/hacker.jpg)

# 🧹 Script de Limpeza para Kali Linux

Material interativo em **formato Bash Script** que automatiza tarefas de limpeza de disco, remoção de arquivos temporários e otimização de espaço.  
Este script é um complemento ao vídeo tutorial do canal no YouTube, mostrando de forma **didática e prática** como desenvolver scripts no Kali Linux utilizando o editor **nano**.

Para fins educacionais, o projeto foi desenvolvido utilizando **Kali Linux** em ambiente controlado.

---
📜 Script Utilizado no Vídeo (Ronaldo Academia Cyber)

#!/bin/bash

if [ "$EUID" -ne 0 ]; then
  echo "ERRO: por favor, execute como root: sudo ./limpeza.sh"
  exit
fi

apt-get autoremove -y
apt-get autoclean -y
apt-get clean

journalctl --vacuum-time=2d

rm -rf ~/.cache/thumbnails/*
rm -rf /tmp/*

rm -rf ~/.local/share/trash/*
rm -rf /root/.local/share/trash/*

df -h | grep '^/dev/'


---

## 📊 Estatísticas do Projeto

| 📈 Conteúdo | 📦 Atualizações | 🧠 Tópicos Cobertos | 🖼️ Demonstrações | 🌍 Público-Alvo | 🏆 Avaliação |
|-------------|----------------|---------------------|------------------|-----------------|--------------|
| 2025        | 1ª Edição      | 8                   | ✅ Sim           | Estudantes e Profissionais | A+ |

---

## 🧠 Tecnologias Utilizadas

![Bash](https://img.shields.io/badge/Bash-4EAA25?style=for-the-badge&logo=gnubash&logoColor=white)
![Kali Linux](https://img.shields.io/badge/Kali_Linux-557C94?style=for-the-badge&logo=kalilinux&logoColor=white)
![GNU Nano](https://img.shields.io/badge/Nano-1D7CF2?style=for-the-badge&logoColor=white)

---

## 🎁 Funcionalidades

- Automação da limpeza de disco com comandos `apt`, `journalctl` e `rm`
- Verificação de execução como root
- Remoção de arquivos temporários e cache
- Demonstração prática com uso do editor **nano**
- Complemento didático ao vídeo tutorial no YouTube

---
⚙️ Comandos para Rodar o Script

┌──(kali㉿kali)-[~]
└─$ nano limpeza.sh

┌──(kali㉿kali)-[~]
└─$ chmod +x limpeza.sh

┌──(kali㉿kali)-[~]
└─$ sudo ./limpeza.sh

