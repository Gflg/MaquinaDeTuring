# MaquinaDeTuring
Trabalho de Linguagens Formais: criar uma máquina de Turing que lê um autômato de pilha e uma palavra e checa se o autômato aceita tal palavra.


# Arquivos
A máquina de turing principal está no arquivo TrabalhoLF.jff. 
Outros dois arquivos (empilha.jff e desempilha.jff) são utilizados na forma de building blocks no arquivo principal.

# Exemplos utilizados
Para testar foram utilizados os seguintes exemplos listados abaixo:

### Exemplo 1
![L1](https://i.ibb.co/W6312MR/l1.gif)
<br>
Nos casos do exemplo 1 foram utilizadas 3 entradas para o mesmo teste no intuito de mostrar que a ordem das transições não afeta a resposta da nossa Máquina de Turing.

##### Palavras de entrada:

###### aabb:
Este exemplo deve aceitar a entrada (escrever #A no final).<br>
q1a1ea1eq1#q1a11a1eeq11#q11a11a1eeq11$a1a1a11a11<br>
q11a11a1eeq11#q1a1ea1eq1#q1a11a1eeq11$a1a1a11a11<br>
q11a11a1eeq11#q1a11a1eeq11#q1a1ea1eq1$a1a1a11a11<br>

###### aab:
Este exemplo deve rejeitar a entrada (escrever #R no final).<br>
q1a1ea1eq1#q1a11a1eeq11#q11a11a1eeq11$a1a1a11<br>
q11a11a1eeq11#q1a1ea1eq1#q1a11a1eeq11$a1a1a11<br>
q11a11a1eeq11#q1a11a1eeq11#q1a1ea1eq1$a1a1a11<br>

###### abb:
Este exemplo deve rejeitar a entrada.<br>
q1a1ea1eq1#q1a11a1eeq11#q11a11a1eeq11$a1a11a11<br>
q11a11a1eeq11#q1a1ea1eq1#q1a11a1eeq11$a1a11a11<br>
q11a11a1eeq11#q1a11a1eeq11#q1a1ea1eq1$a1a11a11<br>

###### aabbc:
Este exemplo deve rejeitar a entrada.<br>
q1a1ea1eq1#q1a11a1eeq11#q11a11a1eeq11$a1a1a11a11a111<br>
q11a11a1eeq11#q1a1ea1eq1#q1a11a1eeq11$a1a1a11a11a111<br>
q11a11a1eeq11#q1a11a1eeq11#q1a1ea1eq1$a1a1a11a11a111<br>

### Exemplo 2

![L2](https://i.ibb.co/fSXHX1V/l2.gif)

##### Palavras de entrada:

###### aabcdd:
q1a1ea1eq1#q1a11ea11eq11#q11a11ea11eq11#q11a111a11eeq111#q111a111a11eeq111#q111a1111a1eeq1111#q1111a1111a1eeq1111$a1a1a11a111a1111a1111

###### abbccd:
q1a1ea1eq1#q1a11ea11eq11#q11a11ea11eq11#q11a111a11eeq111#q111a111a11eeq111#q111a1111a1eeq1111#q1111a1111a1eeq1111$a1a11a11a111a111a1111

###### aabbcd:
q1a1ea1eq1#q1a11ea11eq11#q11a11ea11eq11#q11a111a11eeq111#q111a111a11eeq111#q111a1111a1eeq1111#q1111a1111a1eeq1111$a1a1a11a11a111a1111

###### abccdd:
q1a1ea1eq1#q1a11ea11eq11#q11a11ea11eq11#q11a111a11eeq111#q111a111a11eeq111#q111a1111a1eeq1111#q1111a1111a1eeq1111$a1a11a111a111a1111a1111

###### aabbccdd:
q1a1ea1eq1#q1a11ea11eq11#q11a11ea11eq11#q11a111a11eeq111#q111a111a11eeq111#q111a1111a1eeq1111#q1111a1111a1eeq1111$a1a1a11a11a111a111a1111a1111


### Outros exemplos de rejeição

###### ab:
q1a11a111a1eq11#q11a1a11eq111$a1a11 <br>
Falha ao tentar encontrar a no estado inicial q1, que possui apenas transição com o símbolo b para q2.

###### ab:
q1a1a111a1eq11#q11a1a11eq111$a1a11 <br>
Falha por tentar desempilhar simbolo que não está no topo da pilha.

###### b:
q1a11ea1eq11#q11a1a11q111$a11 <br>
Falha por ter um símbolo na pilha enquanto a palavra foi toda percorrida.

###### ca:
q1a111eeeq111#q11a1a11q111$a111a1 <br>
Falha por ir ao estado q3, que não possui transições, ao ler c enquanto a palavra não foi toda percorrida.

###### abbbbd:
q1111a1eea11q11#q11a11eeeq11#q11a1111a11eeq111$a1a11a11a11a11a1111 <br>
Falha pelo fato de que o autômato de pilha não possui o estado inicial q1.
