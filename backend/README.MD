# 📚 Sistema de Gerenciamento de Biblioteca

![Java](https://img.shields.io/badge/Java-17+-orange?style=for-the-badge&logo=openjdk)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-3.x-green?style=for-the-badge&logo=springboot)
![Angular](https://img.shields.io/badge/Angular-17+-red?style=for-the-badge&logo=angular)
![Docker](https://img.shields.io/badge/Docker-Enabled-blue?style=for-the-badge&logo=docker)
![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)

O **Sistema de Gerenciamento de Biblioteca** é uma aplicação Fullstack desenvolvida para facilitar a administração e o controle do acervo de bibliotecas. A solução conta com um ecossistema completo que engloba rotas RESTful no backend, interface moderna no frontend e suporte a contêineres Docker.

---

## 📌 Sumário

- [Visão Geral](#-visão-geral)
- [Tecnologias Utilizadas](#-tecnologias-utilizadas)
    - [Backend](#backend)
    - [Frontend](#frontend)
    - [DevOps \& Ferramentas](#devops--ferramentas)
- [Arquitetura do Projeto](#-arquitetura-do-projeto)
- [Instalação e Execução](#-instalação-e-execução)
    - [Pré-requisitos](#pré-requisitos)
    - [Rodando com Docker Compose (Recomendado)](#rodando-com-docker-compose-recomendado)
    - [Execução Manual](#execução-manual)
- [Endpoints da API](#-endpoints-da-api)
- [Contribuição](#-contribuição)
- [Licença](#-licença)

---

## 🧐 Visão Geral

O projeto automatiza fluxos essenciais de uma biblioteca, tais como:
- Cadastro, listagem, atualização e remoção de acervo de livros.
- Organização em arquitetura em camadas (Controller, Service, Repository, DTO/Mapper).
- Interface de usuário responsiva desenvolvida em Angular.
- Padronização de ambiente de desenvolvimento utilizando Docker.

---

## 🛠 Tecnologias Utilizadas

### Backend
- **Java 17+**
- **Spring Boot 3** (Spring Web, Spring Data JPA)
- **Maven** (Gerenciamento de dependências)
- **Lombok / MapStruct** (Mapeamento de modelos e DTOs)

### Frontend
- **Angular 17+**
- **TypeScript**
- **HTML5 / CSS3**
- **Angular CLI**

### DevOps & Ferramentas
- **Docker** & **Docker Compose**
- **Git** (Controle de versão)

---

## 📂 Arquitetura do Projeto

```text
Gerenciamento-de-Biblioteca/
│
├── backend/                             # API Spring Boot
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/com/gerenciamento/biblioteca/blumenau/
│   │   │   │   ├── controller/          # Endpoints da REST API
│   │   │   │   ├── service/             # Regras de negócio
│   │   │   │   ├── repository/          # Acesso ao banco de dados
│   │   │   │   ├── model/               # Entidades JPA
│   │   │   │   └── mapper/              # Mapeamento DTO <-> Entity
│   │   │   └── resources/
│   │   │       └── application.properties
│   ├── Dockerfile
│   └── docker-compose.yml
│
└── frontend/                            # Aplicação Angular
    └── biblioteca/
        ├── src/
        │   ├── app/                     # Componentes e rotas
        │   ├── assets/                  # Arquivos estáticos
        │   └── styles.css               # Estilos globais
        ├── angular.json
        └── package.json
```

---

## 🚀 Instalação e Execução

### Pré-requisitos

Certifique-se de ter instalado em sua máquina:
- [JDK 17+](https://www.oracle.com/java/technologies/downloads/)
- [Node.js](https://nodejs.org/) (v18 ou superior) e npm
- [Angular CLI](https://angular.io/cli) (`npm install -g @angular/cli`)
- [Docker](https://www.docker.com/) e Docker Compose (opcional para execução conteinerizada)

---

### Rodando com Docker Compose (Recomendado)

Na raiz do diretório `backend/`, execute o comando abaixo para subir o ambiente completo:

```bash
cd backend
docker-compose up -d --build
```

O backend estará acessível em `http://localhost:8080`.

---

### Execução Manual

#### 1. Backend (Spring Boot)

```bash
# Entre na pasta do backend
cd backend

# Execute a aplicação usando o Maven Wrapper
./mvnw spring-boot:run
```

*Para Windows, utilize `mvnw.cmd spring-boot:run`.*

A API iniciará no endereço: `http://localhost:8080`.

#### 2. Frontend (Angular)

```bash
# Entre na pasta do frontend
cd frontend/biblioteca

# Instale as dependências
npm install

# Inicie o servidor de desenvolvimento
ng serve
```

Navegue até `http://localhost:4200/` no seu navegador.

---

## 📌 Endpoints da API

Abaixo estão listados os endpoints principais mantidos pelo `BibliotecaController`:

| Método | Endpoint | Descrição |
| :--- | :--- | :--- |
| `GET` | `/api/biblioteca` | Lista todos os livros cadastrados |
| `GET` | `/api/biblioteca/{id}` | Busca um livro por ID |
| `POST` | `/api/biblioteca` | Cadastra um novo livro |
| `PUT` | `/api/biblioteca/{id}` | Atualiza os dados de um livro existente |
| `DELETE` | `/api/biblioteca/{id}` | Remove um livro do acervo |

---

## 🤝 Contribuição

Contribuições são sempre bem-vindas! Para contribuir:

1. Faça um **Fork** do projeto.
2. Crie uma **Branch** para sua feature (`git checkout -b feature/NovaFeature`).
3. Faça os **Commits** (`git commit -m 'Adiciona nova feature'`).
4. Envie a Branch (`git push origin feature/NovaFeature`).
5. Abra um **Pull Request**.

---

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.