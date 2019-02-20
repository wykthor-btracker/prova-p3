Funcionalidades
------

# Classes
### BaseClass:
A classe base para Atividade e Projeto, como ambos continham os mesmos atributos com nomes diferentes, esta classe foi construída para comportar os elementos em comum entre Atividade e Projeto. Também foi definida a função setLeader, que é sobreescrita em Projeto, possibilitando a mudança de funcionalidade dada a necessidade de checar quem está sendo designado como coordenador de um dado Projeto.
### Timestamp:
A classe usada para conter funcionalidades relacionadas a tempo, sendo capaz de receber especificações de formatação, como por exemplo: 
```python
"dd-mm-yy hh:MM:ss"
```
, se este for passado como argumento para parseString, a função irá interpretar como esperado, a string
```python
"28-07-97 19:20:59"
```
, retornando então uma instância de Timestamp com os respectivos atributos assinados corretamente, daí em diante, sendo possível acessar os components do _tempo_ por meio de 
```python
Instance.ano
"1997"
```

### Pessoa:
Como a única diferença entre funcionários da unidade acadêmica é a possiblidade ou não de coordenar projetos, segundo as especificações, basta que um atributo nesta classe sinalize a qual cargo a instância que representa um funcionário pertence daí uma checagem contra este atributo será suficiente para fazer a autenticação da instância.

### Abstrata
A classe BaseClass é analoga à uma classe abstrata, já que define as funções mínimas para o funcionamento de um projeto _ou_ atividade

### Polimorfismo
A ocasião em que fez-se necessário o polimorfismo foi na definição da função parseString da classe Timestamp, já que podemos definir um funcionamento padrão, para quando o formato padrão de data, 
```
"dd/mm/yyyy hh:MM:ss"
```
é preferível.
A contemplação da necessidade diferente para formatação é tratada [aqui](#timestamp)
Tratamento de Exceções

Extensibilidade

Reuso
