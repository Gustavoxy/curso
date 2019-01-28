CONFIGURANDO O GIT COM NOSSAS INFORMAÇÕES PESSOAIS sempre que algo for alterado no projeto, a alteracao será associada ao usuário do git. (Quem foi que fez o que no projeto)

SABER VERSAO DO GIT git --version

OUTROS COMANADOS git help

CONFIGURAR NOME DO USUÁRIO (MEU NOME) git config --global user.name "MeuNome" (nao mostrará nada. Alteracao acontecerá de forma interna)

CONFIGURAR EMAIL git config --global user.email + "meu@email.com"

QUAL EDITOR ESTOU USANDO git config --global core.editor + NOMEdoEDITOR

SABER O USUARIO CADASTRADO NO GIT git config user.name

SABER O EMAIL CADASTRADO git config user.mail.

SABER TUDO git config --list

NO PROMPT, IR PARA A PASTA DO PROJETO. para ver a estrutura da pasta, digita: tree /f

CRIAR PROJETO navegar até a pasta do projeto. Criar pasta: mkdir nomePasta

INICIAR O REPOSITORIO git init - Cria um repositório vazio

O GIT RODA LOCALMENTE E OS PROJETOS SÃO SINCRONIZADOS NO GITHUB

BRANCH - São VERSÕES DIFERENTES do meu sistema. BRANCH PRINCIPAL é a MASTER. Que é a versao principal do sistema. É possível SEPARAR um sistema/projeto em várias Branchs. Ex: A Branch principal precisa ser atualizada. Para tanto, copiamos a versão principal para ser uma segunda Branch a qual

será utilizada pelos programadores para ser atualizada enquanto a primeira Branch (Principal/Master) continuará rodando

sem problemas.

COMMIT - Commitar, Dar um Commit, Dar Commits = Quando fazemos alterações, criamos arquivos novos, trabalhamos no sistema. COMMIT - Quando ENVIAMOS ALTERAÇÕES para o Git. MODIFICA os arquivos.O Git Não armazena TODOS os arquivos. Apenas MODIFICA

os modifica. Ex: Alterei um arquivo que contém mais linhas que o arquivo master. O Git adiciona essas linhas ao arquivo da Branch. Caso

outra pessoa altere o mesmo arquivo, o Git realiza outra modificação no mesmo arquivo e junta as duas modificações em um

só arquivo.

COMMIT - Enviar para o Git as modificações que fizemos ACOMPANHADO de um COMENTÁRIO que explica o que foi alterado. Quando COMMITAMOS, enviamos também uma mensagem/comentário junto ao COMMIT que explica as alterações.

Arquivo PRINCIPAL de um Projeto é o README.txt ou README.md = O qual conterá instruções, comentários e como utilizar e

configurar os arquivos de projeto, qual é a versão que se encontra o projeto. Contém informações descritivas.

TRABALHANDO NO BRANCH PRINCIPAL (NA PASTA DO PROJETO) git status Varre a pasta e verificar o que foi adicionado, modificado, deletado etc... git status - Vai mostrar no branch master os arquivos, se houve algum commit e os arquivos "Untracked" (Arquivos que o Git

nunca viu ou não está trackeando/monitorando os arquivos).

Arquivos Untrackeds devem ser monitorados pelo Git. Fazer o Git monitorar os arquivos ("Anexar" os arquivos ao projeto) - git add + nomeArquivo /ou git add -A(Maiúsculo) (Vai

monitorar TODOS arquivos NÃO trakeados) O Git vai mostrar as alterações no Branch Master e mostrar os arquivos adicionados e modificados.

COMMITAR os arquivos = git commit -m "Comentário do Commit"

LOG DE COMMITS - git log = Vai mostrar em qual Branch estamos e quais foram os commits e quem commitou cada um deles.

1º GIT STATUS (Prestar atenção em qual Branch estamos) Ao CRIAR, ALTERAR, MODIFICAR, TRABALHAR NO PROJETO, Podemos ver pelo Git TUDO que foi alterado na pasta do projeto com o comando git status. Vai mostrar tudo e o que precisa ser commitado, tudo que foi modificado e todos os Untracked files

que precisam ser Trackeados/monitorados.

2º GIT ADD -A ou GIT ADD + NOmeFILE Para trakealos e adicionar ao monitoramento, basta utilizar o comando git add -A ou git add nomeArquivo. Em seguida, o Git mostrarás TODAS as mudanças.

3º GIT COMMIT -M "COMENTÁRIO DO COMMIT" É preciso commitar os novos arquivos que foram criados, alterados e deletados para o projeto. Os arquivos do meu PC serão

disponibilizados para a Branch (no GITHUB/BitBucket) onde estamos trabalhando e disponibilizados para a equipe. Portanto,

commitar. git commit -m "Comentário sobre o commit".

COMANDOS IMPORTANTES

git log Mostra todo o histórico de tudo que foi feito e por quem foi feito. um hash será exibido. os 7 primeiros caractéres do hash são os MAIS IMPORTANTES. Mostrará o Branch onde estamos. Ex: (HEAD -> master).

git branch Lista TODOS OS BRANCHS que temos no projeto e vai marcar com um * em qual branch nós estamos.

git add -am O Git passa a trackear(Junta os arquivos ao projeto) todos os arquivos e comita os arquivos ao mesmo tempo.

REVERTENDO ALTERACOES git reset

3 FORMAS Copiar HASH do commit para o qual desejo voltar. git reset --soft + hash = Volta p o branch copiado, c acesso aos arquivos criados após o commit já Trakeados no projeto. git reset --mixed + hash = Volta para o branch copiado, com acesso aos arquivos criados após o commit mas fora do projeto. git reset --hard + hash = volta para o branch copiado e desconsidera TUDO que um dia existiu depois dele.

CRIANDO E ALTERNANDO BRANCHS
git branch + nomeDaBranch = cria uma nova Branch 
git checkout + nomeDaBranch = alterna para a Branch

Um novo Branch é criado a partir do Branch principal com todos os arquivos que continham nele. Os arquivos da branch master são importados pela nova Branch. A partir disso, haverá DOIS históricos de commits para cada Branch. Os arquivos de uma Branch não irão se misturar com outras Branchs. git branch + nomeDaBranch = cria uma nova branch.

Alternar de uma branch para outra = git checkout + nomeDaBranch RESUME = Posso manter versões diferentes do meu sistema funcionando em Branchs diferentes.

DIFENÇA ENTRE ARQUIVOS COMMITADOS E ARQUIVOS DO MEU PC (OFFLINE) git diff - tecla Q, sai do histórico diff

Por exemplo: Quero saber quais são as diferenças entre os arquivos que foram commitados e os arquivos que estão em meu computador. Quero saber o que foi alterado, criado, excluído etc... ANTES DE COMMITAR, quero saber o que foi feito. Para tanto, usamos o comando git diff. Saber SOMENTE O NOME dos arquivos modificados: git diff --name-only Saber qual foi a alteração em um arquivo específico: git diff + nomeArquivo Ex: git diff style.css OU git diff js.js VOLTAR um arquivo AO O QUE ERA ANTES : git checkout HEAD (meu Branch ATUAL) -- nomeArquivo. Ou seja: git checkout + nomeArquivo volta a versão de algum arquivo ao estado anterior. Ou git checkout pode voltar a versão de algum branch, commit ou arquivo específico.

******REPOSITORIO LOCAL x REPOSITORIO REMOTO******

Rep. LOCAL = Na minha máquina, por exemplo.
Rep. REMOTO = GitGHub, BitBucket...

Na minha conta no GitHub, crio um novo repositório o qual terá uma URL que poderá ser compartilhada.
PROXIMO PASSO: Enviar nosso repositório local para o repositório remoto. Transferir alterações, arquivos, projetos
do nosso computador para o GitHub ou BitBucket.

-Baixar e instalar o GitBash - Terminal específico do Git.
NECESSÁRIO Gerar SSH KEY no GitHub para podermos enviar o Rep.local para Rep.remoto no GitHub.
SSH KEY identifica o usuário e dá permissão para fazer alterações no Rep. Remoto.
Usando SSH Key, eu posso me CONECTAR e autenticar no GitHub sem solicitações de usuário ou senha.

CRIAR SSG => https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/#platform-windows

O passo-a-passo acima vai criar duas chaves. Uma Pública e uma Privada. "id_rsa" e "id_rsa.pub".

Vá até a pasta padrão onde o Git criou as chaves e "arraste" a chave pública para o editor de codigo para ver o conteúdo.
COPIAR o conteúdo da chave, ir até o seu GitHub e vá até SETTINGS do usuário do GitHub.
Em PERSONAL SETTINGS >> SSH and GPG Keys, CLICAR em "New SSG Key" - Dar um Title para a chave e colar o conteúdo da chave
que foi copiado no editor.
Agora temos a minha chave pública cadastrada no GitHub e a chave privada no nosso computador.
Quando enviarmos arquivos do Rep.Local para o Rep.remoto as duas chaves vão bater e o acesso/alterações serão permitidas.


******ENVIANDO(ENVIO) arquivos de Rep.Local para Rep.Público******

ADD um Repositório Remoto ao meu Rep.Local - Ficarão ligados.

SE NÃO HA REPOSITÓRIO NO GIT:
CRIAMOS e add o repostório criado no GitHub ao repositorio local como a seguir:

…or create a new repository on the command line

echo "# curso" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin(NOME) https://github.com/Gustavoxy/curso.git
git push -u origin master
--------------------------------------------------------------

SE, já temos um Repositório no GitHub...

…or push an existing repository from the command line

git remote add origin(NOME) https://github.com/Gustavoxy/curso.git
git push -u origin master | "origin" que é um NOME que dou, é o DESTINO do push. "master" é a BRANCH que selecionamos.
Ex:
git push -u + destino + nomeBranch | git push -u origin Branch2 

SINCRONIZAR DIRETÓRIOS: git pull
CASO o git push não funcione, será preciso SINCRONIZAR o Rep.Remoto com o Rep.Loca. Para tanto, usar o comando: git pull.

CASO o git pull NÃO FUNCIONE, SALVE TUDO, delete o dirório no GitHub e suba o projeto novamente para um novo repositório criado no GitHub.
--------------------------------------------------------------

Para ver os repositórios conectados: 
git remote
git remote -v | vai mostrar (fetch) e (push)
(fetch) Capacidade que eu tenho de puxar conteúdos do Rep.Remoto para o Rep.Local.
(push) Levar os arquivos do meu Rep.Local para o Rep.Remoto

*****IGONORAR ARQUIVOS*****

Ex: Não quero que um determinado arquivo vá para o diretório remoto e que seja desconsiderado pelo Git durante o desenvolvimento.
Na pasta do projeto, criar um arquivos chamado ".gitignore".
Dentro do arquivo ".gitignore", especificar(escrevendo) os arquivos os quais devem ser ignorados pelo Git.
Ignorar umas patas inteira, Ex: nomePasta/*
Pode ser diversos tipos de arquivos, demais estensões e pastas.
Dessa forma, os arquivos especificados no .gitignore, ficam fora do repositório.

REMOVER PASTA DO DIRETORIO:

Primeiro certifique-se que o seu repositório está sincronizado com o repositório remoto: $ git pull origin master, (supondo que o branch seja master).
Então remova a pasta localmente.
Agora faça um commit das modificações: $ git commit -m "Removi as pastas"
Sincronize com repositório remoto: $ git push origin master.

*****GIT REVERT*****
Ex: Fiz um commit com algum problema e quero voltar. git revert + hash

Volta ao estado anterior do commit sem perder o commit posterior. REVERTE O COMMIT.
Pego a Hash do commit:
git revert --no-edit + hash do commit

As linhas que eu adicionei, serão removidas. Linhas que eu editei, serão revertidas.
NÃO PERDEMOS O COMMIT que fizemos errado.

*****DELETAR BRANCHS REMOTOS*****
Para ter mais de um branch no repositório do GitHub, basta alternar, no Git, para o segundo branch e fazer o push desse branch para o GitHub.

DELETAR a branch REMOTO do GitHub:
git push origin(nome/DESTINO) + :nomeBranch
Ex: "git push origin :testes"
Push com "dois pontos" antes do nomeBranch > Deleta.

DELETAR branch LOCAL:
Alternar para outra branch que NÃO será deletada e, a partir dessa branch, deletar a branch que deseja.

*****PUXANDO ALTERACOES DE OUTRAS PESSOAS (pull)*****
git log - para verificar como estão os commits

VERMELHO - REMOTO
AZUL - LOCAL

Caso algum colaborador faça alguma alteração nos arquivos do repositório, preciso puxar essas alterações.
Alteraçoes podem ser feitas diretamente no repositório remoto em "Create new file" ou por um push feito pelo Git.

Esses arquivos e alterações, podem não existir no meu projeto.
Preciso TRAZER os arquivos e alteraçoes do Rep.Remoto para o meu Rep.Local. COMANDO IMPORTANTE que sempre devo fazer antes de continuar o projeto para atualizar meu Rep.Local.

git pull origin + nomeBranch

Ex: "git pull origin master"
Em seguida, os arquivos serao trazidos para o Rep.Local.
E então, os repositório, Remoto e Local estarão atualizados e sincronizados.
IMPORTANTE! = Antes de fazer um PUSH, sempre faça um PULL antes.

*****CLONANDO REPOSITORIOS REMOTOS*****

CRIA uma CÓPIA do repositório. Porém, como posso não ser o dono do Rep, não conseguirei fazer alterações diretamente no repositório.
Ex: Achei um projeto legal e quero clona-lo.
Vou copiar o link do Rep.Remoto e vou no meu terminal do Git:
git clone + "url do projeto"
"git clone https://github.com/Gustavoxy/curso.git"

----Contribuindo com outros repositórios (fork/pull request)----

Contribuir com projetos que não são nossos.

Quando o projeto não é nosso, fazemos um "FORK".
No GitHub, clicar em "FORK"
Com o projeto "Forkado", consigo clonar e fazer alterações.