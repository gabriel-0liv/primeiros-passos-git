# 📘 Minicurso de Git e GitHub para Iniciantes (do zero absoluto)

> **Você não precisa saber nada.** Nem o que é terminal, nem o que é GitHub.
> Esta cartilha começa criando sua conta, instalando as ferramentas e fazendo login, e termina com você colaborando em projetos de outras pessoas.

---

## 📑 Sumário

**Parte 1: Preparando o terreno**

1. [Como usar esta cartilha](#1--como-usar-esta-cartilha)

2. [O que é Git? O que é GitHub?](#2--o-que-é-git-o-que-é-github)

3. [Criando sua conta no GitHub](#3--criando-sua-conta-no-github)

4. [Instalando as ferramentas](#4--instalando-as-ferramentas)

5. [Terminal para quem nunca viu um](#5--terminal-para-quem-nunca-viu-um)

6. [Configurando o Git pela primeira vez](#6--configurando-o-git-pela-primeira-vez)

**Parte 2: Git no seu computador**

7. [Conceitos fundamentais](#7--conceitos-fundamentais)

8. [Seu primeiro repositório](#8--seu-primeiro-repositório)

9. [Ciclo básico: editar, add, commit](#9--ciclo-básico-editar-add-commit)

10. [Vendo o histórico](#10--vendo-o-histórico)

11. [Ignorando arquivos (.gitignore)](#11--ignorando-arquivos-gitignore)

12. [Desfazendo coisas](#12--desfazendo-coisas)

13. [Branches](#13--branches)

14. [Merge e conflitos](#14--merge-e-conflitos)

**Parte 3: GitHub (a nuvem)**

15. [Fazendo login: conectando o Git à sua conta](#15--fazendo-login-conectando-o-git-à-sua-conta)

16. [Criando um repositório no GitHub (pelo site)](#16--criando-um-repositório-no-github-pelo-site)

17. [Enviando seu projeto local para o GitHub](#17--enviando-seu-projeto-local-para-o-github)

18. [Baixando projetos: clone, pull e fetch](#18--baixando-projetos-clone-pull-e-fetch)

19. [Escrevendo um bom README (Markdown)](#19--escrevendo-um-bom-readme-markdown)

20. [Trabalhando em equipe: fork e pull request](#20--trabalhando-em-equipe-fork-e-pull-request)

**Parte 4: Fechamento**

21. [Erros comuns e como resolver](#21--erros-comuns-e-como-resolver)

22. [Boas práticas](#22--boas-práticas)

23. [Exercícios](#23--exercícios)

24. [Cola de comandos](#24--cola-de-comandos)

25. [Glossário](#25--glossário)

26. [Para continuar estudando](#26--para-continuar-estudando)

---

# PARTE 1: PREPARANDO O TERRENO

## 1. 🎯 Como usar esta cartilha

- Leia **na ordem**. Cada seção usa o que foi aprendido na anterior.
- **Digite os comandos você mesmo**, em vez de só ler. Git se aprende fazendo.
- Blocos de código assim são para **digitar no terminal**:

```bash
git status
```

- Quando aparecer algo como `seu-usuario`, `Seu Nome` ou `nome-do-repositorio`, **troque pelo seu valor**.
- Sugestão de divisão em aulas:

| Aula | Seções | Tema |
|---|---|---|
| 1 | 2 a 6 | Conta, instalação, terminal e configuração |
| 2 | 7 a 10 | Primeiros commits e histórico |
| 3 | 11 a 14 | .gitignore, desfazer, branches e merge |
| 4 | 15 a 18 | Login, repositório no GitHub, push e clone |
| 5 | 19 a 20 | README e trabalho em equipe |

---

## 2. 🤔 O que é Git? O que é GitHub?

### O problema

Você está escrevendo um trabalho e vai salvando assim:

```
trabalho.docx
trabalho_final.docx
trabalho_final_agora_vai.docx
trabalho_final_REVISADO_2.docx
```

Qual é a versão certa? O que mudou entre elas? E se duas pessoas editarem ao mesmo tempo?

### A solução: Git

**Git é um sistema de controle de versão.** Ele:

- 📸 Tira "fotos" (chamadas **commits**) do seu projeto quando você pede;
- 🕰️ Guarda todo o histórico e permite voltar no tempo;
- 🌿 Permite criar ramificações para testar ideias sem estragar o que funciona;
- 👥 Ajuda várias pessoas a trabalharem no mesmo projeto;
- 💻 Roda **no seu computador**, sem precisar de internet.

### E o GitHub?

**GitHub é um site** que guarda projetos Git na nuvem, como um "Google Drive para código", com recursos extras para colaboração.

| | **Git** | **GitHub** |
|---|---|---|
| O que é | Programa instalado no seu PC | Site / serviço online |
| Precisa de internet? | Não | Sim |
| Para que serve | Controlar versões | Hospedar, compartilhar e colaborar |
| Analogia | O Word | O Google Drive |

> 💡 Existem outras plataformas parecidas (GitLab, Bitbucket), mas todas usam Git por baixo. Aprendendo Git, você usa qualquer uma.

---

## 3. 🆕 Criando sua conta no GitHub

### Passo a passo

1. Abra o navegador e acesse **<https://github.com>**.
   <img width="1628" height="565" alt="image" src="https://github.com/user-attachments/assets/8b7776b4-1fbf-4959-90e2-793510680ecd" />

3. Clique em **Sign up** (Cadastre-se), no canto superior direito.
4. Preencha:
   - **E-mail**: use um e-mail que você acessa (vão chegar mensagens de confirmação);
   - **Senha**: forte e única (não reutilize a de outros sites);
   - **Username (nome de usuário)**: pense bem, ele aparece na URL do seu perfil (`github.com/seu-usuario`) e será visto por professores e recrutadores. Prefira algo profissional, como `joaosilva` ou `maria-souza-dev`.
5. Resolva a verificação anti-robô (puzzle) e clique em **Create account**.
6. O GitHub envia um **código por e-mail**. Digite-o para confirmar.
7. Responda às perguntas iniciais (pode pular) e escolha o plano **Free** (gratuito). Ele é mais que suficiente.

### 🔐 Ative a verificação em duas etapas (2FA)

O GitHub exige ou recomenda fortemente a autenticação em duas etapas. Ela protege sua conta mesmo que alguém descubra sua senha.

1. Clique na sua **foto/ícone** no canto superior direito → **Settings** (Configurações).
2. No menu lateral, clique em **Password and authentication**.
3. Em *Two-factor authentication*, clique em **Enable two-factor authentication** e siga as instruções (normalmente com um app autenticador, como Google Authenticator ou Authy, ou chave de segurança).
4. **Guarde os códigos de recuperação** em local seguro (gerenciador de senhas ou papel). Sem eles, você pode perder acesso à conta se perder o celular.

> As telas do GitHub mudam de vez em quando. Se algum botão estiver em outro lugar, procure pelo nome em inglês indicado aqui.

### Como fazer login no site (e sair)

- **Entrar:** vá em <https://github.com/login>, digite usuário (ou e-mail) e senha, e depois o código do 2FA.
- **Sair:** clique no seu ícone (canto superior direito) → **Sign out**.

> ⚠️ **Atenção:** o login do **site** é uma coisa; o login do **Git no terminal** é outra. Você vai configurar o segundo na [seção 15](#15--fazendo-login-conectando-o-git-à-sua-conta).

### Complete seu perfil (opcional, mas legal)

Ícone → **Your profile** → **Edit profile**: coloque foto, nome e uma frase curta sobre você.

---

## 4. 🛠️ Instalando as ferramentas

Você precisa de **duas** coisas: o **Git** e um **editor de texto** (recomendo o VS Code).

### 4.1 Instalando o Git

#### 🪟 Windows

1. Acesse **<https://git-scm.com/downloads>** e clique em **Windows**. O download começa.
2. Abra o instalador e clique em **Next** na maioria das telas (as opções padrão funcionam bem).
3. Quando aparecer a tela sobre o **editor padrão do Git**, você pode escolher o **Visual Studio Code** se já o tiver instalado (ou deixar o padrão).
4. Conclua com **Install** e depois **Finish**.
5. Agora você tem o **Git Bash**: um terminal que entende os comandos desta cartilha. Procure por "Git Bash" no menu Iniciar.

#### 🍎 macOS

1. Abra o app **Terminal** (Cmd + Espaço, digite "Terminal").
2. Digite:

```bash
git --version
```

3. Se o Git não estiver instalado, o macOS oferece instalar as *Command Line Tools*. Aceite e aguarde.

(Alternativa: se você usa o Homebrew, `brew install git`.)

#### 🐧 Linux (Ubuntu/Debian)

```bash
sudo apt update
sudo apt install git
```

#### ✅ Conferindo a instalação

Abra o terminal (Git Bash no Windows) e digite:

```bash
git --version
```

Deve aparecer algo como `git version 2.xx.x`. Se aparecer, está pronto! 🎉

### 4.2 Instalando o VS Code (editor de texto)

1. Acesse **<https://code.visualstudio.com>** e baixe a versão para o seu sistema.
2. Instale com as opções padrão.
3. No Windows, na instalação, marque as opções **"Adicionar ao PATH"** e **"Abrir com Code"** (facilitam a vida).

> Você pode usar outro editor, mas **não use o Bloco de Notas** nem o Word para código.

---

## 5. ⌨️ Terminal para quem nunca viu um

O **terminal** é uma janela onde você controla o computador **digitando comandos**, em vez de clicar. O Git é usado principalmente por ele.

### 5.1 Abrindo o terminal

| Sistema | Como abrir |
|---|---|
| Windows | Menu Iniciar → digite **Git Bash** |
| macOS | Cmd + Espaço → **Terminal** |
| Linux | Ctrl + Alt + T |
| Dentro do VS Code | Menu **Terminal → New Terminal** (ou `Ctrl + '`) |

### 5.2 O que você vê

```
usuario@computador MINGW64 ~
$ _
```

- O `$` indica que o terminal **espera um comando**. (Você não digita o `$`.)
- O `~` representa sua **pasta pessoal** (a "home").
- Digite um comando e aperte **Enter** para executar.

### 5.3 Os comandos que você precisa

| Comando | O que faz | Exemplo |
|---|---|---|
| `pwd` | Mostra **onde você está** (pasta atual) | `pwd` |
| `ls` | **Lista** arquivos e pastas | `ls` |
| `ls -a` | Lista também os arquivos **ocultos** | `ls -a` |
| `cd pasta` | **Entra** em uma pasta | `cd Documentos` |
| `cd ..` | **Volta** uma pasta | `cd ..` |
| `cd ~` | Vai para sua pasta pessoal | `cd ~` |
| `mkdir nome` | **Cria** uma pasta | `mkdir projetos` |
| `touch arquivo.txt` | **Cria** um arquivo vazio | `touch notas.txt` |
| `clear` | **Limpa** a tela | `clear` |

> 🪟 No Git Bash do Windows, todos esses comandos funcionam. No Prompt de Comando (CMD), alguns são diferentes (`dir` em vez de `ls`, por exemplo). **Use o Git Bash** para seguir esta cartilha.

### 5.4 Truques que salvam tempo

- ⭐ **Tab** completa nomes automaticamente. Digite `cd Doc` e aperte Tab.
- ⬆️ **Seta para cima** repete comandos anteriores.
- 🛑 **Ctrl + C** interrompe um comando que travou.
- 📂 Nomes com **espaço** precisam de aspas: `cd "Meus Documentos"`.
- 🔤 O terminal diferencia **maiúsculas de minúsculas** (em muitos sistemas): `Projetos` ≠ `projetos`.
- 📋 No Git Bash, para colar use **Shift + Insert** ou clique com o botão direito. (Ctrl + V pode não funcionar em versões antigas.)

### 5.5 Mini-prática

Vamos criar uma pasta para o curso e entrar nela:

```bash
cd ~                    # vai para a pasta pessoal
mkdir curso-git         # cria a pasta do curso
cd curso-git            # entra nela
pwd                     # confirma onde você está
```

> Todos os exercícios daqui para frente acontecerão **dentro de `curso-git`**.

---

## 6. ⚙️ Configurando o Git pela primeira vez

O Git grava **quem fez** cada commit. Por isso precisa do seu nome e e-mail. Faça isso **uma única vez** no computador:

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seu-email@exemplo.com"
```

> 📧 Use **o mesmo e-mail da sua conta do GitHub** para seus commits serem ligados ao seu perfil.
> (Se preferir não expor o e-mail, o GitHub oferece um e-mail privado em *Settings → Emails*. Veja a documentação.)

Defina o nome padrão da branch principal como `main`:

```bash
git config --global init.defaultBranch main
```

Confira o que foi salvo:

```bash
git config --list
```

> Aperte `q` para sair da listagem se ela travar a tela.

---

# PARTE 2: GIT NO SEU COMPUTADOR

## 7. 🧠 Conceitos fundamentais

Estas ideias explicam **90% do Git**. Leia com calma.

### 7.1 Repositório (repo)

Uma pasta de projeto que o Git está "vigiando". Dentro dela existe uma pasta oculta chamada `.git`, onde fica todo o histórico.

> ⚠️ Se você apagar a pasta `.git`, perde o histórico do projeto.

### 7.2 Commit

Uma "foto" do projeto em determinado momento, com: mensagem, autor, data e um identificador único (hash), como `a1b2c3d`.

### 7.3 As três áreas do Git (o conceito mais importante!)

```
┌──────────────────┐   git add    ┌──────────────────┐  git commit  ┌──────────────────┐
│ Diretório de     │ ───────────► │ Área de          │ ───────────► │ Repositório      │
│ trabalho         │              │ preparação       │              │ (histórico)      │
│ (working dir)    │              │ (staging area)   │              │ (.git)           │
└──────────────────┘              └──────────────────┘              └──────────────────┘
  Onde você edita                   O que vai entrar                  Versões salvas
  os arquivos                       no próximo commit
```

**Analogia da mudança de casa 📦:**

- *Diretório de trabalho* = a bagunça da casa.
- *Staging area* = as coisas que você já colocou na caixa.
- *Commit* = fechar e etiquetar a caixa.

Por que a staging existe? Para você escolher **exatamente** o que entra em cada commit.

### 7.4 Estados de um arquivo

| Estado | Significado |
|---|---|
| **Untracked** | Arquivo novo; o Git ainda não o conhece |
| **Modified** | Arquivo conhecido que foi alterado |
| **Staged** | Alteração marcada para o próximo commit |
| **Committed** | Alteração salva no histórico |

### 7.5 Branch

Uma linha independente de desenvolvimento. A principal costuma se chamar `main`.

### 7.6 HEAD

Um "ponteiro" que indica **onde você está agora** no histórico.

### 7.7 Remoto (remote) e origin

Uma cópia do repositório em outro lugar (como o GitHub). O remoto padrão recebe o apelido **`origin`**.

---

## 8. 🚀 Seu primeiro repositório

Dentro da pasta `curso-git`, vamos criar um projeto:

```bash
cd ~/curso-git
mkdir meu-primeiro-repo
cd meu-primeiro-repo
git init
```

Saída esperada:

```
Initialized empty Git repository in .../meu-primeiro-repo/.git/
```

🎉 **Parabéns, você criou um repositório!** Para ver a pasta oculta `.git`:

```bash
ls -a
```

Agora veja a situação:

```bash
git status
```

```
On branch main
No commits yet
nothing to commit
```

> 🔎 **`git status` é seu melhor amigo.** Use-o o tempo todo. Ele diz o que está acontecendo e sugere o próximo passo.

---

## 9. 🔁 Ciclo básico: editar, add, commit

O fluxo que você repetirá milhares de vezes:

```
editar arquivos  →  git status  →  git add  →  git commit
```

### Passo a passo

**1. Crie um arquivo:**

```bash
echo "# Meu Projeto" > README.md
```

(O `echo` escreve o texto e o `>` joga dentro do arquivo.)

**2. Veja o status.** O arquivo aparece como *untracked*:

```bash
git status
```

**3. Adicione à staging area:**

```bash
git add README.md
```

Outras formas:

```bash
git add arquivo1.txt arquivo2.txt   # vários arquivos
git add pasta/                      # uma pasta
git add .                           # tudo que mudou (use com atenção!)
```

**4. Faça o commit:**

```bash
git commit -m "Adiciona README inicial"
```

> 🪤 **Armadilha do iniciante:** se você digitar só `git commit` (sem `-m`), o Git abre um editor de texto no terminal (geralmente o **Vim**) e muita gente fica presa! Se isso acontecer: aperte `Esc`, digite `:q!` e Enter para sair sem salvar. Sempre use `-m "mensagem"`.

**5. Confira:**

```bash
git status
```

```
nothing to commit, working tree clean
```

🎉 **Primeiro commit feito!**

### Modificando e salvando de novo

Edite o `README.md` (pelo VS Code: `code .` abre a pasta atual) e acrescente uma linha. Depois:

```bash
git status          # mostra "modified"
git diff            # mostra exatamente o que mudou
git add README.md
git commit -m "Adiciona descrição ao README"
```

### Como escrever uma boa mensagem de commit

- Curta e clara (primeira linha com até ~50 caracteres).
- Diga **o que** a mudança faz.
- Verbo no imperativo: *"Adiciona"*, *"Corrige"*, *"Remove"*.

| ❌ Ruim | ✅ Bom |
|---|---|
| `alterações` | `Corrige cálculo do total no carrinho` |
| `asdf` | `Adiciona página de login` |
| `final v2` | `Remove função de exportação não utilizada` |

---

## 10. 📜 Vendo o histórico

```bash
git log
```

Versões mais legíveis:

```bash
git log --oneline                  # um commit por linha
git log --oneline --graph --all    # com desenho das branches
git log -3                         # só os 3 últimos
```

Ver o que mudou em um commit:

```bash
git show a1b2c3d
```

Comparar mudanças:

```bash
git diff              # arquivos editados x staging
git diff --staged     # staging x último commit
```

> Dentro do `git log`, use as setas para navegar e **`q` para sair**.

---

## 11. 🙈 Ignorando arquivos (.gitignore)

Nem tudo deve ir para o repositório: senhas, arquivos temporários, pastas de dependências (`node_modules`), arquivos do sistema...

Crie um arquivo chamado `.gitignore` na raiz do projeto:

```gitignore
# Dependências
node_modules/

# Senhas e variáveis de ambiente
.env

# Arquivos de sistema
.DS_Store
Thumbs.db

# Logs
*.log

# Pastas geradas automaticamente
dist/
```

Depois, commite o próprio `.gitignore`:

```bash
git add .gitignore
git commit -m "Adiciona .gitignore"
```

> 🔐 **Nunca** envie senhas, tokens ou chaves de API para o Git. Mesmo apagando depois, elas continuam no histórico. Se vazar, troque a credencial imediatamente.

> ⚠️ O `.gitignore` só vale para arquivos que **ainda não foram commitados**. Se o arquivo já era rastreado, use `git rm --cached arquivo`.

---

## 12. ⏪ Desfazendo coisas

Todo mundo erra, e o Git foi feito para isso.

### 12.1 Descartar alterações de um arquivo (antes do `add`)

```bash
git restore arquivo.txt
```

> ⚠️ Apaga suas alterações naquele arquivo. **Não tem volta.**

### 12.2 Tirar um arquivo da staging (fez `add` sem querer)

```bash
git restore --staged arquivo.txt
```

### 12.3 Corrigir a mensagem do último commit

```bash
git commit --amend -m "Nova mensagem correta"
```

> Use só em commits que **ainda não foram enviados** ao GitHub.

### 12.4 Desfazer um commit com segurança: `git revert`

Cria um **novo commit** que desfaz um anterior, preservando o histórico. É seguro em projetos compartilhados.

```bash
git revert a1b2c3d
```

### 12.5 Voltar no tempo: `git reset`

| Comando | O que acontece com suas alterações |
|---|---|
| `git reset --soft HEAD~1` | Desfaz o commit; mantém tudo na staging |
| `git reset --mixed HEAD~1` | Desfaz o commit; mantém as alterações nos arquivos (padrão) |
| `git reset --hard HEAD~1` | Desfaz o commit **e apaga** as alterações 🔥 |

> `HEAD~1` significa "um commit antes de onde estou".

### Qual usar?

```
Não commitei, quero descartar         →  git restore
Dei add sem querer                    →  git restore --staged
Errei a mensagem do último commit     →  git commit --amend
Já enviei ao GitHub e quero desfazer  →  git revert
Só no meu PC, quero voltar            →  git reset
```

---

## 13. 🌿 Branches

Branches permitem trabalhar em algo novo **sem mexer na versão estável**.

```
main     ●───●───●───────────●───●
                  \         /
nova-feature       ●───●───●
```

### Comandos

```bash
git branch                       # lista as branches (a atual tem *)
git branch nova-feature          # cria uma branch
git switch nova-feature          # muda para ela
git switch -c nova-feature       # cria E muda (atalho)
git branch -d nova-feature       # apaga a branch (já mergeada)
```

> Em tutoriais antigos você verá `git checkout nome`. Funciona, mas `git switch` é mais claro.

### Fluxo típico

```bash
git switch -c adiciona-rodape       # 1. cria a branch e entra nela
# ... edita arquivos ...
git add .
git commit -m "Adiciona rodapé ao site"
git switch main                     # 2. volta para a main
git merge adiciona-rodape           # 3. junta o trabalho
git branch -d adiciona-rodape       # 4. apaga a branch (opcional)
```

Ao trocar de branch, os arquivos da pasta **mudam sozinhos** para refletir aquela branch. Parece mágica, mas é o Git trabalhando.

> 💡 Antes de trocar de branch, faça commit das alterações pendentes (ou use `git stash` para guardá-las temporariamente).

---

## 14. 🔀 Merge e conflitos

### Merge

Traz as alterações de uma branch para a branch em que você está:

```bash
git switch main
git merge nome-da-outra-branch
```

### Conflitos

Acontecem quando **duas branches alteraram a mesma parte do mesmo arquivo**. Não é erro: é o Git perguntando qual versão manter.

O arquivo fica assim:

```
<<<<<<< HEAD
Título da versão da main
=======
Título da versão da outra branch
>>>>>>> nome-da-outra-branch
```

**Como resolver:**

1. Abra o arquivo e escolha o que fica (ou combine os dois textos).
2. **Apague** as marcações `<<<<<<<`, `=======` e `>>>>>>>`.
3. Salve o arquivo.
4. Finalize:

```bash
git add arquivo-com-conflito.txt
git commit
```

> 🛟 Desistiu no meio? `git merge --abort` cancela tudo.
> O VS Code mostra botões como *Accept Current Change*, *Accept Incoming Change* e *Accept Both Changes* para resolver visualmente.

---

# PARTE 3: GITHUB (A NUVEM)

## 15. 🔑 Fazendo login: conectando o Git à sua conta

Até aqui tudo ficou no seu computador. Para enviar projetos ao GitHub, o Git precisa **provar que você é você**. Isso é o "login no terminal".

> ⚠️ **O GitHub não aceita sua senha normal no terminal.** Precisa de um dos métodos abaixo.

Escolha **um** método. Se estiver em dúvida, comece pelo **Método A**.

| Método | Dificuldade | Quando usar |
|---|---|---|
| **A. Login pelo navegador** (Git Credential Manager) | ⭐ Fácil | Windows e macOS, a opção mais simples |
| **B. Token de acesso pessoal** | ⭐⭐ Médio | Qualquer sistema, usando HTTPS |
| **C. Chave SSH** | ⭐⭐⭐ Mais passos | Quem quer configurar uma vez e esquecer |
| **D. GitHub CLI (`gh`)** | ⭐⭐ Médio | Quem quer login guiado pelo terminal |

---

### 🅰️ Método A: Login pelo navegador (mais fácil)

No **Windows**, o instalador do Git já inclui o *Git Credential Manager*. Funciona assim:

1. Você usará um repositório com endereço **HTTPS** (começa com `https://github.com/...`).
2. Na **primeira vez** que fizer `git push` ou `git clone` de um repositório privado, uma **janela do navegador** abre pedindo para você entrar no GitHub.
3. Clique em **Sign in with your browser** (ou similar), faça login e clique em **Authorize**.
4. Pronto. O Git guarda a credencial e **não pergunta mais**.

> Se a janela não abrir ou der erro, use o Método B.

---

### 🅱️ Método B: Token de acesso pessoal (PAT)

O token é uma "senha especial" para o Git. **Você usa o token no lugar da senha.**

**Gerando o token:**

1. Faça login em <https://github.com>.
2. Clique no seu **ícone** (canto superior direito) → **Settings**.
3. No menu lateral esquerdo, vá até o final e clique em **Developer settings**.
4. Clique em **Personal access tokens** → **Tokens (classic)**.
5. Clique em **Generate new token** → **Generate new token (classic)**. (Pode pedir sua senha/2FA.)
6. Preencha:
   - **Note:** um nome para lembrar, como `meu-notebook`;
   - **Expiration:** escolha um prazo (ex.: 90 dias);
   - **Select scopes:** marque **`repo`** (dá acesso aos seus repositórios).
7. Clique em **Generate token**.
8. 🚨 **Copie o token agora** (começa com `ghp_...`). Ele **só aparece uma vez**. Guarde em lugar seguro, como um gerenciador de senhas.

**Usando o token:**

Na primeira vez que o Git pedir login (ao dar `git push`, por exemplo):

```
Username for 'https://github.com': seu-usuario
Password for 'https://seu-usuario@github.com': <cole o TOKEN aqui>
```

- **Username:** seu nome de usuário do GitHub.
- **Password:** cole o **token** (a tela **não mostra nada** enquanto você cola, é normal).

Para o Git **lembrar** a credencial e não pedir sempre:

```bash
git config --global credential.helper store
```

> ⚠️ O `store` salva o token em texto simples no seu PC. Em computador compartilhado, **não use**. No Windows e no macOS, o gerenciador de credenciais padrão já guarda de forma mais segura.

> 🔐 **Trate o token como senha.** Nunca poste em fóruns, nem coloque em arquivos do projeto. Se vazar, vá em *Settings → Developer settings → Tokens* e clique em **Delete** nele.

---

### 🅲 Método C: Chave SSH

Aqui você cria um par de "chaves": uma **privada** (fica no seu PC, secreta) e uma **pública** (você entrega ao GitHub). Depois, o login é automático e sem senha.

**1. Gere a chave** (no Git Bash / Terminal):

```bash
ssh-keygen -t ed25519 -C "seu-email@exemplo.com"
```

- Quando perguntar onde salvar, aperte **Enter** (aceita o padrão).
- Quando pedir uma *passphrase* (senha da chave), você pode digitar uma ou apertar Enter para deixar vazia. Uma passphrase é mais seguro.

**2. Inicie o agente SSH e adicione a chave:**

```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

**3. Copie a chave PÚBLICA** (o arquivo termina em `.pub`):

```bash
cat ~/.ssh/id_ed25519.pub
```

Selecione todo o texto exibido (começa com `ssh-ed25519` e termina com seu e-mail) e copie.

> ⚠️ **Nunca** compartilhe o arquivo **sem** `.pub` (`id_ed25519`). Esse é o privado!

**4. Cadastre no GitHub:**

1. GitHub → seu **ícone** → **Settings**.
2. No menu lateral, clique em **SSH and GPG keys**.
3. Clique em **New SSH key**.
4. **Title:** nome para lembrar (ex.: `Notebook pessoal`).
5. **Key:** cole a chave pública.
6. Clique em **Add SSH key** (pode pedir sua senha/2FA).

**5. Teste a conexão:**

```bash
ssh -T git@github.com
```

Na primeira vez pergunta se deve continuar (`yes`). Se tudo deu certo, aparece algo como:

```
Hi seu-usuario! You've successfully authenticated, but GitHub does not provide shell access.
```

🎉 Funcionou! (A frase "não fornece acesso shell" é normal.)

**Importante:** com SSH, os endereços dos repositórios têm o formato `git@github.com:seu-usuario/repo.git`, e **não** `https://...`.

---

### 🅳 Método D: GitHub CLI (`gh`)

O GitHub oferece uma ferramenta oficial de linha de comando que faz o login para você.

1. Instale em **<https://cli.github.com>** (siga as instruções para seu sistema).
2. No terminal:

```bash
gh auth login
```

3. Responda as perguntas (use as setas e Enter):
   - *GitHub.com*;
   - Protocolo: *HTTPS* (mais simples);
   - *Authenticate Git with your GitHub credentials?* → **Yes**;
   - *Login with a web browser* → copie o código de uso único que aparece, aperte Enter, cole no navegador e autorize.

4. Confira:

```bash
gh auth status
```

---

## 16. 🏗️ Criando um repositório no GitHub (pelo site)

Vamos criar um repositório na nuvem.

### Passo a passo

1. Faça login em <https://github.com>.
2. No canto superior direito, clique no botão **`+`** → **New repository**.
   (Ou acesse direto: <https://github.com/new>.)
3. Preencha:

| Campo | O que colocar |
|---|---|
| **Owner** | Sua conta (já vem selecionada) |
| **Repository name** | Nome do projeto, sem espaços (use `-`). Ex.: `meu-primeiro-repo` |
| **Description** | Opcional: uma frase explicando o projeto |
| **Public / Private** | **Public**: qualquer pessoa vê. **Private**: só você (e quem convidar) |
| **Add a README file** | Cria um README inicial (veja abaixo) |
| **Add .gitignore** | Escolhe um modelo de `.gitignore` para sua linguagem |
| **Choose a license** | Define as regras de uso do código (ex.: MIT) |

4. Clique em **Create repository**. 🎉

> 💡 **Público ou privado?** Para estudar e montar portfólio, público é ótimo. Para trabalhos que ainda não podem ser vistos, use privado. Nunca coloque senhas em nenhum dos dois.

### ⚖️ Marcar ou não "Add a README file"?

Isso muda o próximo passo:

| Situação | O que fazer |
|---|---|
| **Quero começar do zero pelo GitHub** | ✅ Marque o README → depois use [`git clone`](#181-clonando-um-repositório) |
| **Já tenho um projeto no meu PC** | ❌ **Não marque** → o repo fica vazio → siga a [seção 17](#17--enviando-seu-projeto-local-para-o-github) |

### O endereço (URL) do repositório

Na página do repositório, clique no botão verde **`< > Code`**. Aparecem as abas **HTTPS** e **SSH** com o endereço para copiar (use o formato do método de login que você configurou na seção 15):

```
HTTPS:  https://github.com/seu-usuario/meu-primeiro-repo.git
SSH:    git@github.com:seu-usuario/meu-primeiro-repo.git
```

### Tour pela página de um repositório

- **Code**: seus arquivos e pastas;
- **Issues**: lista de tarefas, bugs e ideias;
- **Pull requests**: pedidos de junção de código;
- **Actions**: automações (para depois);
- **Settings**: configurações (incluindo apagar o repositório);
- O arquivo **README.md** é exibido automaticamente abaixo dos arquivos.

### Editando direto pelo site (para testar)

Clique em um arquivo → ícone de **lápis** (✏️) → edite → **Commit changes...** → **Commit changes**. Isso cria um commit **no GitHub**. Seu computador **não** sabe disso ainda; você precisará de `git pull` (seção 18).

---

## 17. ⬆️ Enviando seu projeto local para o GitHub

Cenário: você já tem o `meu-primeiro-repo` no computador com commits, e criou um repositório **vazio** no GitHub (sem README).

**1. Entre na pasta do projeto:**

```bash
cd ~/curso-git/meu-primeiro-repo
```

**2. Ligue seu projeto ao repositório do GitHub** (troque a URL pela sua):

```bash
git remote add origin https://github.com/seu-usuario/meu-primeiro-repo.git
```

**3. Garanta que a branch se chama `main`:**

```bash
git branch -M main
```

**4. Envie:**

```bash
git push -u origin main
```

Se pedir login, use o método que você configurou na seção 15.

**5. Atualize a página do repositório no navegador.** Seus arquivos devem aparecer! 🎉

### O que cada comando fez

| Comando | Significado |
|---|---|
| `git remote add origin URL` | Cadastra o endereço remoto com o apelido `origin` |
| `git branch -M main` | Renomeia/garante que a branch é `main` |
| `git push -u origin main` | Envia a `main` e deixa configurado para os próximos envios |

Nas próximas vezes, basta:

```bash
git push
```

### Verificando os remotos

```bash
git remote -v
```

### Fluxo diário completo

```bash
git add .
git commit -m "Descrição do que mudou"
git push
```

---

## 18. ⬇️ Baixando projetos: clone, pull e fetch

### 18.1 Clonando um repositório

`git clone` baixa **todo o projeto e o histórico** e já configura o `origin`:

```bash
cd ~/curso-git
git clone https://github.com/usuario/repositorio.git
cd repositorio
```

Serve para: baixar seu próprio repo em outro computador, ou projetos de outras pessoas.

> Para clonar com um nome de pasta diferente: `git clone URL meu-nome`.

### 18.2 Atualizando: `pull` e `fetch`

```bash
git fetch     # baixa as novidades do remoto, mas NÃO mexe nos seus arquivos
git pull      # baixa E integra as novidades na sua branch atual
```

> 🧭 **Rotina saudável:** `git pull` **antes** de começar a trabalhar e `git push` **depois** de commitar.

### 18.3 Exemplo prático: sincronizando alterações feitas no site

1. No GitHub, edite o README pelo lápis e faça o commit.
2. No seu terminal, dentro do projeto:

```bash
git pull
```

3. Abra o README no computador: a edição veio junto! ✅

---

## 19. 📝 Escrevendo um bom README (Markdown)

O **README.md** é a "capa" do seu projeto: o primeiro arquivo que as pessoas veem no GitHub. Ele é escrito em **Markdown**, uma forma simples de formatar texto.

### Sintaxe básica

```markdown
# Título grande
## Subtítulo
### Subtítulo menor

Texto normal com **negrito** e *itálico*.

- Item de lista
- Outro item

1. Passo um
2. Passo dois

[Texto do link](https://exemplo.com)

![Texto alternativo da imagem](caminho/da/imagem.png)

`código dentro da frase`
```

Para blocos de código, use três crases com o nome da linguagem:

````markdown
```bash
git status
```
````

### Modelo de README

```markdown
# Nome do Projeto

Breve descrição do que o projeto faz.

## Como instalar

Passos para rodar o projeto.

## Como usar

Exemplos de uso.

## Autor

Seu nome e link do perfil.
```

> 💡 Dica: o VS Code tem **pré-visualização de Markdown**. Abra o arquivo e aperte `Ctrl + Shift + V`.

---

## 20. 🤝 Trabalhando em equipe: fork e pull request

### 20.1 Fluxo com colaboradores no mesmo repositório

Quando você tem **permissão de escrita** (foi adicionado como colaborador):

```
1. git pull                          (atualiza sua main)
2. git switch -c minha-feature       (cria sua branch)
3. ... edita e commita ...
4. git push -u origin minha-feature  (envia a branch)
5. Abre um Pull Request no GitHub
6. A equipe revisa e aprova
7. Merge pelo GitHub
8. git switch main && git pull       (atualiza seu PC)
```

### 20.2 Como adicionar colaboradores ao seu repositório

1. No repositório: **Settings** → **Collaborators** (ou *Collaborators and teams*).
2. Clique em **Add people**.
3. Digite o usuário ou e-mail da pessoa e confirme. Ela receberá um convite.

### 20.3 Abrindo um Pull Request (PR)

1. Faça `git push` da sua branch.
2. Abra o repositório no GitHub. Aparece uma faixa amarela **Compare & pull request**. Clique nela. (Ou vá em *Pull requests → New pull request*.)
3. Escreva um **título** claro e uma **descrição** do que mudou e por quê.
4. Clique em **Create pull request**.
5. Quem revisa pode comentar, pedir mudanças ou aprovar. Para finalizar: **Merge pull request** → **Confirm merge**.

### 20.4 Fork: contribuindo com projetos de terceiros

Quando você **não tem permissão** de escrita (projetos open source, trabalhos de colegas):

1. Abra o repositório da pessoa e clique em **Fork** (canto superior direito). Isso cria **uma cópia na sua conta**.
2. Clone **o seu fork**:

```bash
git clone https://github.com/SEU-USUARIO/repositorio.git
```

3. Crie uma branch, faça alterações, commite e dê push:

```bash
git switch -c correcao-erro-digitacao
# ... edita ...
git add .
git commit -m "Corrige erro de digitação no README"
git push -u origin correcao-erro-digitacao
```

4. No GitHub, abra um **Pull Request** do seu fork para o repositório original.

> 🌍 Um ótimo primeiro passo no open source: corrigir um erro de digitação em uma documentação.

---

# PARTE 4: FECHAMENTO

## 21. 🆘 Erros comuns e como resolver

| Mensagem / situação | O que significa | Como resolver |
|---|---|---|
| `fatal: not a git repository` | Você não está dentro de um repositório | Use `pwd` e `cd` para entrar na pasta certa, ou `git init` |
| `command not found: git` | Git não instalado ou terminal aberto antes da instalação | Reinstale e **reabra** o terminal |
| `Author identity unknown` / `Please tell me who you are` | Falta configurar nome e e-mail | Refaça a [seção 6](#6--configurando-o-git-pela-primeira-vez) |
| `Authentication failed` / `Password authentication is not supported` | Usou a senha do site em vez de token/login | Siga a [seção 15](#15--fazendo-login-conectando-o-git-à-sua-conta) (token, SSH ou navegador) |
| `Permission denied (publickey)` | Chave SSH não configurada/cadastrada | Refaça o Método C; teste com `ssh -T git@github.com` |
| `remote origin already exists` | Já existe um `origin` | `git remote -v` para ver; `git remote set-url origin NOVA-URL` para trocar |
| `failed to push some refs` / `rejected (non-fast-forward)` | O remoto tem commits que você não tem | `git pull` e depois `git push` |
| `nothing to commit, working tree clean` | Não há nada alterado | Não é erro! Edite um arquivo antes |
| `Your local changes would be overwritten` | Alterações pendentes impedem a troca/pull | Faça commit, ou `git stash` para guardá-las |
| Preso no editor (Vim) após `git commit` | Esqueceu o `-m` | `Esc`, depois `:q!` + Enter, e refaça com `-m` |
| Commitei um arquivo que não devia | Esqueceu o `.gitignore` | `git rm --cached arquivo`, adicione ao `.gitignore` e commite |
| Commitei uma **senha/token** | Credencial exposta | **Revogue/troque a credencial imediatamente**. Apagar o commit não basta |

> 🧯 **Na dúvida:** rode `git status`. Ele quase sempre indica o caminho.

---

## 22. ✅ Boas práticas

- 🔹 **Commits pequenos e frequentes**, cada um com um propósito.
- 🔹 **Mensagens claras** (seção 9).
- 🔹 **`git status` antes de `git add .`**, para saber o que está adicionando.
- 🔹 **Nunca commite segredos** (senhas, tokens, `.env`).
- 🔹 **Uma branch por tarefa**, com nomes descritivos: `feature/login`, `fix/erro-calculo`.
- 🔹 **Não reescreva histórico já compartilhado** (evite `reset --hard` e `push --force` em branches de equipe).
- 🔹 **`pull` antes de começar** e **antes de dar `push`**.
- 🔹 **Tenha um README e um `.gitignore`** desde o início.
- 🔹 **Use 2FA** na conta do GitHub.

---

## 23. 📝 Exercícios

### Exercício 1: Conta e login
1. Crie sua conta no GitHub e ative o 2FA.
2. Instale o Git e configure nome e e-mail.
3. Configure um método de login (A, B, C ou D) e teste.

### Exercício 2: Primeiros commits
1. Dentro de `curso-git`, crie a pasta `treino-git` e rode `git init`.
2. Crie `sobre-mim.txt` com seu nome e faça o primeiro commit.
3. Adicione seu curso e cidade e faça um segundo commit.
4. Veja os dois commits com `git log --oneline`.

### Exercício 3: Corrigindo erros
1. Edite o arquivo **sem** `add` e descarte com `git restore`.
2. Edite de novo, faça `add` e tire da staging com `git restore --staged`.
3. Faça um commit com mensagem errada e corrija com `git commit --amend`.

### Exercício 4: Branches
1. Crie a branch `hobbies` e adicione `hobbies.txt`.
2. Volte à `main` e observe que o arquivo sumiu.
3. Faça o merge da `hobbies` na `main`.

### Exercício 5: Conflito proposital 😈
1. Na `main`, altere a primeira linha do `sobre-mim.txt` e commite.
2. Crie a branch `conflito` **a partir do commit anterior** (`git switch -c conflito HEAD~1`), altere a **mesma linha** de outra forma e commite.
3. Volte à `main` e faça `git merge conflito`.
4. Resolva o conflito manualmente.

### Exercício 6: Meu primeiro repositório no GitHub
1. Crie no GitHub um repositório **vazio** chamado `treino-git` (sem README).
2. Conecte seu projeto local com `git remote add origin ...`.
3. Envie com `git push -u origin main`.
4. Confira os arquivos no navegador.

### Exercício 7: Sincronizando
1. Edite o README **pelo site do GitHub** e faça o commit.
2. No seu PC, rode `git pull` e confira a alteração.

### Exercício 8: Clone
1. Em outra pasta, clone o seu repositório com `git clone`.
2. Faça uma alteração, commite e dê `push`.
3. Volte à pasta original e rode `git pull`.

### Exercício 9: Colaboração
1. Peça a um colega para dar **fork** no seu repositório.
2. Ele altera algo em uma branch e abre um **pull request**.
3. Você revisa, comenta e faz o **merge**.

---

## 24. 🧾 Cola de comandos

### Terminal

| Objetivo | Comando |
|---|---|
| Onde estou? | `pwd` |
| Listar | `ls` / `ls -a` |
| Entrar em pasta | `cd pasta` |
| Voltar | `cd ..` |
| Criar pasta | `mkdir nome` |
| Criar arquivo | `touch arquivo` |
| Limpar tela | `clear` |

### Git

| Objetivo | Comando |
|---|---|
| Configurar nome | `git config --global user.name "Nome"` |
| Configurar e-mail | `git config --global user.email "email"` |
| Iniciar repositório | `git init` |
| Clonar repositório | `git clone URL` |
| Ver situação | `git status` |
| Adicionar arquivo | `git add arquivo` |
| Adicionar tudo | `git add .` |
| Commitar | `git commit -m "mensagem"` |
| Ver histórico | `git log --oneline --graph --all` |
| Ver alterações | `git diff` / `git diff --staged` |
| Descartar alteração | `git restore arquivo` |
| Tirar da staging | `git restore --staged arquivo` |
| Corrigir último commit | `git commit --amend` |
| Desfazer com novo commit | `git revert <hash>` |
| Listar branches | `git branch` |
| Criar e mudar de branch | `git switch -c nome` |
| Mudar de branch | `git switch nome` |
| Juntar branches | `git merge nome` |
| Apagar branch | `git branch -d nome` |
| Ver remotos | `git remote -v` |
| Adicionar remoto | `git remote add origin URL` |
| Trocar URL do remoto | `git remote set-url origin URL` |
| Enviar | `git push` |
| Enviar 1ª vez | `git push -u origin nome-branch` |
| Baixar e integrar | `git pull` |
| Só baixar | `git fetch` |
| Guardar alterações temporariamente | `git stash` / `git stash pop` |
| Cancelar merge | `git merge --abort` |

---

## 25. 📖 Glossário

| Termo | Significado |
|---|---|
| **Branch** | Linha paralela de desenvolvimento |
| **Clone** | Cópia completa de um repositório |
| **Commit** | Registro de um conjunto de alterações no histórico |
| **Conflito** | Quando o Git não consegue juntar alterações automaticamente |
| **Fork** | Cópia de um repositório de outra pessoa para a sua conta |
| **Git** | Programa de controle de versão |
| **GitHub** | Plataforma online que hospeda repositórios Git |
| **HEAD** | Ponteiro para onde você está no histórico |
| **HTTPS / SSH** | Dois jeitos de se conectar ao GitHub |
| **Markdown** | Linguagem simples de formatação de texto (`.md`) |
| **Merge** | Juntar o conteúdo de duas branches |
| **Origin** | Apelido padrão do repositório remoto |
| **PAT (token)** | Senha especial usada pelo Git no lugar da senha da conta |
| **Pull** | Baixar e integrar alterações do remoto |
| **Pull Request** | Pedido de revisão/junção de uma branch |
| **Push** | Enviar commits locais para o remoto |
| **README** | Arquivo de apresentação do projeto |
| **Repositório** | Projeto com seu histórico gerenciado pelo Git |
| **Staging area** | Área onde se preparam as mudanças para o commit |
| **Terminal** | Janela para controlar o computador por comandos |
| **Working directory** | A pasta onde você edita os arquivos |

---

## 26. 📚 Para continuar estudando

- 📕 **Pro Git** (livro oficial e gratuito, com versão em português): <https://git-scm.com/book/pt-br/v2>
- 📘 **Documentação do Git:** <https://git-scm.com/doc>
- 📙 **GitHub Docs:** <https://docs.github.com/pt>
- 🎮 **Learn Git Branching** (jogo interativo): <https://learngitbranching.js.org/?locale=pt_BR>
- 🧪 **Próximos tópicos:** `git rebase`, `git cherry-pick`, `git stash`, `git tag`, GitHub Actions, GitHub Pages, *Conventional Commits*, *Git Flow*.

---

## 👨‍🏫 Considerações finais

Git parece difícil no começo porque tem muitos comandos, mas **90% do seu dia a dia será este ciclo**:

```bash
git pull
git status
git add .
git commit -m "mensagem clara"
git push
```

Pratique, erre num repositório de teste e consulte o `git status` sempre que ficar em dúvida. 💪

---

📌 *Material produzido para fins educacionais. Contribuições são bem-vindas via Pull Request!*
Conferido - Profa. Eliane Ribeiro
