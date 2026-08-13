# 🎉 Tetoka

O Tetoka é uma plataforma criada para ajudar jovens que acabaram de completar 18 anos a navegarem pelos direitos, deveres e responsabilidades da vida adulta. Ela centraliza conteúdos práticos sobre documentos, educação, carreira, empreendedorismo e cidadania, tornando essa transição mais simples e acessível.

## Características principais

- **Guia de documentos:** orientações sobre documentos essenciais, como RG, CPF e CNH.
- **Educação e carreira:** conteúdos sobre ENEM, ensino superior e oportunidades em concursos públicos.
- **Empreendedorismo:** informações e passos iniciais para quem deseja abrir um negócio.
- **Direitos e responsabilidades:** conteúdos para conhecer direitos e obrigações a partir dos 18 anos.
- **Feed personalizado:** recomendação de conteúdos de acordo com os interesses selecionados pela pessoa usuária.
- **Acompanhamento de progresso:** marcação das etapas concluídas em cada conteúdo e visualização do progresso.
- **Autenticação de usuários:** cadastro, login, logout e sessão para uma experiência individualizada.
- **Interface responsiva:** experiência adaptada para computadores, celulares e tablets.

## Tecnologias utilizadas

- [TypeScript](https://www.typescriptlang.org/): linguagem utilizada no front-end e no back-end, com tipagem estática.
- [Next.js 14](https://nextjs.org/): framework React utilizado na construção da interface web.
- [React 18](https://react.dev/): biblioteca para criação de interfaces de usuário.
- [Tailwind CSS](https://tailwindcss.com/): framework CSS utilitário para estilização responsiva.
- [Node.js](https://nodejs.org/): ambiente de execução do servidor.
- [Express](https://expressjs.com/pt-br/): framework para a API e rotas do back-end.
- [MongoDB](https://www.mongodb.com/pt-br): banco de dados NoSQL para usuários e conteúdos da plataforma.
- [Passport.js](https://www.passportjs.org/): autenticação local baseada em sessão.

## Arquitetura do projeto

O projeto é separado entre o cliente e o servidor. O Next.js disponibiliza a interface e encaminha requisições iniciadas em `/api` para o Express. O servidor centraliza regras de autenticação, usuários, posts e progresso, persistindo os dados no MongoDB.

```text
Navegador
   │
   ▼
client/ (Next.js + React + Tailwind CSS)
   │  /api/*
   ▼
server/ (Express + Passport.js)
   │
   ▼
MongoDB
```

## Rotas da API

As rotas da API são disponibilizadas sob `/api`:

- `/api/auth`: autenticação, encerramento de sessão e verificação de login;
- `/api/users`: cadastro, dados de usuário, interesses e progresso dos conteúdos;
- `/api/posts`: consulta, filtragem e gerenciamento dos conteúdos da plataforma.

Operações administrativas de usuários e posts requerem o token configurado em `ADMIN_TOKEN`.
