# 🕵🏽‍♂️ Catálogo - Estudo de Clean Architecture

Este repositório tem como objetivo registrar um estudo prático da arquitetura **Clean Architecture**, utilizando uma aplicação de catálogo como exemplo. O foco é aplicar os princípios de separação de responsabilidades e independência de tecnologias externas.

## 📚 Sobre o Projeto

A aplicação simula um sistema de **catálogo de produtos**, dividido em camadas bem definidas e organizadas de acordo com os princípios da Clean Architecture propostos por Robert C. Martin (Uncle Bob). A estrutura favorece a escalabilidade e manutenção.

<div align="center">
  <img src="https://img-c.udemycdn.com/course/750x422/3850148_5ad7_10.jpg" alt="Arquitetura Clean Architecture" width="600"/>
</div>


## 🛠️ Tecnologias Utilizadas

- .NET 7 
- Entity Framework Core
- AutoMapper
- FluentValidation
- Swagger

## 🏗️ Estrutura de Pastas

```bash
📦 Catalogo
 ┣ 📂 Catalogo.API
 ┣ 📂 Catalogo.Application
 ┃ ┣ 📂 DTOs
 ┃ ┣ 📂 Interfaces
 ┃ ┣ 📂 Mappings
 ┃ ┗ 📂 Services
 ┣ 📂 Catalogo.Domain
 ┃ ┣ 📂 Entities
 ┃ ┣ 📂 Interfaces
 ┃ ┗ 📂 Validation
 ┣ 📂 Catalogo.CrossCutting
 ┃ ┗ 📂 IoC
 ┗ 📂 Catalogo.Infrastructure
   ┣ 📂 Context
   ┣ 📂 EntitiesConfiguration
   ┣ 📂 Migrations
   ┗ 📂 Repositories
```

## 📂 Catalogo.API

Camada responsável por expor a aplicação via Web API. Contém os **controllers**, configuração de middlewares, tratamento de erros e documentação (ex: Swagger).

## 📂 Catalogo.Application

Contém a lógica de **aplicação** e os **casos de uso**. Orquestra as ações entre a interface do usuário e o domínio.

*   **DTOs**: Representações de dados utilizadas para entrada e saída.
    
*   **Interfaces**: Contratos usados para abstrair serviços.
    
*   **Mappings**: Configurações de mapeamento de objetos (AutoMapper).
    
*   **Services**: Implementações dos casos de uso da aplicação.
    

## 📂 Catalogo.Domain

Contém o **núcleo da regra de negócio**, independente de frameworks ou tecnologias externas.

*   **Entities**: Entidades do domínio com suas regras e comportamentos.
    
*   **Interfaces**: Abstrações como repositórios e serviços de domínio.
    
*   **Validation**: Validações de entidades com regras de negócio (FluentValidation).
    

## 📂 Catalogo.CrossCutting

Responsável por **preocupações transversais** à aplicação, como:

*   Logging
    
*   Tratamento global de erros
    
*   Utilitários e helpers
    

### 📂 IoC (Inversion of Control)

Contém as configurações de **injeção de dependência** para registrar e resolver serviços, repositórios e outras dependências do sistema.

## 📂 Catalogo.Infrastructure

Implementa as dependências técnicas e os contratos definidos nas camadas superiores (Domain e Application).

*   **Context**: DbContext do Entity Framework Core.
    
*   **EntitiesConfiguration**: Mapeamento das entidades com o banco de dados via Fluent API.
    
*   **Migrations**: Histórico das migrações do EF Core.
    
*   **Repositories**: Implementações concretas dos repositórios do domínio.

## 📌 Observações
Este projeto tem fins educacionais e serve como referência para a implementação de Clean Architecture com .NET. Algumas decisões podem ter sido simplificadas para facilitar o aprendizado.

## 📚 Referências

[Clean Architecture - Uncle Bob](https://blog.cleancoder.com/uncle-bob/2011/11/22/Clean-Architecture.html)

[Documentação oficial do .NET](https://learn.microsoft.com/pt-br/aspnet/core/?view=aspnetcore-9.0)
