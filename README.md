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
# redux-dev tool
- install chrome extension

## Access store value 

- create components/Navbar.js
- this is for creating cart item

```js
import { AiOutlineShoppingCart } from "react-icons/ai";
import { useSelector } from "react-redux";

const Navbar = () => {
  const amount = useSelector((store) => store.cart.amount)
   
  return (
    <nav>
      <div className="nav-center">
        <h3>redux toolkit</h3>
        <div className="nav-container">
          <AiOutlineShoppingCart />
          <div className="amount-container">
            <p className="total-amount">{amount}</p>
          </div>
        </div>
      </div>
    </nav>
  );
};

export default Navbar;

