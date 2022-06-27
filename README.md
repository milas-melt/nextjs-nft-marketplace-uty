1. home page
    1. show recently listed NFTs
        1. if you own the NFT, you can update the listing
        2. if not, you can buy the listing
2. sell page
    1. you can list your NFT on the marketplace
    2. Withdraw proceeds

# Restarting local dev chain steps and warnings
1.  kill all terminals from `hardhat-nft-marketplace-uty` and `nextjs-nft-marketplace-uty ` (or ctrl + c).
2. Go to `moralis.io/servers` then `server details` then `Devchain Proxy Server` and hit `Disconnected` button.
3. On `hardhat-nft-marketplace-uty` : start node with `yarn hardhat node` on its own terminal.
4. On `nextjs-nft-marketplace-uty` : sync servers : `yarn moralis:sync`.
5. Go to `moralis.io/servers` then `server details` then `Devchain Proxy Server` and hit `Connected` button to refresh + make sure it stays connected + hit `reset local chain`.
6. Restart frontend: `yarn dev`. 
WARNINIG: Notice that even after all these steps when you go on moralis db you will notice that the database is still populated. However, these entries are from blockchains that no longer exist. As a result, we do the below step...
7. on moralis DB: on `ActiveItems`, select all then click edit then click `delete all rows` in this class.
8. do it for `ItemListed` too and for the other relevant classes.
9. refresh the page and make sure that all the relevant classes are zeroed out.
10. to verify it's working, on `hardhat-nft-marketplace-uty` terminal, execute `yarn hardhat run scripts/mint-and-list-item.js --network localhost`
11. On moralis server, refresh and make sure that you got the right classes populated with the right number.


# Other notices
when updating moralise code, don't worget to push the code by executing the following script: `yarn moralis:cloud` on `nextjs-nft-marketplace-uty` terminal. (should get `Changes Uploaded Correctly`)































This is a [Next.js](https://nextjs.org/) project bootstrapped with [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app).

## Getting Started

First, run the development server:

```bash
npm run dev
# or
yarn dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `pages/index.js`. The page auto-updates as you edit the file.

[API routes](https://nextjs.org/docs/api-routes/introduction) can be accessed on [http://localhost:3000/api/hello](http://localhost:3000/api/hello). This endpoint can be edited in `pages/api/hello.js`.

The `pages/api` directory is mapped to `/api/*`. Files in this directory are treated as [API routes](https://nextjs.org/docs/api-routes/introduction) instead of React pages.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js/) - your feedback and contributions are welcome!

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/deployment) for more details.
