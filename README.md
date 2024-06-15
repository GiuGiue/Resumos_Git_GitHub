# Resumos Git e GitHub

Construi esse README com a finalidade de armazenar resumos realcionados ao versionamento de código com Git e GitHub, servindo como material de apoio para revisão.

## Documentações
- [Documentação Git](https://git-scm.com/docs/git/pt_BR)
- [Documentação GitHub](https://docs.github.com/pt)

## Como configurar o Git Bash

Para baixar o git no Windows basta ir no site [Git for Windows](https://gitforwindows.org), que é um projeto de uma comunidade que visa facilitar o processo de instalação do Git para os usuários do Windows, encontrar e reparar bugs na versão do Git do Windows. Baixando por esse site, no processo de instalação basta clicar em "Next" em todas as etapas.

Obviamente também pode ser baixado no próprio site do [Git](https://www.git-scm.com/downloads), onde possui opções para outros sistemas operacionais e com os devidos passos a passos. Se optar por instalar pelo site oficial do Git, fique atento no processo de instalação ao marcar as opções, esse [Vídeo](https://www.youtube.com/watch?v=mmcOw2ynWEs) ensina bem o processo.

O Git deve ser configurado para que tudo funcione perfeitamente. Deve ser criado uma pasta, e dentro da pasta ao clicar com o botão direito irá aparecer a opção "Open the Git Bash Here" e a selecione. Irá abrir o terminal do Git Bash com o caminho do diretório que você abriu. Segue os comandos:

1. Primeiro verifique se está tudo certo com a versão do Git: ```git version``` Se apareceu o número da versão e não apareceu nenhuma mensagem de erro é porque está tudo OK!
2. Coloque o mesmo nome que você registrou no GitHub dentro das aspas após o comando: ```git config --global user.name "SeuNomeDeUsuarioDoGithub"```
3. Coloque o mesmo e-mail que foi registrado na sua conta do GitHub dentro das aspas após o comando:```git config --global user.email "seuemail.dogithub@gmail.com"```
4. Vefique se seu email e nome registrado está dentro da lista de configuração:```git config --list``` Se apareceu é porque está tudo OK!

PRONTO! Agora seu Git Bash está ligado a sua conta do GitHub!

### Comandos básicos para manipular diretórios pelo cmd

|Voltar para a pasta anterior|Criar diretório (pasta)|Entrar no diretório|
|-----------|-----------|------------|
|```cd ..```|```mkdir Nome_Do_Diretório```|```cd Nome_Do_Diretório```|

- Voltar para a pasta anterior: ```cd ..```
Se você quer entrar na pasta anterior do caminho do diretório basta utilizar este comando.
- Criar diretório (pasta): ```mkdir```
Para fazer uma pasta pelo terminal basta digitar o comando e o nome que você deseja dar ao diretório.
- Entrar no diretório: ```cd```
Nota-se que tudo que envolve em entrar em diretórios é usado anteriormente o comando ```cd```. É importante colocar o caminho logo em seguida.

*Por que é importante saber esses comandos?*
Para criar repositórios, e na realização de suas atualizações, é muito importante ficar atento em qual diretório você está, se não pode ocorrer alguns problemas.

### Comandos do git importantes para diretórios

|Mostrar status|Ignorar diretório|
|-----------|-----------|
|```git status```|```touch .gitignore```|

- Mostrar status: ```git status```
Esse comando pode ser utilizado para verificar o status do commit na pasta, da árvore de trabalho e área de preparação. A área de preparação (ou index) é onde será preparado os arquivos que serão salvos em um commit. 
- Ignorar diretório: ```touch .gitignore```
Esse comando irá criar um arquivo .gitignore, por isso é importante está dentro do diretório desejado. O diretório será ignorado e não será passado para o repositório.

## Mexendo no Git
### Criando um repositório local
1. Novo repositório
Esse comando irá criar um novo repositório, dessa forma irá criar um subdiretório .git . O que permite a criação de uma ramificação principal
```
git init
```
2. Criar um arquivo README.md
```
touch README.md
```
Dica: Uma boa ferramenta para edição de Markdown (.md) é o [Readme so](readme.so), pois permite pré-visualização. Mas também é possível editar no próprio GitHub, sendo possível até utilizar uma ferramenta própria para edição apertando a tecla de atalho "."

3. Adicionando o arquivo na área de preparação
O texto feito no editor do [Readme so](readme.so) pode ser colado no arquivo .md local por meio do bloco de notas. Após isso o arquivo precisa ser adicionado na área de preparação. No Git Bash insira o comando:

```
git add README.md
```

Observe que "README.md" é o nome do arquivo Markdown. Então você irá colocar o nome de acordo com o arquivo. Nestes exemplos está sendo criado um readme como nome padrão.

O arquivo foi adicionado, e o status pode ser verificado novamente pelo comando ```git status``` como mostrado anteriormente.

4. Criando um commit
As alterações feitas precisam ser commitadas.

```
git commit -m"primeiro commit"
```

O ```-m``` indica mensagem, e ela deverá ser digitada entre as aspas. Essa função serve para adicionar uma breve descrição do que foi feito.

- Visualizar o commit criado
Será mostrado o hash do commit criado, o autor, a data e a mensagem.
```
git log
```
Se o status for verificado novamente mostrará que a árvore de trabalho está limpa. Lembrando que o status da pasta não é reconhecido se estiver vazio, assim será mostrado que não há nada na árvore de trabalho.

## Subir repositório local pronto para o repositório remoto

1. Adicionando a URL do repositório remoto
```
git remote add origin https://github.com/seugit/nomedorepositorio.git
```
A URL adicionado após o ```origin``` é um exemplo.

2. Adicionando todos os arquivos do repositório
```
git add .
```
3. Fazendo o push para o repositório remoto
```
 git push --set-upstream origin main
```

### Clonando um repositório
Todo processo de colocar comandos envolve o caminho correto do diretório. Então para essa estapa faça uma nova pasta e clique com o botão direito do mouse dentro da pasta e selecione a opção "Open the Git Bash Here", irá abrir o terminal do Git com o caminho do diretório criado. Com o link do repositório desejado do GitHub, no terminal coloque o comando:
```
git clone https://github.com/GiuGiue/test.git
```
Acrescente o link do repositório desejado após o comando. Este é um link fctício, substitua pelo link de um repositório existente. 

## Subindo atualizações dos arquivos
É possível observar que esse processo é muito semelhante aos outros. A diferença que será excluída as etapas de criação de arquivos e diretórios, ligação entre o repositório local e remoto, pois estas etapas em tese já devem ter sido realizadas para que ocorra uma atualização do repositório.

1. Verificar o ```git status```:
A árvore de trabalho precisa ser verificada para sinalizar se há um arquivo que precisa ser reconhecido e commitado

2. Fazer o ```git add``` do arquivo:
Caso algum não seja reconhecido na ávore de trabalho, o nome dos arquivos aparecerão em vermelho. Por isso é necessário utilizar o ```git add ``` com o nome do arquivo. 
Ou se deseja adicionar todos os arquivos do diretório é só utilizar o ```git add . ```

3. Realizando o ```commit```:
Agora que os arquivos foram reconhecidos com suas devidas alterações, eles poderão ser comitados. Para isto basta inserir ```git commit -m "comentario importante sobre o que foi commitado"```. Isso ajudará quando for preciso revisar o histórico de alterações, então utilize uma linguagem simples, direta e **bem resumida**.

4. Verificar o ```git log```:
Como mensionado anteriormente, o git log irá exibir o hash, o autor, a data e o commit. Assim como o status, o log também é sempre bom ser verificado nos processos de realizar o envio (push) para o repositório.

5. Fazer o ```git push```:
Finalmente chegamos no momento de realizar o ```git push origin main```, agora todas as alterações são empurradas para o repositório. Importante observar que ```main``` é o nome da branch. Normalmente, na atualidade, no processo de criação de repositórios é colocado como main, mas ainda há usuários que utilizam ```master```. O nome da branch tem que está de acordo com a branch do projeto remoto.

### Puchando alterações do repositório remoto
Imagine que um colaborador do projeto fez algumas alterações nos arquivos do repositório, então o que você possui na sua máquina está desatualizado, pois seu projeto está com o versionamento anterior. É necessário que você atualize seu repositório local, para que assim você possa fazer novas alterações na versão mais recente do projeto. No terminal do diretório desejado basta digitar ```git pull origin main``` para colocar todas as alterações no repositório local. Fique atento ao nome da branch utilizada no repositório.

### Realizando alterações

- Remover versionamento
Caso o git init foi feito na pasta errada, poderá ser utilizado o ````rm -rf .git```. Isso irá remover .git da pasta.

- Restaura arquivo para a versão anterior
Ele irá retornar para o último salvamento.
```
git restore Nome_Do_Arquivo
```

- Alterar o commit
Existe duas maneiras de editar o último commit:

```
git commit --amend -m"comentário" 
```
ou

```
git commit --amend 
```
A diferença que a última opção abrirá uma janela nova para edição. Aperte a tecla "i" para começar a editar e para sair da janela aperte "esc"+"shift"+":" e para sair digite "wq" e aperte "enter".

- Desfazer um commit
No ```git reset``` pode ser adicionado ```--soft```, ```--mixed``` ou ```--hard```.

1. Soft 

Este tem a função de retornar para o staged. Isso significa que retornando para esse estado a única coisa que falta é commitar e enviar para a branch.
É necessário adicionar depois do comando o hash do commit anterior do que deseja retornar, que pode ser acessado pelo ```git log```. 

2. Mixed

O ```--mixed``` retorna para o unstaged. Então para dar proseguimento é preciso fazer o git add e depois commitar.
Para utilizá-lo basta fazer o mesmo do soft, colocando o hash do commit após o comando.

3. Hard 

Nesse caso ele vai além do staged e unstaged, descartando totalmente o(s) arquivo(s) do commit indicado. Ele segue o mesmo processo de utilização instruído anteriormente. 


# Referências

- [Digital Innovation One - DIO.me](https://web.dio.me/track/coding-future-banco-pan-desenvolvimento-frontend-com-angular?tab=path)
- [Trybe](https://blog.betrybe.com/git/git-push/)
- [Tiago Castro Barbosa](https://www.linkedin.com/pulse/diferenças-entre-git-reset-soft-mixed-e-hard-tiago-castro-barbosa/?originalSubdomain=pt)
