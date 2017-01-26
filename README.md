# ACHEI

Para começar a executar o projeto, siga os passos abaixo:
```shell
bundle install
bundle exec figaro install
```
Crie um usuário no PostgreSQL chamado `achei` da seguinte maneira:
```shell
sudo -u postgres createuser -s achei
sudo -u postgres psql
\password achei
\q
```
A gem `figaro` (instalada no primeiro passo) irá gerar o arquivo não versionado `config/application.yml`. Nele, insira a senha para o seu usuário `achei` do PostgreSQL:
```yml
ACHEI_DATABASE_PASSWORD: senha_sem_aspas
```
Feito isto, execute os passos abaixo:
```shell
rake db:create
rake db:migrate
```
Para finalmente executar a aplicação, execute:
```shell
rails s
```