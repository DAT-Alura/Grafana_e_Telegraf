# Para saber mais

## Criando o painel de Erros 404

Para criar o painel de Erros 404 siga os passos abaixo:

1) Clique no botão Add panel;

2) Em seguida clique em Add Query, logo na parte superior temos que deixar a opção server com valor ubuntu-bionic;

3) Agora no campo Query selecione a opção InfluxDB;

4) Logo abaixo no campo A (onde tem a consulta em si, com os campos FROM, WHERE, SELECT, GROUP BY), clique no botão com ícone lápis (nome do campo é: ```Toggle text edit mode```) que fica no lado direito, para podermos ir para o modo de edição de texto;

5) No campo de texto que aparecer, devemos ver uma consulta padrão semelhante a essa:
```sql
SELECT mean("value") FROM "measurement" WHERE $timeFilter GROUP BY time($__interval) fill(null)
```
Altere essa consulta para:
```sql
SELECT count("request") FROM "apache_access_log" WHERE ("host" =~ /^$server$/)  AND "resp_code" = '404'  AND $timeFilter AND "agent" != 'Go-http-client/1.1' AND agent != 'worldping-api'
```
6) Agora clique na opção __Visualization__, e no seletor ```Visualization``` selecione a opção ```Gauge```;

7) No campo ```Calc``` do painel __Display__ selecione a opção ```Total```;

8) No campo ```Unit``` no painel __Field__ selecione a opção ```Misc``` e depois a opção ```none``` (dentro de ```Misc```);

9) No campo ```Min``` que fica logo abaixo do campo __Unit__, digite ```0``` (zero);

10) Agora na opção __General__ no campo ```Title``` coloque o nome ```Erros 404```;

11) Pronto, agora é só voltar para o Dashboard e você vai poder visualizar o novo painel __Erros 404__.
