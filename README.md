## DESCRICÃO GERAL
No trabalho da disciplina (e nessa atividade autônoma), vocês não vão rodar um “projetinho” em Java.  Vocês vão rodar um servidor web Java real, dentro de um contêiner, como na indústria, usando a tecnologia que existia antes dos frameworks modernos. Isso é a base de tudo o que veio depois.
### O que é o projeto?
O projeto é uma aplicação Java Web clássica, baseada em:
- Java Servlet
- JSP
- Executada dentro de um Tomcat
- Empacotada como WAR
- Rodando dentro de um container Docker

### O que é Docker?
Docker é uma forma de empacotar:
-- Aplicação + Servidor + Java + Configuração + Sistema
Em uma “caixinha” chamada contêiner, que roda igual em qualquer máquina.
Sem Docker, vocês teriam de instalar:
- Java certo
- Tomcat certo
- Configurar variáveis
- Configurar porta
- Deploy do WAR manual
- Com Docker: um comando e roda.

### O que é Java Servlet?
Antes de Spring, antes de frameworks modernos, Java Web era assim:
- O navegador faz uma requisição HTTP
- O Servlet (uma classe Java) recebe essa requisição
- Ele processa a lógica
- Ele manda uma resposta HTML (geralmente via JSP)
- Servlet é literalmente:
   Uma classe Java que responde a requisições web.

### O que é o Tomcat?
Tomcat é um servidor de aplicação que sabe:
- Executar Servlets
- Executar JSP
- Entender aplicações Java Web (WAR)
- Ele é quem “roda” o projeto.

### O que é um WAR?
WAR = Web Application Archive
É um .zip especial que contém:
- Classes Java
- JSP
- Configurações
- Bibliotecas
Que o Tomcat sabe executar.

## Preparando o ambiente
### Instalar o Docker Desktop.
- https://www.docker.com/products/docker-desktop/
- Depois de instalar, testar no terminal:

```
docker --version
```

- Se aparecer a versão, está OK.

### Baixar o projeto template do Giithub Classroom
Entrar na pasta do projeto no terminal
Exemplo:
cd Downloads/projeto-oo-web


### Os arquivos do projeto
Observem que existem:
- Dockerfile
- docker-compose.yaml
- pom.xml ou estrutura Java Web
- pasta src
- talvez um .war ou estrutura para gerar

O Dockerfile e o docker-compose.yml ensinam o Docker a montar o ambiente com Tomcat e esse projeto.

### Rodando o projeto (a mágica)
Dentro da pasta do projeto:
Construir a imagem
```
docker-compose up --build -d
```

Isso significa:
“Docker, construa uma máquina com base nesse Dockerfile”

Vai demorar um pouco na primeira vez.

Abrir no navegador
```
http://localhost:8080
```

E a aplicação vai abrir 

### Sequencia de docker importante durante o trabalho:
```
docker compose down
docker compose build --no-cache
docker compose up
```

### O que está acontecendo por baixo dos panos
Quando rodamos o que está abaixo, estamos rodando uma aplicação Java Web real.
- Navegador → localhost:8080 → Docker Container → Tomcat → Servlet → JSP → HTML volta

