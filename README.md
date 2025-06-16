# Aplicação Web de Cadastro e Autenticação

Projeto de desenvolvimento de software para cadastro de usuários e autenticação
utilizando JWT com dois tipos de usuários **admin** e **user**.

## 📚 Sobre o Projeto

Este projeto foi desenvolvido como parte de uma disciplina do curso de **Desenvolvimento de Software**. Seu principal objetivo é construir uma aplicação web capaz de autenticar via JWT e cadastrar usuários com diferentes roles.

---

## ⚙️ Tecnologias Utilizadas

### 🔙 Backend
- **Java (Spring)**: estrutura principal da aplicação.

### 🛢️ Banco de Dados
- **mySQL/PostgreSQL**: banco de dados mySQL/PostgreSQL.

---

## 🧠 Como Funciona

1. **Cadastra Usuários**: Permite o registro de novos usuários com campos básicos como nome, e-mail, e senha. Define o papel (role) do usuário no momento do cadastro.
2. **Autenticação com JWT**: Implementa um sistema de login que gere um token JWT ao autenticar o usuário com sucesso. Permite acesso a endpoints protegidos apenas com um token JWT válido.
3. **Controle de Acesso por Role**: Cria endpoints específicos para admins e users. Garante que apenas admins tenham acesso a determinadas funcionalidades, como listar todos os usuários cadastrados.
4. **Gerenciamento de Usuários**: User pode visualizar e editar seu próprio perfil. Admin pode visualizar, editar e deletar qualquer usuário.

---

## 🛠️ Estrutura do Projeto

```bash
/backend
  └── src
      └── main
          └── java
              └── com.example.gbr
                  ├── user
                  ├── (soon)
                  ├── (soon)
                  └── GbrApplication.java

```

## 🚀 Como Rodar o Projeto Localmente

### Pré-requisitos

- JDK 17+
- mySQL/PostgreSQL
- Git

### Passo a passo

1. Clone o repositório:
```bash
git clone https://github.com/gabrsantos1/crud-eliel.git
```

2. Acesse a pasta do diretório e inicie a aplicação Java via IDE ou bash:
```bash
cd java
cd com
cd example
cd gbr
./mvnw spring-boot:run
```

### 📝 Licença
Este projeto está sob a licença MIT. Veja o arquivo LICENSE para mais detalhes.
