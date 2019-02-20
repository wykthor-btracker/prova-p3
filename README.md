# Funcionalidades
- [x] O sistema permite a adição/remoção de informações referentes aos projetos e atividades.
- [x] Associação de usuários.
- [x] Alteração do status

### O sistema oferece as seguintes consultas:
- [x] Consulta por usuário
- [x] Consulta por projeto
- [x] Consulta por atividade
- [x] O sistema deve fornecer um relatório de projeto e atividades da unidade acadêmica.

( O loop principal de execução do software administra uma lista contendo todos as instâncias criadas durante a execução, se um relatório geral for pedido, este iterará pelos elementos da lista, concatenando suas respectivas chamadas .relatorio a uma string resposta, e devolverá o relatório acumulado de todas as instâncias criadas.)

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
A contemplação da necessidade diferente para formatação é tratada [aqui](#Timestamp)
### Tratamento de Exceções:
- No geral:
    - Serão checados os parâmetros de cada função, para ter certeza que o parâmetro passado é do tipo esperado.
- Na classe Timestamp:
    - O que for passado na String format deve estar contido nas chaves do seguinte dicionário:
        - ```{"y":"year","m":"month","d":"day","h":"hour","M":"minute","s":"seconds"}```
    - Quando estiver fazendo _parse_ da string passada como possível data, será constatado se o valor passado no campo equivalente é compatível. Ex: "dd/mm/yy" para "28/07/97" é compatível, o mesmo formato para "15/20/97" não é.
