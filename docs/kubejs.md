# KubeJS
KubeJS is a Minecarft mod that allows modders and modpack devloppers to create their own blocks, items, crafting recipes, potion effects and much more.
Consider checking the [official website](https://kubejs.com).

## Installation
To install KubeJS, download it on Curseforge, Modrinth or the official KubeJS website, and drag the *.jar* file in your Minecraft instance *mods* folder.
Dependencies :
- Rhino
- Architectury API
- Fabric API (only for Fabric)

We recommand installing *ProbeJS* too. ProbeJS is an add-on for KubeJS which makes working with code and files way easier. Download ProbeJS, lauch the game and enter a world. Then type `/probejs dump` in the chat. Wait a few seconds and there you have it. Once done, continue on with the guide.

# Guide

We will be writing JavaScript scripts inside 3 folders. Here is an example on how to acces it :  
Vanilla : `.minecraft\mods\kubejs\`  
Using curseforge : `curseforge\minecraft\Instances\YourModpack\kubejs\`
>[!TIP]
>With curseforge, you can click on the three dots ` ⁝ ` next to ` Play ` on your modpack profile, than click on "open folder". This will bring you directly to your modpack's folder.

We are looking for the following folders :
- `client_scripts`
- `server_scripts`
- `startup_scripts`

## Creating a new block
In `startup_scripts`:

```js
StartupEvents.registry('block', event => {
     event.create('block_name')
     .displayName('Block')
})
```
- `event.create('')` creates a block with an ID of its entry
- `displayName('')` is responsible for the item name seen in-game

## Creating a new item
In `startup_scripts`:

```js
StartupEvents.registry('block', event => {
    event.create('item_name')
    .displayName('Item')
})
```
>[!NOTE]
>The new block/item automatically chooses the texture with the same name as the block/item in the corresponding folder. For example, if you want your block to have the texture of a netherite block, place the texture file in the `assets\kubejs\textures\block` folder.



## Creating a new recipe
In `server_scripts`:

### Shapeless recipe
```js
ServerEvents.recipes(event =>{
    event.shapeless('output', 'input')
})
```
>[!NOTE]
>Entries such as `'input'` can be arrays. For example : `event.shapeless(minecraft:blackstone, [minecraft:cobblestone, minecraft:black_dye])`

### Shaped recipe
```js
ServerEvents.recipes(event =>{
     event.shaped('output', [
          ' A ',
          'ABA',
          '   '
     ],{
          A: 'minecraft:leather',
          B: 'minecraft:iron'
     })
})
```
