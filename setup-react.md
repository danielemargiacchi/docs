### GET VITE + REACT
`npm create vite@latest nome-progetto`
### GET Tailwind
`npm i tailwindcss @tailwindcss/vite`

```ts
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'
import tailwindcss from '@tailwindcss/vite'

// https://vite.dev/config/
export default defineConfig({
  plugins: [react(),tailwindcss()],
})
```

```css
@import "tailwindcss"
```

### ESTENSIONI
- Atom one dark
- Tailwind css
- Prettier
- Material icon theme
- Javascript auto backtip
- Thunderclient
- Auto rename tag



### Struttura progetto
/components
/context
/hooks
/services
/types


### APP.TSX
```tsx
<BrowserRouter>
    <Routes>
      <Route path="/" element={<Home />} ></Route>
      <Route path="/equipment/:id" element={<Equipment />} ></Route>
      <Route path="/equipment/:id/book" element={<Book />} ></Route>
      <Route path="/bookings" element={<Bookings />} ></Route>
      <Route path="/login/:firstaccess?" element={<Login />} ></Route>
      <Route path="/registration" element={<Registration />} ></Route>
      <Route path="/account/:username" element={<Account/>} ></Route>
      <Route path="/account/:username/bookings" element={<MyBookings/>} ></Route>
      <Route path={"*"} element={<Navigate to="/" />} />
    </Routes>
  </BrowserRouter>
  ```


### ProtectedRoute

```tsx
const ProtectedRoute = () => {
  
}
```


### TAILWIND UI

https://tailwindcss.com/plus/ui-blocks/application-ui/forms/sign-in-forms


 https://www.hyperui.dev/

 https://floatui.com/components



 ### TIPIZZAZIONE EVENTI

 onChange -> React.ChangeEvent<HTMLInputElement> 
 onClick -> React.MouseEvent<HTMLInputElement>


 ### REACT TOASTIFY per notifiche

 npm install --save react-toastify

 


 qua mettiti già i link o il codice di componenti tailwind pronti e responsive








 Gestione del Token di autenticazione
L’API di login ritorna un oggetto contenente un token JWT. Non è necessario decodificarlo, ai fini della prova.

È importante tuttavia utilizzare il token per le chiamate che richiedono autenticazione. È sufficiente includerlo come header con la seguente forma:

Authorization: Bearer <token>
Salvare il token
Seppur non sia un approccio sicuro e adeguato ad un ambiente di produzione, ai fini della prova è sufficiente salvare il token del localstorage del browser con il seguente codice. Qualora si volesse, è accettabile salvare il token nel cookie storage.


localStorage.setItem('authToken', response.token);
e recuperarlo quando necessario con il seguente codice


const token = localStorage.getItem('authToken');

Utilizzare il token nelle chiamate HTTP
Esempio Fetch
const response = await fetch(`${apiBaseUrl}/api/equipment-bookings`, {
  method: 'GET',
  headers: {
    'Content-Type': 'application/json',
    'Authorization': `Bearer ${token}`
  }
});
if (!response.ok) {
  throw new Error('Failed to fetch equipment');
}
return response.json();
Gestione delle Date
Ai fini della prova, si utilizzerà il formato semplificato ISO 8601. Questo formato è facilmente gestibile da JavaScript senza l’utilizzo di librerie.

Il formato ISO 8601
Il formato ISO 8601 consente di combinare data e ora in una singola stringa, in modo da rappresentare un momento specifico nel tempo. La combinazione di data e ora è rappresentata come YYYY-MM-DDThh:mm:ss, dove T è un separatore tra la data e l'ora.

YYYY è l'anno a quattro cifre;

MM è il mese a due cifre (01 per gennaio, 02 per febbraio, ecc.);

DD è il giorno a due cifre (01-31);

hh è l'ora a due cifre (00-23);

mm sono i minuti a due cifre (00-59);

ss sono i secondi a due cifre (00-59).

La stringa ISO 8601 può essere seguita da altre lettere e cifre che, ai fini della prova, possiamo ignorare.

Da stringa ad oggetto Data in JavaScript
Il server non è in grado di ritornare oggetti di tipo Date, ma li converte in stringa ISO 8601. 

Questo esempio dimostra come una stringa di data ISO 8601 possa essere convertita in un oggetto Date.

const isoDateString: string = "2024-01-01T13:00:00Z";
const dateObject: Date = new Date(isoDateString);
console.log(dateObject); // Output: Mon Jan 01 2024 13:00:00 GMT+0000 (UTC)
Da oggetto Data a stringa in JavaScript
Prima di inviare una data al server, è necessario trasformarla in stringa.

Questo esempio dimostra come un oggetto JavaScript di tipo Date possa essere convertito in stringa ISO 8601.

const dateObject: Date = new Date();
const isoDateString: string = dateObject.toISOString();
console.log(isoDateString); // Output: 2023-11-10T08:37:00.123Z
