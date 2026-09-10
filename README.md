# Barbearia Dom Rafa — Site Oficial

Site institucional da Barbearia Dom Rafa (São Miguel do Araguaia — GO),
construído com React, TypeScript, Vite e Tailwind CSS.

> **Sobre as informações do site:** todos os dados exibidos (endereço,
> telefone, horários e avaliação) são os que foram confirmados
> publicamente. Serviços, preços, fotos, redes sociais e história da
> empresa ainda não foram confirmados e aparecem no site como espaços
> preparados para preenchimento futuro — veja `src/data/barbearia.ts`.

## 1. Como instalar

Pré-requisitos: [Node.js](https://nodejs.org) 18 ou superior.

```bash
npm install
```

## 2. Como executar (ambiente de desenvolvimento)

```bash
npm run dev
```

Abra o endereço exibido no terminal (geralmente `http://localhost:5173`).

## 3. Como editar as informações da barbearia

Todas as informações reais ficam centralizadas em:

```
src/data/barbearia.ts
```

Lá você edita, por exemplo:

- nome, endereço e CEP
- telefone e número de WhatsApp
- horários de funcionamento (inclusive o domingo, quando for confirmado)
- textos do hero e da seção "Sobre"
- nota e quantidade de avaliações

Basta alterar o valor e salvar — o site atualiza automaticamente.

## 4. Como trocar as imagens

Como ainda não há fotos oficiais, o site usa placeholders identificados
("Foto da barbearia", "Foto do ambiente", "Foto de corte") nos componentes
`Hero.tsx`, `About.tsx` e `Gallery.tsx`.

Para usar fotos reais:

1. Coloque os arquivos de imagem em `public/images/`.
2. Nos componentes citados acima, troque o bloco do placeholder por uma
   tag `<img>` apontando para `/images/nome-do-arquivo.jpg`, mantendo o
   `alt` descritivo.

## 5. Como adicionar serviços

Edite o array `servicos` em `src/data/barbearia.ts`. Ele começa vazio de
propósito, pois não há uma lista pública confiável de serviços e preços.

Exemplo de item:

```ts
{
  id: "corte",
  nome: "Corte",
  descricao: "Descrição curta do serviço.",
  preco: "A partir de R$ 00",
  duracao: "30 min",
}
```

Assim que houver pelo menos um item no array, a seção "Nossos Serviços"
passa a exibir os cards automaticamente, no lugar da chamada para
"Consultar pelo WhatsApp".

## 6. Como alterar o número de WhatsApp

Edite `contato.whatsappNumero` em `src/data/barbearia.ts`, usando o
formato internacional sem espaços ou símbolos (ex: `5562999859558`).
Todos os botões do site usam esse mesmo valor automaticamente.

## 7. Como gerar o build de produção

```bash
npm run build
```

Os arquivos finais serão gerados na pasta `dist/`.

Para conferir o resultado localmente antes de publicar:

```bash
npm run preview
```

## 8. Como publicar na Vercel

1. Suba este projeto para um repositório no GitHub, GitLab ou Bitbucket.
2. Acesse [vercel.com](https://vercel.com) e clique em **Add New → Project**.
3. Selecione o repositório do site.
4. A Vercel detecta automaticamente o framework Vite. Mantenha:
   - Build Command: `npm run build`
   - Output Directory: `dist`
5. Clique em **Deploy**.

## 9. Como publicar na Netlify

1. Suba o projeto para um repositório Git.
2. Acesse [netlify.com](https://netlify.com) e clique em **Add new site → Import an existing project**.
3. Selecione o repositório.
4. Configure:
   - Build command: `npm run build`
   - Publish directory: `dist`
5. Clique em **Deploy site**.

## Publicação alternativa: Cloudflare Pages

1. Acesse o painel da Cloudflare → **Workers & Pages → Create → Pages**.
2. Conecte o repositório Git.
3. Configure:
   - Build command: `npm run build`
   - Build output directory: `dist`
4. Clique em **Save and Deploy**.

## Estrutura do projeto

```
src/
  components/     Componentes reutilizáveis (Navbar, Hero, Sobre, etc.)
  data/           Dados editáveis da barbearia (barbearia.ts)
  hooks/          Hook de animação ao rolar a página
  App.tsx         Montagem das seções da página
  main.tsx        Ponto de entrada do React
  index.css       Estilos globais e tokens do Tailwind
public/
  robots.txt
  sitemap.xml
  favicon.svg
```

## Tecnologias

- React 18 + TypeScript
- Vite
- Tailwind CSS
- lucide-react (ícones)
