# Spring Security Study

Projeto de estudo de autenticação com **Spring Security** e **JWT**. Permite cadastrar usuários, fazer login e acessar rotas protegidas usando um token.

## Tecnologias

- Java 17
- Spring Boot 4 (Web, Security, Data JPA, Validation)
- JWT ([java-jwt](https://github.com/auth0/java-jwt))
- MariaDB + Flyway
- Lombok

## Endpoints

| Método | Rota             | Descrição                              | Autenticação |
|--------|------------------|----------------------------------------|--------------|
| POST   | `/auth/register` | Cadastra um usuário                    | Não          |
| POST   | `/auth/login`    | Faz login e retorna um token JWT       | Não          |
| GET    | `/test`          | Rota protegida para testar o token     | Sim          |

Para acessar rotas protegidas, envie o token no header:

```
Authorization: Bearer <token>
```

## Como rodar

1. Crie o banco de dados:
   ```
   mariadb -u root -p -e "CREATE DATABASE spring_security_study;"
   ```
2. (Opcional) Defina as variáveis de ambiente `DB_USER`, `DB_PASSWORD` e `JWT_SECRET`.
3. Inicie a aplicação:
   ```
   ./mvnw spring-boot:run
   ```

As tabelas são criadas automaticamente pelo Flyway. O arquivo `Requests.http` tem exemplos de requisições para testar a API.
