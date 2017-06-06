---
layout: post
title:  "Primeiros contatos com BDD e TDD"
date:   2017-03-23 09:16:36 -0300
categories: paulinho les20171
---

## Geral

Numa atividade ([repositório](https://github.com/adlerosn/exLes1)), foi requisitado programar alguns itens usando BDD e TDD.

Para demonstrar que é útil, a atividade podia ter parado na segunda questão; a terceira e a quarta questões só serviram para cansar.

Desenvolver orientado a comportamento e testes se demonstrou útil para repetir uma bateria de testes quando um pequeno erro de lógica (ou digitação?) fazem com que o código tenha um comportamento diferente do esperado, que é convenientemente testado em massa a partir de um único comando no terminal que testa todos os casos fornecidos duma vez só.

Em contrapartida, escrever o arquivo Gherkin é uma tarefa tediosa que dá desânimo só de pensar que ele terá de ser escrito se mistura ao desânimo de ter de codificar uma solução que não será utilizada; já a parte de traduzir as linhas de Gherkin para um arquivo de testes foi bem mais fluida e menos penosa.

Portanto, desenvolver com BDD e TDD demonstrou que, embora adicione passos ao desenvolvimento, economiza-se tempo e paciência com tais práticas. Infelizmente, realizar testes unitários em algumas frameworks não é algo trivial e não garante que o usuário aprovará.

## Exercício 1: Ar condicionado

Não ficou claro qual a fórmula que determina a temperatura da sala a partir do ar condicionado; adotei que a média da temperatura estimada da sala com a temperatura no duto de ar é a temperatura percebida pelos alunos.

## Exercício 2: Imposto de renda

Scenario Outline poupou tempo ao replicar o mesmo caso de teste com campos diferentes.

## Exercício 4: Calculadora em notação polonesa reversa

Construir um parser dá trabalho. Usei o "cheat" de expressão regular para ter o tokenizador pronto, mesmo assim ficou maior que esperava.

## Exercício 3: Sistema de navegação fictício

Parser para quê? Um simples matcher resolve o problema com menos dores de cabeça.

Além disso, não ficou claro como a cidade é selecionada. Assumi que é a cidade cuja coordenada está mais à coordenada geográfica mencionada (north → northmost city; east → eastmost city).

## Padrões de projeto

"Tudo em excesso faz mal". Um problema geralmente "pede" padrão de projeto, ficando mais difícil ou prolixo de resolver caso não utilizado. Em algumas questões, foi tanto padrão de projeto que a solução ficou maior usando padrões do que se não fosse usado.