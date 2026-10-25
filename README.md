  <h1 align="center" style="color:red;">
    🏋️‍♂️ Academia 🏋️‍♀️
</h1>
<p align="center">
  <img src="https://svg-banners.vercel.app/api?type=origin&text1=Academia%20API&text2=Java%20%7C%20Spring%20Boot%20%7C%20Railway&width=900&height=250" />
</p>




## Projeto desenvolvido para conclusão do Santander Dev Week com parceria DIO.me 
Este sistema foi construído em Java, utilizando Spring Boot, Maven como gerenciador de dependências e H2 Database durante o desenvolvimento.

Trata-se de uma API Restful que permite aos alunos de uma academia consultar:

> Em quais categorias estão matriculados

> Os dias e horários das aulas

> O professor responsável por cada categoria

O objetivo é demonstrar domínio em backend Java, modelagem de dados, boas práticas de API e documentação.

## 🚀 Tecnologias utilizadas

![Java](https://img.shields.io/badge/Java-17-ff8c00?style=plastic&logo=openjdk)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-3.0-00ff7f?style=plastic&logo=springboot)
![Copilot](https://img.shields.io/badge/Copilot-AI_Assistant-00ffff?style=plastic&logo=microsoft)
![Maven](https://img.shields.io/badge/Maven-3.8.6-ff1493?style=plastic&logo=apachemaven)
![MySQL](https://img.shields.io/badge/Postgres-9.0-1e90ff?style=plastic&logo=mysql)
![Railway](https://img.shields.io/badge/Railway-Deploy-9400d3?style=plastic&logo=railway)




## Diagrama de classes:

```mermaid
classDiagram
    class Pessoa {
        +string nome
        +string cpf
        +string telefone
        +string email
    }

    class Aluno {
        +int id_aluno
        +date data_cadastro
    }

    class Professor {
        +int id_professor
        +int id_categoria
    }

    class Categoria {
        +int id_categoria
        +string nome
        +string descricao
    }

    class DataDeAula {
        +int id_aula
        +int id_categoria
        +datetime data_hora
        +int duracao
        +string sala
    }

    class Mensalidade {
        +int id_mensalidade
        +int id_aluno
        +decimal valor
        +date data_vencimento
        +date data_pagamento
        +string status
    }

    class Aulas {
        +int id_aluno
        +int id_categoria
        +date data_matricula
    }

    %% HERANÇA
    Pessoa <|-- Aluno
    Pessoa <|-- Professor

    %% RELACIONAMENTOS
    Aluno "1" --> "N" Mensalidade : possui
    Aluno "N" --> "N" Categoria : matriculado_em
    Aluno "1" --> "N" Aulas : vinculo

    Categoria "1" --> "N" Professor : possui
    Categoria "1" --> "N" DataDeAula : agenda
    Categoria "1" --> "N" Aulas : vinculo

```

