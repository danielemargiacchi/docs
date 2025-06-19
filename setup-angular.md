### GET ANGULAR
`npm i -g @angular/cli`
ng --version
ng new nome-app

ng serve

ng g c nomeComponente

ng g service nomeservizio


### GET TAILWIND ANGULAR
1. `npm install tailwindcss @tailwindcss/postcss postcss --force`

2. creare file `.postcssrc.json` nella root

3. nel file

```json
{
  "plugins": {
    "@tailwindcss/postcss": {}
  }
}

```
4. `@import "tailwindcss";` in style.css



### HTTPCLIENT

1. Lo devo iniettare nel service

private httpClient = inject(HttpClient);

2. App.config.ts importo `provideHttpClient()`



