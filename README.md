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
                  ├── service
                  ├── security
                  ├── repository
                  ├── model
                  ├── dto
                  ├── controller
                  ├── config
                  └── GbrApplication.java

```

## 🚀 Como Rodar o Projeto Localmente

### Pré-requisitos

- JDK 17+
- mySQL/PostgreSQL
- Git
- JWT Secret Key (key-gbr)
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

# Documentação das Rotas

## Endpoints de Autenticação

### Registrar novo usuário
- **URL**: `/api/auth/signup`
- **Método**: `POST`
- **Body**:
```json
{
    "name": "Nome do Usuário",
    "email": "usuario@exemplo.com",
    "password": "senha123",
    "role": "ROLE_USER"  // padrão: ROLE_USER
}
```

### Login
- **URL**: `/api/auth/signin`
- **Método**: `POST`
- **Body**:
```json
{
    "email": "usuario@exemplo.com",
    "password": "senha123"
}
```

## Endpoints de Usuários

### Listar todos os usuários
- **URL**: `/api/users/all`
- **Método**: `GET`
- **Acesso**: Apenas Admin

### Buscar usuário por ID
- **URL**: `/api/users/{id}`
- **Método**: `GET`
- **Acesso**: Admin ou próprio usuário

### Atualizar usuário
- **URL**: `/api/users/{id}`
- **Método**: `PUT`
- **Acesso**: Admin ou próprio usuário
- **Body**:
```json
{
    "name": "Nome Atualizado",
    "email": "atualizado@exemplo.com",
    "password": "novasenha"  // Opcional
}
```

### Deletar usuário
- **URL**: `/api/users/{id}`
- **Método**: `DELETE`
- **Acesso**: Apenas Admin

## Autenticação

Todos os endpoints protegidos requerem um token JWT no cabeçalho:
```
Authorization: Bearer <token_jwt>
```

## Níveis de Acesso

O sistema possui dois níveis de acesso:
1. `ROLE_USER` - Usuário comum
2. `ROLE_ADMIN` - Administrador

### 📝 Licença
Este projeto está sob a licença MIT. Veja o arquivo LICENSE para mais detalhes.
