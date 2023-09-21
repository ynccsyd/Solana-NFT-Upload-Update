# Solana NFT Upload/Update
* # $\textcolor{green}{Getting\ Started}$

* ## :dart: $\textcolor{green}{In\ this\ project\ you\ have\ to\ know:}$ 
<div>
     <img src="https://raw.githubusercontent.com/devicons/devicon/1119b9f84c0290e0f0b38982099a2bd027a48bf1/icons/typescript/typescript-original.svg" title="typescript" **alt="typescript" width="40" height="40"/> 
</div>

---
* ## :memo: $\textcolor{green}{ First,\ run\ the\ development\ server:}$ 
 
```bash
npx create-solana-client [name] --initialize-keypair
cd [name]
npm install @solana/web3.js
npm install @metaplex-foundation/js fs
npm start
```
* ## :black_nib:  $\textcolor{green}{ And\ describe\ your\ token\ metada:}$ 
  
```ruby
const tokenName = "Phoenix "
const description = "Before everything"
const symbol = "BP"
const sellerFeeBasisPoints = 100
const imageFile = "phoenix1.jpg"
```

* ##  $\textcolor{green}{And\ you'r\ on\ blockchain}$ :heart_eyes:
As you run your code,  go to the Solana Explorer URL in your terminal.
<p align="center">
    <img src="https://user-images.githubusercontent.com/109158340/205504257-e4af3ec5-d3c8-4861-9e51-ab3afe555f85.png" >
    
---
* ##  $\textcolor{green}{Here's\ your\ first\ NFT}$ :fire:

<p align="center">
  <img src="https://user-images.githubusercontent.com/109158340/205504389-a365947e-cca2-43d9-ad56-f0acd77722ea.png" >
  
 --- 
* ##  $\textcolor{green}{You\ can\ get\ every\ details\ of\ Nft}$
<p align="center">
  <img src="https://user-images.githubusercontent.com/109158340/205504436-33ac0b8a-8ae1-43aa-b520-42f24ab29560.png" >
  
---
* # :boom: $\textcolor{green}{Now\ it's\ time\ to\ update}$

* ##  $\textcolor{green}{Update\ the\ imageFile\ constant\ to\ the\ name\ of\ the\ final\ image\ of\ your\ NFT. }$
* ##  $\textcolor{green}{Add\ this\ anywhere\ outside\ main: }$
```ruby
async function updateNft(
  metaplex: Metaplex,
  uri: string,
  mintAddress: PublicKey
) {
  // get "NftWithToken" type from mint address
  const nft = await metaplex.nfts().findByMint({ mintAddress })

  // omit any fields to keep unchanged
  await metaplex
    .nfts()
    .update({
      nftOrSft: nft,
      name: tokenName,
      symbol: symbol,
      uri: uri,
      sellerFeeBasisPoints: sellerFeeBasisPoints,
    })

  console.log(
    `Token Mint: https://explorer.solana.com/address/${nft.address.toString()}?cluster=devnet`
  )
}
```
* ##  $\textcolor{green}{Add\ the\ updateNFT\ helper\ function }$
```ruby
 // await createNft(metaplex, uri)

  // You can get this from the Solana Explorer URL 
  const mintAddress = new PublicKey("Write here your PbblicKey")
  await updateNft(metaplex, uri, mintAddress)

```
* # :trophy: $\textcolor{brown}{Congratulations\ your\ Nft\ has\ been\ updated}$

<p align="center">
  <img src="https://user-images.githubusercontent.com/109158340/205505587-31b08132-2b3b-4a3f-b404-3d7159647646.png" >
