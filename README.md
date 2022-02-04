# **Desafio Tech (DevOps) | Processo Seletivo Estágio Frexco**

Para esse desafio eu utilizei o WSL2 com Ubuntu 20.04, na minha máquina com WIndows 10, também fiz os mesmos testes em outra máquina com Ubuntu 21.04, Docker 20.10.12 e Dokcer-compose 1.29.2.

Para a aplicação utilizei o Nginx como servidor local, criando uma rede interna no arquivo ``docker-compose.yml`` para obter acesso pela porta 80

Utilizei a imagem do Node Alpine por ser uma versão mais leve para uma aplicação simples.

---

Para subir a aplicação no docker, é necessário somente o comando:

````
docker-compose up -d
````

Ao digitar o comando ````docker ps```` temos as seguintes informações:

````
CONTAINER ID   IMAGE          COMMAND                  CREATED       STATUS       PORTS                    NAMES
2022499c2caa   nginx:latest   "/docker-entrypoint.…"   3 hours ago   Up 3 hours   0.0.0.0:80->80/tcp       nginx
c99ebf9072d9   devops_app     "docker-entrypoint.s…"   3 hours ago   Up 3 hours   0.0.0.0:4123->4000/tcp   frexco-app
````


Ao final de todo o processo de build a aplicação irá rodar em:

````
http://localhost:80/
````
---

Para fechar a aplicação docker é só digitar o comando:

````
docker-compose down
````



## Fazendo o Deploy
Para o deploy, utilizei o Heroku. Levando em consideração que o Heroku está instalado e que há uma conta logada, entre no diretório da aplicação e digite os comandos nessa ordem e faça o que se pede:

````
heroku login
````

````
heroku create nomedoapp
````


````
git push heroku master
````

O Deploy pode ser acessado nesse link: [https://dry-atoll-87491.herokuapp.com/](https://dry-atoll-87491.herokuapp.com/) 

> Obs: O link ficou sem o nome do app, pois como estava aprendendo, o heroku gera um nome aleatório, resolvi manter o mesmo para concluir o teste.

---


Para a elaboração desse desafio, utilizei algumas informações que encontrei na documentação do docker e alguns tutoriais, com algumas alterações e fazendo do meu modo e o modo mais fácil para eu poder entender, no começo houve alguns erros em algumas linhas do Dockerfile, mas consegui corrigir durante esses dias em que estava aprendendo. 
No meu estágio anterior trabalhei com docker em uma aplicação PHP e conheço o básico e suas funcionalidades, não foi muito difícil de realizar esse desafio por eu ja ter um certo conhecimento dessa tecnologia. 

---

Links de referência:

[Using React.js with Docker
](https://www.pluralsight.com/guides/using-react.js-with-docker)

[Deploy Reactjs com Docker](https://kledenai.medium.com/deploy-reactjs-com-docker-1769cf7a5f74)