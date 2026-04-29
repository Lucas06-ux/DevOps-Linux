API REST com Java Spring Boot + MySQL rodando em Docker.

🚀 Como subir o projeto
bash sudo docker run -d --name mysql2 -e MYSQL_ROOT_PASSWORD=123456 -p 3307:3306 mysql:8.0 ./mvnw spring-boot:run -DskipTests -Dspring-boot.run.fork=false

🌐 Acessar a interface
Abra no navegador:

http://102.37.218.127:8080/usuarios

📡 Endpoints
Listar todos os usuários
GET http://102.37.218.127:8080/usuarios

Cadastrar usuário
``` POST http://102.37.218.127:8080/usuarios
 Content-Type: application/json

{ "nome": "João Silva", "email": "joao@email.com
" }```

🗄️ Acessar o banco de dados
bash sudo docker exec -it mysql2 mysql -u root -p projeto

Senha: 123456

Comandos SQL úteis
sql SELECT * FROM usuario; INSERT INTO usuario (nome, email) VALUES ('Maria', 'maria@email.com
'); DELETE FROM usuario WHERE id = 1; exit

🐳 Containers
Container Imagem Porta
projeto-api Java 17 + Spring Boot 8080
mysql2 MySQL 8.0 3307
