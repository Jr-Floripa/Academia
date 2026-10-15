  <h1 align="center" style="color:red;">
    🏋️‍♂️💥 Academia 💥🏋️‍♀️
</h1>

### Projeto desenvolvido para conclusão do Santander Dev Week (DIO.me)  
Este sistema foi construído em Java, utilizando Spring Boot, Maven como gerenciador de dependências e H2 Database durante o desenvolvimento.

Trata-se de uma API Restful que permite aos alunos de uma academia consultar:

> Em quais categorias estão matriculados

> Os dias e horários das aulas

> O professor responsável por cada categoria

O objetivo é demonstrar domínio em backend Java, modelagem de dados, boas práticas de API e documentação.
```mermaid
%% ============================
%% Estilos personalizados
%% ============================
classDiagram
    %% Cores das classes
    classDef tabela fill:#ffe6e6,stroke:#cc0000,stroke-width:2px,color:#660000;
    classDef relacao stroke:#990000,stroke-width:2px;

    %% ============================
    %% Classes
    %% ============================
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

    %% Aplicando estilos
    Alunos:::tabela
    Aulas:::tabela
    Aula_Aluno:::tabela
    Professor:::tabela
    Calendario:::tabela

    %% ============================
    %% Relacionamentos
    %% ============================
    Alunos "1" --> "0..*" Aula_Aluno : matricula
    Aulas "1" --> "0..*" Aula_Aluno : id_aula
    Aulas "1" --> "0..*" Professor : id_aula
    Aula_Aluno "1" --> "1" Calendario : codigo
``
