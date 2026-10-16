  <h1 align="center" style="color:red;">
    🏋️‍♂️⚔️ Academia ⚔️🏋️‍♀️
</h1>


### Projeto desenvolvido para conclusão do Santander Dev Week (DIO.me)  
Este sistema foi construído em Java, utilizando Spring Boot, Maven como gerenciador de dependências e H2 Database durante o desenvolvimento.

Trata-se de uma API Restful que permite aos alunos de uma academia consultar:

> Em quais categorias estão matriculados

> Os dias e horários das aulas

> O professor responsável por cada categoria

O objetivo é demonstrar domínio em backend Java, modelagem de dados, boas práticas de API e documentação.





## Entidades

    class Alunos {
        +int matricula PK
        +string nome
        +string cpf
        +string telefone
        +string senha
    }

    class Aulas {
        +int id_aula PK
        +string categoria
    }

    class Aula_Aluno {
        +int codigo PK
        +int matricula FK
        +int id_aula FK
    }

    class Professor {
        +int registro PK
        +string nome
        +int id_aula FK
    }

    class Calendario {
        +int codigo FK
        +string dia_semana
        +time hora
    }

    Alunos "1" --> "0..*" Aula_Aluno : matricula
    Aulas "1" --> "0..*" Aula_Aluno : id_aula
    Aulas "1" --> "0..*" Professor : id_aula
    Aula_Aluno "1" --> "1" Calendario : codigo

