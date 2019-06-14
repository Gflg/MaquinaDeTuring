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
