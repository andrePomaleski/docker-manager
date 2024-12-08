# Docker Manager

Este projeto é uma API para gerenciar containers Docker. Ele fornece endpoints para criar, listar, inspecionar, iniciar, parar, reiniciar e remover containers. A API foi construída com Spring Boot.

## Tecnologias Utilizadas

- **Spring Boot**: Framework para construção da API.
- **Docker**: A API interage com o Docker para gerenciar containers.
- **Java 21**: Linguagem de programação para o back-end.
- **Maven**: Para gerenciamento de dependências e build do projeto.

## Endpoints da API

### 1. `POST /api/containers`
Cria um novo container a partir de uma imagem Docker.

- **Parâmetro**: `imageName` (obrigatório) - O nome da imagem Docker para criar o container.
- **Exemplo de request**:
    - URL: `/api/containers`
    - Parâmetro: `imageName=docker.io/hello-world`
    
**Nota**: O parâmetro `imageName` deve ser o nome completo da imagem Docker (por exemplo, `docker.io/hello-world`). Certifique-se de alterar esse parâmetro de acordo com a imagem que deseja usar.

### 2. `GET /api/containers`
Lista todos os containers Docker em execução.

- **Exemplo de request**:
    - URL: `/api/containers`
    
### 3. `GET /api/containers/{containerName}`
Obtém as informações sobre um container específico.

- **Parâmetro**: `containerName` (obrigatório) - O nome ou ID do container.
- **Exemplo de request**:
    - URL: `/api/containers/my-container`

### 4. `POST /api/containers/{containerName}/start`
Inicia um container.

- **Parâmetro**: `containerName` (obrigatório) - O nome ou ID do container.
- **Exemplo de request**:
    - URL: `/api/containers/my-container/start`

### 5. `POST /api/containers/{containerName}/stop`
Para um container em execução.

- **Parâmetro**: `containerName` (obrigatório) - O nome ou ID do container.
- **Exemplo de request**:
    - URL: `/api/containers/my-container/stop`

### 6. `POST /api/containers/{containerName}/restart`
Reinicia um container.

- **Parâmetro**: `containerName` (obrigatório) - O nome ou ID do container.
- **Exemplo de request**:
    - URL: `/api/containers/my-container/restart`

### 7. `DELETE /api/containers/{containerName}`
Remove um container.

- **Parâmetro**: `containerName` (obrigatório) - O nome ou ID do container.
- **Exemplo de request**:
    - URL: `/api/containers/my-container`

## Como Testar

1. **Baixar uma Imagem Docker**:
   Antes de testar a API, você precisa ter uma imagem Docker disponível. Por exemplo, você pode usar a imagem `hello-world` com o seguinte comando:

   ```bash
   docker pull hello-world
   
2. **Clone o projeto**:
   git clone https://github.com/andrePomaleski/docker-manager.git
   cd docker-manager

3. **Compile e rode as aplicações com o Maven**:
   mvn spring-boot:run


