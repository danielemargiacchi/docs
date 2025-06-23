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

routing con tonde
routing con quadre
server action
api next 
middleware
dsd



prossimi piani

avere su github, sito, drive e altro: 
- progetto in react sia palestra sia film

- progetto in angular

- files con istruzioni per setuppare react e angular

- file con componenti già fatti in tailwind


