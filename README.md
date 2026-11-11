
# 🐾 Pet Mania API Challenge

Uma API RESTful completa desenvolvida em **Spring Boot** para o sistema de adoção de animais **Pet Mania**. A aplicação permite cadastrar, consultar, editar e remover pets para adoção, integrada a um banco de dados MySQL e consumida por uma interface web moderna.

---

## 📸 Demonstração do Sistema

### 🎨 Interface Web (Frontend)
Visualização dos pets cadastrados e disponíveis para adoção:

---

## 🛠️ Tecnologias Utilizadas

- **Java 17+**
- **Spring Boot 3.x**
  - Spring Web (API RESTful)
  - Spring Data JPA (Persistência de Dados)
- **MySQL Database** & MySQL Workbench
- **Postman** (Testes de endpoints)
- **Maven** (Gerenciador de dependências)

---

## 🗄️ Estrutura do Banco de Dados (MySQL)

O sistema utiliza a tabela `pet` no banco de dados MySQL para armazenar as informações dos animais:

```sql
CREATE DATABASE pet_mania_api_challenge;
USE pet_mania_api_challenge;

SELECT * FROM pet;
```

### **Tabela `pet`**
| Coluna | Tipo | Descrição |
| :--- | :--- | :--- |
| `id` | `BIGINT` (PK) | Identificador único do pet |
| `nome` | `VARCHAR` | Nome do pet (ex: *"Abobrinha"*) |
| `especie` | `VARCHAR` | Espécie (ex: *"Cachorro"*, *"Gato"*) |
| `raca` | `VARCHAR` | Raça do pet |
| `idade` | `INT` | Idade em anos |
| `sexo` | `VARCHAR` | Sexo (*"Macho"* / *"Fêmea"*) |
| `porte` | `VARCHAR` | Porte (*"Pequeno"*, *"Médio"*, *"Grande"*) |
| `personalidade`| `VARCHAR` | Descrição comportamental |
| `foto` | `TEXT` | URL da imagem do pet |
| `disponivel` | `BOOLEAN` | Status para adoção (`true` / `false`) |

#### 📊 Visualização no MySQL Workbench & Postman (POST):
![Banco de Dados MySQL](./assets/database_mysql.png)

---

## 🚀 Endpoints da API

Base URL: `http://localhost:8080/api/pets`

| Método | Endpoint | Descrição |
| :--- | :--- | :--- |
| `GET` | `/api/pets` | Retorna a lista de todos os pets cadastrados |
| `GET` | `/api/pets/{id}` | Busca um pet específico pelo ID |
| `POST` | `/api/pets` | Cadastra um novo pet |
| `PUT` | `/api/pets/{id}` | Atualiza as informações de um pet |
| `DELETE` | `/api/pets/{id}` | Remove um pet do sistema |

---

## 🧪 Testando a API no Postman

### **1. Listar Pets (`GET /api/pets`)**
Retorna todos os pets gravados no banco de dados em formato JSON:

![Resultado GET Postman](./assets/postman_get_pets.png)

**Exemplo de Resposta JSON (`200 OK`):**
```json
[
  {
    "id": 2,
    "nome": "Abobrinha",
    "especie": "Gato",
    "raca": "Abobrinha",
    "idade": 2,
    "sexo": "Macho",
    "porte": "Pequeno",
    "personalidade": "Muito fofo",
    "foto": "https://newr7-r7-prod.web.arc-cdn.net/resizer/v2/ECECFL5MD5KYFKT40S3G4Y2C7Q.jpg...",
    "disponivel": true
  }
]
```

### **2. Cadastrar Pet (`POST /api/pets`)**
**Body (JSON):**
```json
{
  "nome": "Abobrinha",
  "especie": "Cachorro",
  "raca": "Abobrinha",
  "idade": 2,
  "sexo": "Macho",
  "porte": "Pequeno",
  "personalidade": "muito fofo",
  "foto": "https://newr7-r7-prod.web.arc-cdn.net/...",
  "disponivel": true
}
```

---

## ⚙️ Como Executar o Projeto Localmente

### **Pré-requisitos:**
- Java 17+ instalado
- MySQL instalado e rodando na porta `3306`
- Git

### **Passo a Passo:**

1. **Clonar o Repositório:**
   ```bash
   git clone https://github.com/IgorBarretodeLima/pet-mania-api-challenge-.git
   cd pet-mania-api-challenge-
   ```

2. **Configurar o Banco de Dados:**
   Abra o arquivo `src/main/resources/application.properties` e atualize com suas credenciais do MySQL:
   ```properties
   spring.datasource.url=jdbc:mysql://localhost:3306/pet_mania_api_challenge?createDatabaseIfNotExist=true
   spring.datasource.username=seu_usuario
   spring.datasource.password=sua_senha
   spring.jpa.hibernate.ddl-auto=update
   spring.jpa.show-sql=true
   ```

3. **Executar a Aplicação:**
   ```bash
   ./mvnw spring-boot:run
   ```

4. **Acessar a Aplicação:**
   - API REST: `http://localhost:8080/api/pets`
  


   ## Amostras

   <img width="1909" height="943" alt="Captura de tela 2026-11-11 163349" src="https://github.com/user-attachments/assets/a1d11fbc-80a8-49d0-a851-0b823e723510" />

   <img width="1379" height="676" alt="Captura de tela 2026-11-11 163335" src="https://github.com/user-attachments/assets/43205be6-7982-45b6-9c8e-41bd8d680c3e" />

<img width="1072" height="910" alt="Captura de tela 2026-11-11 164229" src="https://github.com/user-attachments/assets/bfd8757d-12fb-4431-8f42-7e16a43b625d" />


