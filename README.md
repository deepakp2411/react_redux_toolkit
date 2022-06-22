## Basics of Redux toolki ##

install tools 

<!-- // npm install @redux-toolkit react-redux // -->
# npm install @redux-toolkit react-redux 

- store.js

```js 
import { configureStore } from '@reduxjs/toolkit';
import cartReducer from './features/cart/cartSlice';


export const store = configureStore({
    reducer: {
        cart: cartReducer
    },
})

- cartSlice.js

import { createSlice } from "@reduxjs/toolkit";

const initialState = {
    cartItem: [],
    amount: 0,
    total:0,
    isLoading:true
}

const cartSlice = createSlice({
    name: 'cart',
    initialState
})

console.log(cartSlice)

export default cartSlice.reducer;
```
