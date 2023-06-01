# Roadmap do desafio

## Visão

Minha visão sobre o desafio foi a contrução de uma aplicação web para usuários backoffice com o intuito de fazer upload de um arquivo de vendas dos clientes e cadastrar todas as informações no banco de dados. Isso permitirá a análise de dados e evitará a perda dos detalhes das vendas.

Os requisitos entregues podem ser encontrados [aqui](./CHALLENGE.md#requisitos-funcionais).

## Escolhas

Tecnologias escolhidas para a aplicação e motivos da escolha:

- Next.js
  - Por já ter experiência com o framework.
  - Autonomia na criação de APIs e servidores HTTP.
  - SSR (Server-Side Rendering).
  - Facilidade na integração de autenticação com o NextAuth.
- TRPC.io
  - Comunicação entre cliente e servidor tipada.
  - Como se trata de uma aplicação simples e com prazo curto, não achei necessário construir um ecossistema backend separado.
  - Para aprendizado durante o desafio, nunca tinha usado antes (gostei, mas faltam algumas features simples).
  - Cliente totalmente baseado em hooks para o frontend.
- Prisma
  - Por ser intuitivo e fácil de integrar o ORM.
  - Criação de esquema.
  - Geração de tipos para o ORM.
- PostgreSQL
  - Por já ter usado em outras aplicações.
  - Documentação e recursos facilmente acessíveis.
- TypeScript
- react-hook-form
  - Para criação de formulários sem re-renderizações.
- NextAuth
  - Implementação de autenticação facilitada.
  - Evita a necessidade de implementar autenticação do zero com contexto e serviços de autenticação.
  - Por ser um requisito bônus, não achei necessário criar todo o ecossistema de autenticação.
  - Acesso à sessão tanto no servidor quanto no cliente.

## Dificuldades

1. Durante o desafio, enfrentei um problema com minha escolha do tRPC.io, pois ele não tinha suporte para upload de arquivos (multipart/form-data). Acabei optando por enviar os arquivos em formato Base64 para não perder as tipagens e não precisar criar uma rota específica para upload (usando a API do Next.js). Isso resultou em requisições um pouco maiores. Em uma situação real e com mais tempo, tentaria implementar o suporte para multipart/form-data no tRPC.io.
2. Optei por trabalhar com os valores das transações como strings para evitar problemas de cálculo com centavos.
3. No último momento, tive um problema ao importar as transações usando o `Promise.all` e decidi substituí-lo por um loop `for...of`. Assim que possível, vou apresentar uma nova solução.

## Documentações

- [Desafio](./CHALLENGE.md) - Desafio proposto
- [API Routes](./API.md) - Documentação da API
- [README](../README.md) - Instruções para iniciar o projeto, desenvolvimento e informações

## Timeline

_O processo de desenvolvimento da aplicação_

### Início

1. Definição das tecnologias e ferramentas.
2. Criação das relações no banco de dados.

### Meio

1. Criação das rotas do tRPC.io.
2. Criação dos componentes.
3. Implementação das telas.
4. Criação de testes para as transações.
5. Implementação da autenticação.

### Final

- Documentação.
- Dockerizar a aplicação.

## Conclusão

Tests: Acredito que apenas os testes das transações tenham ficado adequados, os demais não foram implementados.

Desenvolvimento: Gostei do resultado final, apesar de não ter implementado o upload corretamente sem o uso de Base64. Acredito que as escolhas tecnológicas gerais foram relevantes e produtivas.

Desafio: Gostei da regra de negócio do desafio, mas achei os requisitos um pouco extensos e o prazo bastante corrido para conseguir encaixar tudo.
