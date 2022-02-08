# How does it work?

You tell the smart contract what token you want to invest, and which liquidity pool do you want to invest in.

Then, the smart contract takes your tokens and talks to the Solarbeam smart contracts to deposit your token in the pool.

Now, let’s see how it takes your token, and convert it into the LP tokens of the pool you’re investing in.

The smart contract splits the token you want to invest into two halves, and then by interacting with the Solarbeam DEX Router, it converts the halves to the two tokens that are needed for providing liquidity.

Once the smart contract has the two tokens needed to provide liquidity for your chosen pool, it puts them into the pool, and transfers to you, the user, the LP tokens that it receives in return for providing liquidity using your token.
