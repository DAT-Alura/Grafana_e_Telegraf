# Perguntas

## Aula 1

1 - Em quais casos devemos considerar montar um ambiente de monitoramento?

- Somente quando o nosso sistema atingir uma certa maturidade, pois não devemos disponibilizar recursos de monitoramento no início do projeto
- __O monitoramento deve ser uma prática comum para garantir a qualidade, inclusive em estágios de pré-produção__
> Alternativa correta! É extremamente importante olhar para a saúde do nosso ecossistema de software. Todos os dados coletados e as análise feitas auxiliam na tomada de decisões, reação a problemas e prevenção de falhas.
- Somente após a entrega do software, pois o objetivo é corrigir os erros assim que eles aparecerem

2 - Qual a infraestrutura básica para um ambiente de monitoramento?

- Preferencialmente, devemos utilizar uma solução terceirizada para monitoramento
- __Podemos utilizar a mesma infraestrutura da aplicação__
> Alternativa correta! Nos estágios iniciais, podemos utilizar a mesma infraestrutura, mas após certa maturidade, devemos separar os recursos, para não comprometer a saúde da aplicação.
- Um servidor exclusivo para o monitoramento, pois, como vamos monitorar somente o ambiente de produção, vamos precisar de muito recurso

3 - Quais as principais características de dashboards, considerando que podemos visualizar os dados brutos da aplicação?

- São complementares à análise tradicional do comportamento do sistema. Com uma precisão próxima da real, as métricas exibidas são importantes para insights do comportamento geral
- __São complementares à análise tradicional do comportamento do sistema. Os valores são precisos, pois foram coletados em tempo de execução__
- Preferencialmente devemos analisar os logs da aplicação e do sistema. Os dashboards são imprecisos e lentos.

## Aula 2

1 - Sobre o conceito de coletores de métricas e bancos de dados temporais (time series databases), podemos afirmar, respectivamente:

- __São complementares, o primeiro faz uma "raspagem" de dados no sistema e injeta os valores no segundo, que mantém um histórico temporal dos dados, para análises futuras__
- São independentes, o primeiro, sozinho, é capaz de analisar as métricas e exibir o comportamento do sistema ao passar do tempo. O segundo deve ser utilizado quando for necessária a análise de séries de tempo maiores que um dia
- Eventualmente podemos utilizar somente o Grafana para armazenar os dados em conjunto com o Telegraf

2 - O que melhor define um data source no Grafana?

- É a parte responsável por configurar onde os dados serão armazenados no Grafana
- É nessa parte do Grafana que definimos o principal repositório de dados para análise do comportamento do sistema que eles aparecerem
- __É nessa parte do sistema que definimos múltiplos repositórios de dados para montarmos nossos dashboards__
