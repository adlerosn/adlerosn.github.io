---
layout: post
title: "O Trabalho Integrado de LES e sua retroalimentação"
date: "2017-06-05 17:32:30 -0300"
categories: paulinho les20171
---

O trabalho semestral, até o momento, foi nada além de aplicar conceitos e boas práticas - bem, é o que deveria ter sido feito. Senta que lá vem história!

Não bastava estar com um certo medo da disciplina, a qual alguns diziam ser difícil, sendo o que mais me aterrorizou durante os dias que antecediam o início do semestre foi o código imenso que certamente me aguardava. Ledo engano: o mais difícil foi a parte de lidar com pessoas.

Durante as primeiras aulas, veio o primeiro problema: qual empresa que tivesse um problema real a ser resolvido? E nos foi concedido tempo para decidir o problema, que durante aproximadamente dois minutos um olhando para o outro, passando a palavra em círculos (ou quase). Mencionei duma lanchonete próxima a onde moro, a dependência deles com papel e as dificuldades em compreender o garrancho escritos enquanto o estabelecimento está cheio, e a possibilidade de automatizar algumas tarefas.

Foi um desafio criar coragem para ir à lanchonete num horário sem movimento sem ser para ser para consumir algo; tão difícil que o Pitch foi apresentado antes da primeira visita. Faltando três semanas para a primeira entrega criei coragem e fui, para receber a seguinte notícia: o sistema proposto no Pitch já estava nos estágios finais de implantação, sendo este processo iniciado há 9 meses (na data da visita); em contrapartida, o administrador do estabelecimento relatou a necessidade de obter lista de compras de supermercado mais barata.

Com o problema definido, foi marcada uma reunião entre os integrantes do grupo, onde colaborativamente, de fato, começamos o projeto - a poucos dias de um deadline.

Configurar o repositório para executar a métricas de software no SonarQube online demandou muito esforço: simplesmente não funcionava; mas no nosso arquivo de configuração faltava o campo "organization".

A primeira entrega foi feita às pressas. Foi um sábado sem dormir e um domingo torturante; tudo isso para tirar a documentação do zero. De aprendizado, ficou que orientar o projeto aos deadlines foi uma péssima escolha.

Visando evitar tal situação, Yago começou a base de código; mas todo *commit* era feito diretamente na *branch* *master*, o que impossibilitava paralelizar o desenvolvimento ao gerar conflitos constantemente. Mesmo após instruído a usar branches secundárias e depois fazer pull request, os novos commits continuavam aparecendo diretamente na *branch* *master*.

Impossibilitado de alterar o código sem quebrar o *push* automático da IDE do Yago, notei que o código simplesmente não estava sendo testado de forma alguma, portanto pesquisei formas de testar e contatei-o, o qual chegou a afirmar que os testes com backend em SQLite seriam feitos através do celular conectado ao computador - o que sabia previamente que não era possível. Então pesquisei formas de inserir o SQLite no browser; ainda preso ao TypeScript, ignorei o SQL.js durante algumas semanas e, quando desisti, tive de adicionar a biblioteca na tag `head` do HTML principal; um local onde certamente não haveria conflitos no *push*.

Quando o repositório passou uma semana sem alterações, peguei o código para ler: desisti em menos de 3 minutos ao ver duplicações de código óbvias e grosseiras, que podiam ter sido facilmente evitadas usando herança. Neste momento estava certo de algo: se ajustar o código não fosse possível, este deveria ser completamente reescrito. Entrei em contato com o Yago, quem simplesmente deixou completamente por minha conta refatorar o código pois, segundo ele "não vejo onde ou como deixar genérico"; na mesma ocasião, rejeitou uma implementação de ActiveRecord que havia preparado para usar LocalStorage, uma tecnologia que funciona tanto em browsers quanto no aplicativo.

Em uma semana de refatoração, consegui deixar 1 dos 6 métodos da classe de DAO numa classe abstrata, dada a não-reusabilidade do código. Se continuasse nessa velocidade, o semestre encerraria e todos seríamos reprovados. Parti para algo que estava atrasado e necessitava ser adicionado ao projeto "para ontem": os casos de teste.

A Framework Ionic foi projetada negligenciando testes unitários; consequência disso foi que gastei horas pesquisando como realizá-los. Encontrar um tutorial não foi difícil, mas sim fazê-los funcionar; quando terminei, observei que nenhuma classe de backend não era testável. O backend tinha de ser trocado, mas guardei isso para mim pois mais uma entrega estava à vista e a documentação necessitava de minha atenção.

Entrega feita, me vi no dilema: ou usamos o que aprendemos ao longo das *sprints*, ou continuaremos enrolados (e reprovação iminente). Mudar não era opção: era o caminho mais promissor.

Após entregue e descansado (ok, menos exausto), simplesmente avisei: "vou trocar o backend e parte do código terá de ser reescrita". Tentei usar a framework TypeORM enquanto tentava salvar uma mínima parte do já tinha sido escrito: só sobrou a tela de início. **Apaguei sem dó**. Refiz a modelagem de dados, pois a anterior não usava *clean code* e estava confusa: primeiro um UML rascunhado numa folha de caderno que depois virou código.

* Classes de modelo: 1 hora e meia;
* Fazer o TypeORM funcionar: 2 horas;
* Criar um DAO genérico: 4 horas;
* Criar todos os DAOs: 30 minutos;
* Criar uma tela genérica de listagem: 3 horas;
* Criar uma tela genérica de formulário: 2 horas;
* Criar 4 listagens com seus respectivos formulários de inserção/edição: 5 horas.

E finalmente o código estava no mesmo ponto que antes, porém testável e duma forma que as telas dependiam de abstrações: era apenas implementar alguns poucos métodos abstratos.

Ao término da terceira semana (domingo à noite), restavam apenas dois requisitos funcionais, então Yago fez o requisito funcional de compartilhamento em redes sociais e eu fiz os gráficos de histórico de preços; na terça-feira à noite, compilei e submeti o APK na release `0.0.1-beta3`.
