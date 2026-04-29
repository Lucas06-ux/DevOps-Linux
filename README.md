CP2 — DevOps: Azure VM + Docker + Spring Boot + MySQL

👤 Aluno
Nome: Lucas Giannini
RM: (coloque seu RM aqui)

🌐 Endpoint para Correção
Acesse no navegador: http://102.37.218.127:8080/usuarios

📋 Rotas da API REST

Método | Rota | Descrição
GET | /usuarios | Lista todos os usuários
POST | /usuarios | Cadastra novo usuário

🏗️ Arquitetura

Nuvem: Azure — Ubuntu VM
Backend: Java 17 + Spring Boot
Banco: MySQL 8.0
Containerização: Docker
Testes: Insomnia / curl

🚀 Como Executar em uma Nova VM

Pré-requisitos
VM com Ubuntu 22.04
Porta 8080 liberada no NSG
Docker instalado
Java 17 instalado

Passos

git clone https://github.com/Lucas06-ux/DevOps-Linux.git
cd DevOps-Linux

sudo docker run -d \
  --name mysql2 \
  -e MYSQL_ROOT_PASSWORD=123456 \
  -p 3307:3306 \
  mysql:8.0

./mvnw spring-boot:run -DskipTests -Dspring-boot.run.fork=false

Aguarde a mensagem nos logs:

Started ProjetoApplication

🧪 Testes da API

Listar usuários:

curl http://102.37.218.127:8080/usuarios

Cadastrar usuário:

curl -X POST http://102.37.218.127:8080/usuarios \
-H "Content-Type: application/json" \
-d '{"nome":"Teste","email":"teste@email.com"}'

🗄️ Banco de Dados

Acessar MySQL:

sudo docker exec -it mysql2 mysql -u root -p

Senha: 123456

Selecionar banco:

USE projeto;

🐳 Containers

Container | Imagem | Porta
projeto-api | Java 17 + Spring Boot | 8080
mysql2 | MySQL 8.0 | 3307
