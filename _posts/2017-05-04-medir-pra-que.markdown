---
layout: post
title:  "Medir? Pra que?"
date:   2017-05-04 10:46:25 -0300
categories: paulinho les20171
---

A experiência em tentar medir a qualidade do software que está sendo desenvolvido está sendo bem frustrante.

Confiando nos resultados do SonarQube com o plugin TsLint gerados localmente, permanecemos desenvolvendo tranquilamente sem atentarmo-nos se as métricas realmente estavam sendo calculadas.

Após uma breve desconfiança dos resultados apresentados pelo Sonar ao identificar manualmente duplicidade de código cujo tamanho é maior que 50 tokens, e observar que esta não foi detectada; percebemos também que as outras métricas também não estavam sendo contabilizadas. A única métrica que funcionou foi (parcialmente) já era obtida a partir do compilador do TypeScript.

Além disso, observou-se que ao utilizar classes que usam implementações nativas, o código deixa de funcionar de funcionar em browsers desktop. As ferramentas de teste automatizado de código ou usam o console do NodeJS, ou um browser desktop para executar. Isso implica que em ambos os casos, não é possível testar nenhum caso de teste se um banco de dados relacional persistente for utilizado.

Outra frustração foi uma atualização do framework ionic que impôs uma perda de trabalho pronto ao projeto, sendo necessário retrabalho. Isso atrasou em uma semana a constatação de que testar com as ferramentas escolhidas não será possível.

A idéia inicial era utilizar gráficos X-bar e R sobre o GQM do projeto, medido ao final de cada uma das 10 sprints do projeto. Devido à influência negativa das tarefas de outras disciplinas sobre o tempo disponível para desenvolver o projeto, as várias métricas do GQM foram consideradas a ser atreladas à única métrica: pontos cumpridos por sprint; entretanto seria um gráfico sem propósito, pois o gráfico de burndown já supre tal necessidade.

Medir? Sim! Pra quê? Para saber se algo está indo mal, e onde está indo mal. E sabemos que estamos atrasados em nosso cronograma, infelizmente.