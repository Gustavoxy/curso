CONFIGURANDO O GIT COM NOSSAS INFORMAÇÕES PESSOAIS
sempre que algo for alterado no projeto, a alteracao será associada ao usuário do git.
(Quem foi que fez o que no projeto)

SABER VERSAO DO GIT
git --version

OUTROS COMANADOS
git help

CONFIGURAR NOME DO USUÁRIO (MEU NOME)
git config --global user.name "MeuNome" (nao mostrará nada. Alteracao acontecerá de forma interna)

CONFIGURAR EMAIL
git config --global user.email + "meu@email.com"

QUAL EDITOR ESTOU USANDO
git config --global core.editor + NOMEdoEDITOR

SABER O USUARIO CADASTRADO NO GIT
git config user.name

SABER O EMAIL CADASTRADO
git config user.mail.

SABER TUDO
git config --list

NO PROMPT, IR PARA A PASTA DO PROJETO.
para ver a estrutura da pasta, digita: tree /f

CRIAR PROJETO
navegar até a pasta do projeto. Criar pasta: mkdir nomePasta

INICIAR O REPOSITORIO
git init - Cria um repositório vazio

********O GIT RODA LOCALMENTE E OS PROJETOS SÃO SINCRONIZADOS NO GITHUB********

BRANCH - São VERSÕES DIFERENTES do meu sistema. BRANCH PRINCIPAL é a MASTER. Que é a versao principal do sistema.
É possível SEPARAR um sistema/projeto em várias Branchs.
Ex: A Branch principal precisa ser atualizada. Para tanto, copiamos a versão principal para ser uma segunda Branch a qual será utilizada pelos programadores para ser atualizada enquanto a primeira Branch (Principal/Master) continuará rodando sem problemas.

COMMIT - Commitar, Dar um Commit, Dar Commits = Quando fazemos alterações, criamos arquivos novos, trabalhamos no sistema.
COMMIT - Quando ENVIAMOS ALTERAÇÕES para o Git. MODIFICA os arquivos.O Git Não armazena TODOS os arquivos. Apenas MODIFICA os modifica. 
Ex: Alterei um arquivo que contém mais linhas que o arquivo master. O Git adiciona essas linhas ao arquivo da Branch. Caso outra pessoa altere o mesmo arquivo, o Git realiza outra modificação no mesmo arquivo e junta as duas modificações em um só arquivo.

COMMIT - Enviar para o Git as modificações que fizemos ACOMPANHADO de um COMENTÁRIO que explica o que foi alterado.
Quando COMMITAMOS, enviamos também uma mensagem/comentário junto ao COMMIT que explica as alterações.

Arquivo PRINCIPAL de um Projeto é o README.txt ou README.md = O qual conterá instruções, comentários e como utilizar e configurar os arquivos de projeto, qual é a versão que se encontra o projeto. Contém informações descritivas.

***TRABALHANDO NO BRANCH PRINCIPAL (NA PASTA DO PROJETO)***

Varrer a pasta e verificar o que foi adicionado, modificado, deletado etc...
git status - Vai mostrar no branch master os arquivos, se houve algum commit e os arquivos "Untracked" (Arquivos que o Git nunca viu ou não está trackeando/monitorando os arquivos).

Arquivos Untrackeds devem ser monitorados pelo Git.
Setar o Git para monitorar os arquivos - git add NOMEaRQUIVO /ou git add -A(Maiusc) (Vai monitorar TODOS arquivos n trakeados)
O Git vai mostrar as alterações no Branch Master e mostrar os arquivos adicionados e modificados.

COMMITAR os arquivos = git commit -m "Comentário do Commit" 

LOG DE COMMITS - git log = Vai mostrar em qual Branch estamos e quais foram os commits e quem commitou cada um deles.

1º GIT STATUS (Prestar atenção em qual Branch estamos)
Ao CRIAR, ALTERAR, MODIFICAR, TRABALHAR NO PROJETO, Podemos ver pelo Git TUDO que foi alterado na pasta do projeto com
o comando git status. Vai mostrar tudo e o que precisa ser commitado, tudo que foi modificado e todos os Untracked files que precisam ser Trackeados/monitorados.

2º GIT ADD -A ou GIT ADD + NOmeFILE
Para trakealos e adicionar ao monitoramento, basta utilizar o comando git add -A ou git add nomeArquivo.
Em seguida, o Git mostrarás TODAS as mudanças.

3º GIT COMMIT -M "COMENTÁRIO DO COMMIT"
É preciso commitar os novos arquivos que foram criados, alterados e deletados para o projeto. Os arquivos do meu PC serão disponibilizados para a Branch (no GITHUB/BitBucket) onde estamos trabalhando e disponibilizados para a equipe. Portanto, commitar. git commit -m "Comentário sobre o commit".

COMANDOS IMPORTANTES

git log
Mostra todo o histórico de tudo que foi feito e por quem foi feito.
um hash será exibido. os 7 primeiros caractéres do hash são os MAIS IMPORTANTES.
Mostrará o Branch onde estamos. Ex: (HEAD -> master).

git branch
Lista TODOS OS BRANCHS que temos no projeto e vai marcar com um * em qual branch nós estamos.

git add -am
O Git passa a trackear(Junta os arquivos ao projeto) todos os arquivos e comita os arquivos ao mesmo tempo.


*****REVERTENDO ALTERACOES*****
git reset

3 FORMAS 
Copiar HASH do commit para o qual desejo voltar.
git reset --soft + hash = Volta p o branch copiado, c acesso aos arquivos criados após o commit já Trakeados no projeto.
git reset --mixed + hash = Volta para o branch copiado, com acesso aos arquivos criados após o commit mas fora do projeto.
git reset --hard + hash = volta para o branch copiado e desconsidera TUDO que um dia existiu depois dele.

*****CRIANDO E ALTERNANDO BRANCHS*****

Um novo Branch é criado a partir do Branch principal com todos os arquivos que continham nele. 
Os arquivos da branch master são importados pela nova Branch.
A partir disso, haverá DOIS históricos de commits para cada Branch. Os arquivos de uma Branch não irão se misturar com outras Branchs.
git branch + nomeDaBranch = cria uma nova branch.

Alternar de uma branch para outra = git checkout + nomeDaBranch.