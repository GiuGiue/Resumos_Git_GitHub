# Resumos Git e GitHub

Construi esse repositório com a finalidade de armazenar resumos realcionados ao versionamento de código com Git e GitHub, servindo como material de apoio para revisão.

## Documentações
- [Documentação Git](https://git-scm.com/docs/git/pt_BR)
- [Documentação GitHub](https://docs.github.com/pt)

## Comandos Git Bash
- **Comandos importantes para manipular diretórios**

|Voltar para a pasta anterior|Criar diretório (pasta)|Ignorar diretório|Entrar no diretório|Mostrar status|
|-----------|-----------|------------|------------|---------|
|```cd ..```|```mkdir Nome_Do_Diretório```|```touch .gitignore```|```cd Nome_Do_Diretório```|```git status```|

- Mostrar status
Esse comando pode ser utilizado para verificar o status do commit na pasta, da árvore de trabalho e área de preparação. A área de preparação (ou index) é onde será preparado os arquivos que serão salvos em um commit. 
- Ignorar diretório
Esse comando irá criar um arquivo .gitignore, por isso é importante está dentro do diretório desejado. O diretório será ignorado e não será passado para o repositório.

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

Observe que "README.md" é o nome do arquivo Markdown. Então você irá colocar o nome de acordo com o arquivo. Nestes exemplos está sendo criado um readme.

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

### Subir repositório local para o repositório remoto
Depois de realizar o commit, esse processo pode ser realizado.

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
Com o link do repositório do GitHub, no terminal coloque o comando:
```
git clone https://github.com/GiuGiue/test.git
```
Acrescente o link do repositório desejado após o comando. Este é um link fctício. Para alterar o nome basta escrever o nome que deseja após a URL. 

### Subindo alterações dos arquivos
É possível observar que esse processo é muito semelhante aos outros. A diferença que será excluída as etapas de criação de arquivos e diretórios, ligação entre o repositório local e remoto.

1. Verificar o ```git status``` 
A árvore de trabalho precisa ser verificada para sinalizar se há um arquivo que precisa ser reconhecido e commitado

2. Fazer o ```git add``` do arquivo
Caso algum não seja reconhecido na ávore de trabalho, o nome dos arquivos aparecerão em vermelho. Por isso é necessário utilizar o ```git add ``` com o nome do arquivo. 
Ou se deseja adicionar todos os arquivos do diretório é só utilizar o ```git add . ```

3. Realizando o ```commit```
Agora que os arquivos foram reconhecidos com suas devidas alterações, eles poderão ser comitados. Para isto basta inserir ```git commit -m "comentario importante sobre o que foi commitado"```. Isso ajudará quando for preciso revisar o histórico de alterações, então utilize uma linguagem simples, direta e **bem resumida**.

4. Verificar o ```git log```
Como mensionado anteriormente, o git log irá exibir o hash, o autor, a data e o commit. Assim como o status, o log também é sempre bom ser verificado nos processos de realizar o envio (push) para o repositório.

5. Fazer o ```git push```
Finalmente chegamos no momento de realizar o ```git push```, agora todas as alterações são empurradas para o repositório.

### Puchando alterações do repositório remoto
No terminal do diretório desejado basta digitar ```git pull``` para colocar todas as alterações no repositório local.

### Realizar alterações no repositório

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


## Referências

- [Digital Innovation One - DIO.me](https://web.dio.me/track/coding-future-banco-pan-desenvolvimento-frontend-com-angular?tab=path)
- [Trybe](https://blog.betrybe.com/git/git-push/)
- [Tiago Castro Barbosa](https://www.linkedin.com/pulse/diferenças-entre-git-reset-soft-mixed-e-hard-tiago-castro-barbosa/?originalSubdomain=pt)
