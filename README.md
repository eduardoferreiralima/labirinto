# Aplicação de Pilha: Trapped Mouse

## Descrição do Problema
O objetivo do programa é resolver o problema de um rato preso em um labirinto tentando encontrar a saída. O labirinto é modelado como um array bidimensional onde:
- `0`: Corredores.
- `1`: Paredes.
- `e`: Posição da saída.
- `m`: Posição inicial do rato.

## Modelagem
O labirinto é representado por um array bidimensional de caracteres, e as interações seguem as seguintes regras:
- O rato inicia em uma célula especificada como `m`.
- A saída está marcada como `e`.
- Apenas os caracteres `1`, `0`, `e`, e `m` são aceitos.

## Implementação
### Estrutura
O programa utiliza **pilhas** para:
1. Inicializar o labirinto.
2. Implementar o algoritmo de **Backtracking**.

### Algoritmos
#### Inicialização do Labirinto
1. Criar uma pilha para armazenar as linhas do labirinto.
2. Adicionar paredes externas ao labirinto após sua leitura.
3. Permitir entrada do labirinto via arquivo ou diretamente pelo teclado.

#### Saída do Labirinto
O algoritmo de backtracking funciona da seguinte forma:
1. O rato explora sistematicamente todas as rotas disponíveis.
2. Se um beco sem saída for encontrado, o programa retorna para a última posição não testada.
3. Cada posição visitada é marcada com o caractere `.` para evitar loops infinitos.
4. A sequência de busca é: direita, esquerda, baixo, cima.

#### Exemplo de Algoritmo
```text
1. Stack mazeStack;
2. currentCell = posição inicial do rato;
3. enquanto currentCell não for exitCell faça:
4.   Marcar currentCell como visitada;
5.   Colocar na pilha os vizinhos não visitados de currentCell;
6.   Se mazeStack estiver vazia, então:
7.     Caminho não encontrado;
8.   Caso contrário:
9.     Faça pop da pilha e defina como currentCell;
10. fim
