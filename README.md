# Explorando Práticas de Teste

Neste exercício, vamos explorar práticas de teste em sistemas reais utilizando a ferramenta [TestMiner](https://andrehora.github.io/testminer).

O TestMiner permite visualizar e analisar testes de software em repositórios do GitHub, fornecendo dados sobre como os projetos organizam seus testes, como eles evoluem entre versões e quais bibliotecas de teste são utilizadas.
Explore a ferramenta antes de começar para se familiarizar com seu funcionamento.

---

## Passo 1: Selecionar um repositório

Escolha um repositório real que possua testes escritos na linguagem de sua preferência.
Abaixo estão alguns links para ajudá-lo a encontrar projetos interessantes:

- **Python:** https://github.com/topics/python?l=python
- **JavaScript:** https://github.com/topics/javascript?l=javascript
- **TypeScript:** https://github.com/topics/typescript?l=typescript
- **Java:** https://github.com/topics/java?l=java

## Passo 2: Explorar o repositório selecionado

Busque o repositório escolhido no [TestMiner](https://andrehora.github.io/testminer) e analise os dados de teste gerados pela ferramenta.

## Passo 3: Explicar uma prática de teste

Com base nos dados obtidos, selecione uma prática ou dado de teste relevante e explique-o com suas próprias palavras.

---

## Instruções de entrega

1. Faça um `fork` deste repositório (saiba mais sobre forks [aqui](https://docs.github.com/pt/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo)).
2. Responda às questões abaixo diretamente neste arquivo `README.md` do seu fork. Pode adicionar imagens para enriquecer sua explicação.
3. No Moodle, submeta apenas a URL do seu fork.

---

## Respostas

**1. Repositório selecionado:** [prisma](https://github.com/prisma/prisma)

**2. Explicação:** Por se tratar de um repositório responsável pelo desenvolvimento de uma ferramenta de ORM, é esperado que os seus testes utilizem mocks para simular requisições de bancos de dados ao invés de chamadas reais. É exatamente o que está ocorrendo [neste](https://github.com/prisma/prisma/blob/main/packages/client/src/utils/getTestClient.ts) arquivo: ele é responsável por criar um cliente que roda apenas na memória local a fins de teste. Além disso, por ser uma ORM capaz de ser executada em diversas linguagens de bancos de dados diferentes (como [SQL](https://github.com/prisma/prisma/blob/main/packages/client-engine-runtime/src/interpreter/serialize-sql.test.ts), [MongoDB](https://github.com/prisma/prisma/blob/main/packages/migrate/src/__tests__/DbPull/mongodb.test.ts), [CockroachDB](https://github.com/prisma/prisma/blob/main/packages/migrate/src/__tests__/DbPull/cockroachdb.test.ts) etc), é necessário realizar testes pra cada uma dessas linguagens, de modo a garantir que o sistema funcionará de modo coerente independente de qual for selecionada pelo usuário. 
