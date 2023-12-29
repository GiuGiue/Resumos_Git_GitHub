
# Resumos Git e GitHub

Repositório com a finalidade de armazenar resumos realcionados ao versionamento de código com Git e GitHub.

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
Dica: Uma boa ferramenta para edição de Markdown (.md) é o [Readme so](readme.so), pois permite pré-visualização.

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
- Subindo alterações dos arquivos
## Referências

- [Digital Innovation One - DIO.me](https://web.dio.me/track/coding-future-banco-pan-desenvolvimento-frontend-com-angular?tab=path)