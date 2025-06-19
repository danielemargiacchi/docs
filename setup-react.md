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