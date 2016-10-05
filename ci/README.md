# CI

Projeto para a configuração de um ambiente de Continuous Integration.

### setup

``` shell
docker-compose up
```

### jenkins

O Jenkins está configurado para rodar na porta 8082. O password é gerado aleatoriamente para o usuário `admin`, portanto, é importante conferir o log do docker-compose e procurar pelo trecho:

```
jenkins_1      | Jenkins initial setup is required. An admin user has been created and a password generated.
jenkins_1      | Please use the following password to proceed to installation:
jenkins_1      | 
jenkins_1      | <novo_password_gerado>
jenkins_1      | 
jenkins_1      | This may also be found at: /var/jenkins_home/secrets/initialAdminPassword
```

Após logar com a senha, escolha os plugins indicados pela comunidade, instale o plugin Publish Html, após crie um usuário e aproveite o jenkins ;)

### artifactory

O Artifactory está configurado para rodar na porta 8081. O user `admin` tem a senha padrão `password`.

### sonarqube

O sonar está configurado para rodar na porta 9000. O user `admin` tem a senha padrão `admin`.