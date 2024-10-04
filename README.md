# evolution-api-docker-compose
Docker compose completo para subir instancia do Evolution Api V2, conta com Redis e Postgres configurados de acordo com a documentação https://doc.evolution-api.com/v2/pt/install/docker

## Instalação:
Clone o repositório:
```
git clone https://github.com/WinyZanin/evolution-api-docker-compose
```
Entre na pasta e copie o .env.exemple para .env:
```
cd evolution-api-docker-compose
cp .env.exemple .env
```
Por segurança, troque a chave de api por outra aleatória: (https://guidgenerator.com/)
```
AUTHENTICATION_API_KEY=B6D711FCDE4D4FD5936544120E713976
```
Suba os containers com docker compose
```
docker compose up -d
```
Para verificar se deu certo, acesse em seu navegador http://localhost:8080 deve aparecer:
>{"status":200,"message":"Welcome to the Evolution API, it is working!","version":"2.1.1","clientName":"evolution_exchange","manager":"http://localhost:8080/manager","documentation":"https://doc.evolution-api.com"}

## Serviços:
Por padrão alguns serviços do evolution vem desativados, você pode ativar dentro do .env:
```
# Chatwoot - Environment variables
CHATWOOT_ENABLED=true
```
Toda alteração para ter efetividade, deve atualizar os containers:
```
docker compose up -d
```
