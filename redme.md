# Guia de Instalação e Configuração do Git no Windows
## Link do Tutorial   

<a href="https://youtu.be/mmcOw2ynWEs?si=vEEuhvSQm24SjBrg" target="_blank">Link do video</a>

Este documento descreve o passo a passo para instalar o **Git for Windows**, configurar suas credenciais, gerar chaves SSH e conectar-se ao GitHub (ou GitLab, Bitbucket etc.).

---

## 1. Download e Instalação
```
1. Acesse o site oficial do Git for Windows:  
   https://gitforwindows.org/  
2. Clique em **Download** na versão adequada ao seu sistema (ex.: Windows 64-bit).
3. Execute o instalador (`.exe`) baixado.
4. Na tela de selecção de diretório, mantenha o padrão ou escolha sua pasta de preferência.
5. Na página de opções:
   - **Editor padrão do Git**: selecione seu editor de texto (ex.: Notepad++, VS Code, Vim).
   - **Nome da branch inicial**: por padrão “master”; você pode alterar para “main” ou outro de sua preferência.
   - **Integrar Git Bash ao Windows Terminal**:  
     - Para evitar interferência com o terminal nativo do Windows, selecione **Use Git Bash only**.  
     - Se preferir usar o terminal do Windows (CMD/PowerShell), selecione a opção correspondente.
   - Mantenha todas as outras opções como padrão (OpenSSH, line endings, credential helper etc.).
6. Clique em **Install** e aguarde a conclusão.
7. No final, marque **Launch Git Bash** e clique em **Finish**.
```


# 2. Configuração Global

## Abra o **Git Bash** (ou terminal de sua escolha) e execute:

```
Define seu nome de usuário
    git config --global user.name "Seu Nome"

Define seu e-mail
    git config --global user.email "seu.email@exemplo.com"
Verifique com:
    git config --list
```

# 3.  Inicializar um Repositório
```
 Navegue até a pasta do projeto
cd /caminho/para/seu/projeto

 Inicializa o repositório Git
git init

 Cria um arquivo de exemplo
touch teste.txt

 Adiciona todos os arquivos
git add .

 Faz o primeiro commit
git commit -m "Primeiro commit"
```

# 4. Gerar e Adicionar Chave SSH

```
ssh-keygen -t rsa -b 4096 -C "seu.email@exemplo.com"
```
```
Pressione Enter para aceitar o local padrão (~/.ssh/id_rsa).
Crie uma senha opcional para proteger sua chave (ou deixe em branco).
Copie o conteúdo da chave pública:
```

```
cat ~/.ssh/id_rsa.pub
° Acesse seu perfil no GitHub/GitLab/Bitbucket:
° Vá em Settings > SSH and GPG keys.
° Clique em New SSH key.
° Cole a chave pública e defina um título (ex.: “Meu PC Windows”).
° Salve.
```

# 5. Testar a Conexão SSH
```
ssh -T git@github.com
# ou ssh -T git@gitlab.com
```

# 6. Conectar Repositório Remoto

```
# Substitua pela URL SSH do seu repo
 git remote add origin git@github.com:usuario/repo.git
 git push -u origin main
```

# 7. Fluxo de Trabalho Básico
```
git status

git add <arquivo> ou git add .

git commit -m "mensagem"

git push

git pull
```