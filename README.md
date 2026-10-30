# Meu PC Roda?

Site que mostra o PC necessário para rodar até 5 jogos no gráfico baixo, médio e alto.
As imagens dos jogos vêm do [RAWG](https://rawg.io).

## 1. Criar a chave do RAWG (grátis)

1. Entre em https://rawg.io/apidocs e clique em **Get API Key**.
2. Crie uma conta (ou entre com a sua) e preencha o formulário. Em "site", pode colocar o endereço que o seu site vai ter no GitHub Pages (ex.: `https://SEU-USUARIO.github.io/meu-pc-roda`).
3. Copie a chave que aparecer.

> Plano grátis: até 20.000 pedidos por mês e é obrigatório ter um link para o RAWG na página.
> O site já mostra esse link no rodapé quando a chave está preenchida.

## 2. Colocar a chave no site

Abra o `index.html` num editor (VS Code, por exemplo), procure a linha:

```js
const RAWG_KEY = "";
```

e cole a sua chave entre as aspas:

```js
const RAWG_KEY = "sua-chave-aqui";
```

## 3. Rodar no seu computador (localhost)

Abra o terminal na pasta do projeto e rode **um** destes comandos:

```bash
python -m http.server 8000
# ou, se tiver Node.js instalado:
npx serve .
```

Depois abra no navegador: http://localhost:8000 (ou o endereço que o `npx serve` mostrar).

Outra opção: no VS Code, instale a extensão **Live Server**, clique com o botão direito no `index.html` e escolha **Open with Live Server**.

## 4. Publicar no GitHub Pages

Se ainda não tem, crie uma conta em https://github.com e instale o Git.

```bash
git init
git add index.html README.md
git commit -m "Primeira versão do Meu PC Roda?"
git branch -M main
git remote add origin https://github.com/SEU-USUARIO/meu-pc-roda.git
git push -u origin main
```

(Antes do `git remote`, crie um repositório vazio chamado `meu-pc-roda` no site do GitHub.)

Depois, no GitHub: **Settings → Pages → Branch: main → Save**.
Em um ou dois minutos o site fica no ar em `https://SEU-USUARIO.github.io/meu-pc-roda`.

## Observações

- A chave fica visível no código do site. Para um projeto de hobby isso é comum, mas não use essa chave em nada importante.
- As imagens são buscadas só quando a fileira aparece na tela e ficam guardadas no navegador, então cada visitante gasta poucos pedidos.
- Se um jogo não for encontrado no RAWG, ele continua com a capa colorida e o símbolo.
