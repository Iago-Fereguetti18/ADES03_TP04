# AEDS III - TP03

## Alunos integrantes da equipe

* Diego Moreira Rocha
* Luan Barbosa Rosa Carrieiros
* Iago Fereguetti Ribeiro 

Neste trabalho prático foi:
- Abrimos cada arquivo tarefa como um vetor de bytes
- Foi acionado o algoritmo LZW para compactar os arquivos de backup

# Classes e Métodos criados

## Classe Compactador

* ### Métodos:

- descompacta(String versao): Realiza a descompactação de arquivos de um backup, extraindo os dados e salvando-os na pasta dados. Utiliza a classe LZW para decodificar os dados.
- compacta(): Realiza a compactação de arquivos presentes na pasta dados e cria um arquivo de backup utilizando a data atual no nome. Utiliza a classe LZW para codificar os dados.

## Classe LZW

* ### Atributos:

- public static final int BITS_POR_INDICE: Define o número de bits por índice, utilizado para limitar o tamanho do dicionário durante a codificação e decodificação.


* ### Métodos:

- byte[] codifica(byte[] msgBytes): Codifica uma mensagem utilizando o algoritmo LZW, criando um dicionário de sequências de bytes e gerando índices para as subsequências encontradas.
- byte[] decodifica(byte[] msgCodificada): Decodifica uma mensagem codificada utilizando LZW, reconstruindo a mensagem original a partir dos índices.

## Classe VetorDeBits

* ### Atributos:

- BitSet vetor: Um conjunto de bits que pode ser manipulado.

* ### Construtores:

- VetorDeBits(): Construtor padrão que inicializa o vetor como um BitSet vazio e define o bit 0.
- VetorDeBits(int n): Inicializa o vetor com capacidade para n bits e define o último bit como ativo.
- VetorDeBits(byte[] v): Constrói um VetorDeBits a partir de um vetor de bytes.

* ### Métodos:

- byte[] toByteArray(): Converte o BitSet interno para um vetor de bytes.
- void set(int i): Ativa o bit na posição i, ajustando a capacidade do vetor se necessário.
- void clear(int i): Desativa o bit na posição i, ajustando a capacidade do vetor se necessário.
- boolean get(int i): Retorna o estado do bit na posição i.
- int length(): Retorna o índice mais alto do bit ativo.
- int size(): Retorna o tamanho total do BitSet interno.
- String toString(): Constrói uma string composta de 0 e 1 para representar os bits armazenados.

## Classe VisaoBackUps

* ### Atributos:

- Scanner console: Scanner usado para capturar entradas do usuário no console.


* ### Métodos:

- void menu(): Exibe o menu principal para backup e carrega backups antigos.
- void fazerBackup(): Chama o método compacta() da classe Compactador para criar um backup do sistema.
- void carregarBackup(): Exibe uma lista de backups disponíveis no diretório ./backups

## Experiência
Foi um TP mais tranquilo de fazer, foi divertido. O único problema que aconteceu não está relacionado ao TP e sim ao GitHUb, mas também foi tranquilo de resolver. 

## Perguntas

- Há uma rotina de compactação usando o algoritmo LZW para fazer backup dos arquivos? sim
- Há uma rotina de descompactação usando o algoritmo LZW para recuperação dos arquivos? sim
- O usuário pode escolher a versão a recuperar? sim
- Qual foi a taxa de compressão alcançada por esse backup? (Compare o tamanho dos arquivos compactados com os arquivos originais) 1,04
- O trabalho está funcionando corretamente? sim
- O trabalho está completo? sim
- O trabalho é original e não a cópia de um trabalho de um colega? sim
