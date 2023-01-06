# Tutorial

## Operation
### Check Token Pools
* You can check the details of the token pools with `Polkadot.js/app` as follows:  
    <p id="figure.1" align="center">Figure.1 Check the details on-chain</p>  

    ![img](./resource/check-token-pools.png)  

    * `oammsModule` is the pallet name.
    * Choose the interface `tokenPool` and click `＋`.
    * You can see the details of created swap pools.

### Swap
#### On-chain Interface
* Go to `Developers` -> `Extrinsics`, Choose `oammsModule` and interface `swap`:  
    ![img](./resource/swap.png)  

    * `dIn` and `dOut` is the token to be swapped in and out, and note that the `t_amount` has the precision `0.0001`, for example, if we input `12345678`, the real value is `1234.5678`.
    * `virtualOut` is the virtual amount of the current output token, it has a precision `0.0001`.  

* Everythin will be calculated off-chain first. 

#### Off-Chain Calculation Tools
* Locate your terminal just in this repo.
* Installation
    ```sh
    npm install
    ```
* Check the operations.
    ```sh
    node index.mjs --help
    ```
    
    * Operation `swap` is used to calculate the details of a swap, the result of which is just the input parameters of the interface `swap` on-chain.
    * Operation `price` is used to calculate the price of related tokens, that is to calculate $\frac{dy}{dx}$.  
* Make a swap calculation.
    * Get the values of `b`, `C` and `the amount of the input token` from on-chain, which is detailed in [Figure.1](#figure.1).
    * An example of a off-chain swap calculation script is as follows:  
    ```sh
    # -s <Δamount>,<amount>,<b>,<C>,<input token name><output token name><pool name>
    # @Δamount is the input amount of token x
    # @amount is the amount of token x got from on-chain(Figure.1)
    # @b is got from on-chain(Figure.1)
    # @C is got from on-chain(Figure.1)
    # @input token name
    # @output token name
    # @pool name
    node index.mjs -s 100,10000,282842712,200000000,x,y,kitty
    ```

