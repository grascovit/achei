# ACHEI

To run the API, follow the steps below:
```shell
bundle install
bundle exec figaro install
```
Create a PostgreSQL user named `achei` like this:
```shell
sudo -u postgres createuser -s achei
sudo -u postgres psql
\password achei
\q
```
The `figaro` gem (installed on the first step) will generate the unversioned file `config/application.yml`. Insert your password for the `achei` user in it:
```yml
ACHEI_DATABASE_PASSWORD: your_password_without_quotes
```
After this, execute the following steps:
```shell
rake db:create
rake db:migrate
```
Finally, run the API:
```shell
rails s
```