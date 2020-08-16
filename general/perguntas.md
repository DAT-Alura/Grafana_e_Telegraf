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

## Aula 3

1 - Sobre a análise de métricas de um sistema, deve-se considerar alguns aspectos na coleta e a afirmativa que valida esse conceito é:

- Devemos coletar principalmente as métricas da aplicação. A infraestrutura é complementar e sua análise deve ser feita somente em produção
- A análise da infraestrutura deve ser feita em um evento chamado post mortem, que consiste na análise subsequente a um evento de falha
- __A coleta e análise de métricas de vários tipos contribui para a saúde de uma aplicação e é tão importante quanto qualquer outro passo no fluxo de entrega de um produto__

2 - Considerando o monitoramento da infraestrutura, quais indicadores podem demonstrar a saúde da aplicação?

- Processador. Com o histórico dessa métrica, pode-se avaliar o comportamento do sistema durante as horas de pico da aplicação e em conjunto com os logs gerados pelo sistema, pode-se prever comportamento futuro e provisionar mais recursos
- __As duas afirmativas citadas estão corretas, mas recomenda-se ainda adicionar mais métricas para aumentar a cobertura do monitoramento__
- Memória. Com o histórico dessa métrica, pode-se avaliar o comportamento do sistema durante as horas de pico da aplicação e em conjunto com os logs gerados pelo sistema, pode-se prever comportamento futuro e provisionar mais recursos

3 - Gerir a utilização do disco no servidor da aplicação pode prevenir alguns problemas como:

1) Não ter espaço para armazenar os logs da aplicação, podendo, em alguns casos extremos ou ainda características da arquitetura, interromper o funcionamento da instância

2) Mesmo que a utilização do disco não esteja em 100%, é válido coletar as métricas dos inodes do sistema, pois, mesmo com espaço, sem inodes disponíveis, não podemos criar novos arquivos e isso compromete o funcionamento da aplicação

Dos problemas citados acima, qual(is) realmente pode(m) ser prevenido(s) com a utilização do disco no servidor da aplicação?

- __Ambos os problemas__
- O problema 1
- O problema 2

4 - Sobre analisar o consumo de memória nos servidores de aplicação, analise as afirmativas abaixo:

1) A análise do consumo de memória é muito útil para prever períodos ou eventos onde a nossa aplicação pode precisar de novos recursos, como um evento de vendas importante

2) Em uma aplicação que sua inicialização depende da quantidade de memória alocada, como o JBoss, a análise da métrica, durante um período em conjunto com a análise dos logs, pode determinar uma alteração na capacidade do servidor

Qual(is) sentença(s) reflete(m) a(s) motivação(ões) para a coleta dessa métrica?

- Apenas a sentença 1
- Apenas a sentença 2
- __Ambas as sentenças__

## Aula 4

1 - É possível analisar métricas de servidores Docker distintos? Como?

- Podemos utilizar o plugin do Docker do Telegraf, e apontar para outras instâncias do Docker
- __Ambas as alternativas__
- Utilizar o Telegraf em outros servidores e apontar sua configuração para o servidor onde o InfluxDB está rodando, e no painel, podemos utilizar as variáveis do dashboard para mudar qual instância gostaríamos de visualizar

2 - O que é responsável por permitir métricas adicionais no Grafana, além das métricas padrão?

- Variáveis de dashboards para separar as métricas que desejamos visualizar
- __Diferentes measurements no InfluxDB__
> Alternativa correta! Como o InfluxDB é um banco de dados independente, podemos apontar os plugins para gravar dados em measurements distintos, como por exemplo o Docker.
- Múltiplos data sources
