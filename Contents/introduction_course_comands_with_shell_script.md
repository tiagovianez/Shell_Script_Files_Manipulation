# 1) Introduão ao curso e alguns comandos com Shell Script



  ## cd - Mudar diretório

Cd é um acrônimo da expressão ingles _change directory_

* _cd /_    Abre o diretório raiz do sistema

* _cd ~_    Abre o diretório do usuário corrente. O usuário logado naquele instante.

* _cd .._  Volta diretório 



## Listando Arquivos

* _ls -I:_  Lista o conteúdo em coluna detalhada
* _ls -a:_ Lista o conteúdo até os arquivos ocultos
* _ls -s:_ Lista o conteúdo com tamanho alocada de cada arquivo, em bloco

### 

## Comando Touch (Criar e atualizar conteúdo)

##### Criando múltiplos arquivos

touch file_name1.txt file_name2.txt file_name3.txt

##### Alterar Hora de Acesso

touch -a file_name.txt

##### Alterar Hora da Modificação

touch -m file_name1.txt

##### Alterar Hora de Acesso sem Criar um Novo Arquivo

touch -c file_name.txt

##### Definir hora específica de acesso e modificação usando Touch

touch -t 202012081047 file.txt



## Comando cat (Visualizar o conteúdo)

_(cat) concatenate (concatenar)_

* Criar arquivos

* Unir arquivos

* Exibir arquivos

* Colocar o resultado em um outro arquivo utilizando um redirecionador de saída: _cat arq > arq_final_

  

  #### Exercício Prático

  Crie um arquivo chamado arq.txt, insira a informação "arquivo de teste".

  Em seguida, crie um outro arquivo chamado food.txt, e transfira a informação de arq.txt para food.txt

  

  1) _touch arq.txt_
  2) _nano arq.txt_
  3) Inserir a informação "arquivo de teste" no arquivo arq.txt
  4) _touch food.txt_
  5) _cat touch arq.txt > food.txt_

  

  

  ## Movendo arquivos com o comando (mv)

  ##### 1) Crie uma pasta chamada "meudiretorio" e um arquivo "mv-comando.txt" de forma simultânea

  mkdir meudiretorio && touch mv-comando.txt

  

  ##### 2) Mova o arquivo mv-comando.txt para esse diretório com confirmação

  _mv -i mv-comando.txt meudiretorio_

  

  ##### 3) Mova o arquivo mv-comando.txt para esse diretório, sabendo que já há uma cópia dentro da pasta meudiretório, mas substitua pelo backup

  _mv -b mv-comando.txt meudiretorio_

  



## Copiando arquivos (cp)

- Sem confirmação de existência ou não, exceto se usar a flag  **_-i_  (interativa).**

* Nenhuma saída será exibida, exceto se usar o flag opção **_-v_ (verbose)**

* **-i:** criar hard links em vez de copiar os arquivos
* **-s:** criar links simbólicos em vez de copiar arquivos
* **-u:** copiar apenas quando o arquivo de origem for mais novo do que o arquivo destino ou quando o arquivo de destino não existir.





#### Exercício Prático

##### 1) Crie o arquivo m.txt e mova ele para meudiretorio, utilizando o comando absoluto.

_touch m.txt_

_cp -i m.txt /home/tiago/Documents/Exercicios/meudiretorio/_



##### 2) Faça a mesma coisa anteriormente utilizando o comando cp -v

cp -v m.txt /home/tiago/Documents/Exercicios/meudiretorio/

cp: 'm.txt' and '/home/tiago/Documents/Exercicios/meudiretorio/m.txt' are the same file

##### *Este comando informa detalhadamente o caminho para onde o arquivo foi



##### 3) Faça a cópia do "meudiretorio" movendo para um outro diretório chamado"novo"

_cp -v -r meudiretorio novo_



##### 4) Faça a cópia de todos os arquivos que estão no diretório "/Exercicios" para o diretório "/novo"

_cp -v -r . novo_





## Criando diretórios (mkdir)

- **rm:** remoção de arquivos.
- **rm -f:** remoção forçada



## Procurar e Remover arquivos

- **_find . :_**  Procurar por arquivos
- **_find ./ -type d -name "novo" :_**  Irá procurar arquivos que possuem a **apenas** a palavra "novo"

* **_find ./ -type d -name "novo*" :_**  Irá procurar todos aqueles arquivos que possuem a palavra "novo"
* **_find ./ -type f -name ".*" :_**  Irá procurar arquivos ocultos na pasta
* **_man find_**:  Irá informar o manual de instrução do comando find



## Comparando a diferença entre arquivos com o comando _diff_ 

##### 1) Crie um arquivos chamado "arq.txt" 

_touch arq.txt_

##### 2) Use o editor de texto para o "arq.txt" e insira a informação "Arquivo de Teste"

_nano arq.txt_

_Arquivo de Teste > CTRL + O > Enter > CTRL + X_

##### 3) Em seguida, crie um novo arquivo chamado "arq1.txt", já copiando as informações de "arq.txt"

_cat touch arq.txt > arq1.txt_

##### 4) Em seguida, use o editor de texto em "arq1.txt", colocando a informação "Teste2"

_nano arq1.txt_

##### 5) Por último, faça a comparação desses dois arquivos utilizando o comando _diff_

_diff arq.txt arq1.txt_



## Remover Diretório (rmdir)

_**rmdir:**_ remover diretório vazio

_**rm -rf:**_ diretório não vazio





## Variáveis de Ambiente

_**env:**_ Variáveis de ambiente

**PSI**: Prompt da linha de comandos

**HOME:** Diretório "/home" de um usuário

**PATH**: Lista de diretórios vasculhados quando um comando é executado

**Exemplo:** 

1) Crie um diretório chamado **"limão"**

   _**mkdir limao**_

   

2) Crie a variável desse diretório 

   _**limao=limao**_



3) Dê um export nessa variável

   _**export limao**_



4) Visualize as variáveis de ambiente

   _**env**_
