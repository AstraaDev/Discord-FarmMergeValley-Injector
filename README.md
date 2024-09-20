<p align="center">
  <img src="https://venturebeat.com/wp-content/uploads/2022/11/press_release_banner.jpg" width="800">
</p>

<h1 align="center">[Discord] - FarmMergeValley Injector</h1>

<p align="left">
  FMV Injector lets you set up various methods for modifying content in the Farm Merge Valley discord game. This project follows on from @wooslow's repositorie on the same subject. Perform these steps preferably from a Google Chrome browser. There is currently no guarantee that these methods will work on other browsers.
</p>


## Disclaimer

|FMV Injector was made for Educational purposes   |
|-------------------------------------------------|
This project was created only for good purposes and personal use.
By using this Tool, you agree that you hold responsibility and accountability of any consequences caused by your actions.

## Features

- [x] - [giveInventoryItem](https://github.com/AstraaDev/Discord-FarmMergeValley-Injector) - Obtain any object in unlimited quantities.
- [ ] - [spawnUpgradeCard](https://github.com/AstraaDev/Discord-FarmMergeValley-Injector) - Spawn an upgrade card.
- [x] - [spawnBubbledObject](https://github.com/AstraaDev/Discord-FarmMergeValley-Injector) - Spawn a bubble object (gift, coins, gems, energy, crates, etc.).
- [x] - [removeAllObstacles](https://github.com/AstraaDev/Discord-FarmMergeValley-Injector) - remove all obstacles (trees and stones) from the map.
- [x] - [setLuckyMergeChance](https://github.com/AstraaDev/Discord-FarmMergeValley-Injector) - Set the lucky merge chance of objects.

## Common part of each method
Each of the methods described here works in the same way. The game needs to be “paused” at the right moment to access certain elements that are normally blocked. The differences between these methods are the information to be retrieved, the precise moment to break the script, the action to be taken to break the script, etc...
Even if these parts change depending on the method, the beginning remains the same.

#### Setup
- Launch of Farm Merge Valley on discord *(and never close it again until the end)*
- Open the browser console (by pressing `CTRL`+`SHIFT`+`I` on Windows/Linux or `Cmd`+`Opt`+`I` on MacOS)
- Your game should now be "paused". In the **CONSOLE** tab, write the following command and press `ENTER` :
```js
Function.prototype.constructor = function() {};
```
- Click on the `Resume script execution` button *(see image below) (it's the blue button)*
<img src="https://cdn.discordapp.com/attachments/1079127307656122501/1286722534905086073/image.png?ex=66eef13e&is=66ed9fbe&hm=111689ea87b329f10dd1b216424b619a0a4f6943c0304568bc4d2f2548d4aadb&" width="200">

- In the **SOURCE** tab, find the file named main.js located at `top/1187.discordsays.com/1187.discordsays.com/main.1401.js` *(see image below)*
<img src="https://cdn.discordapp.com/attachments/1079127307656122501/1286723565562888222/image.png?ex=66eef234&is=66eda0b4&hm=821455387248d83f3c38ef95ba0b67a3aae0b7cfc00a6f335565334b5bb6451f&" width="300">

#### Injection
- In `main.js` file,
- Search the file (by pressing `CTRL`+`F`)
- Write the following command and press `ENTER` :
```js
this['servi' + 'ces']['mapGr' + 'id']['setCo' + 'ntent']
```
- There will normally be 4 results. Navigate to the third result and set a breakpoint by clicking on the left of the line in the grey area *(see image below)*
<img src="https://cdn.discordapp.com/attachments/1079127307656122501/1286724033706070066/image.png?ex=66eef2a3&is=66eda123&hm=53c9afe455aa09cfdb2cae701d04c97741549e7128ec99f1218f64eca415dc31&" width="400">

- Return to the game and place a crate *(the game should stop again)*
- In the **CONSOLE** tab, write the following command and press `ENTER` :
```js
worldServices = this.services
```
- You can now go back to the `main.js` file in the **SOURCE** tab, then remove the breakpoint *(by clicking on it again)* and click on the `Resume script execution` button again

From now on, the next steps will depend on each method. Make sure you've followed exactly the steps described in this section before moving on.

## [METHOD 1] : giveInventoryItem
<details>
<summary>Click to expand the information</summary>
  
<details>
<summary>What you can get with this method ?</summary>
  
| Parameter       | Is reward | Description           |
| :-------------- | :-------- | :-------------------- |
| `coins`         | True      | Yellow coins          |
| `gems`          | True      | Purple gems           |
| `exp`           | True      | Experience            |
| `levels`        | True      | Levels                |
| `crates`        | True      | Crates with items     |
| `energy`        | True      | Energy for activities |
| `tickets`       | True      | Train tickets         |
| `wheat`         | True      | Wheat                 |
| `egg`           | True      | Egg                   |
| `sunflower`     | True      | Sunflower             |
| `milk`          | True      | Milk                  |
| `sugarcane`     | True      | Sugarcane             |
| `bacon`         | True      | Bacon                 |
| `carrot`        | True      | Carrot                |
| `goatmilk`      | True      | Goat milk             |
| `soybeans`      | True      | Soybeans              |
| `wool`          | True      | Wool                  |
| `corn`          | True      | Corn                  |
| `fur`           | True      | Fur                   |
| `coffeebeans`   | True      | Coffee beans          |
| `tomato`        | True      | Tomato                |
| `avocado`       | True      | Avocado               |
| `truffle`       | True      | Truffle               |
</details>

Make sure you've followed exactly the steps described in the “Common part of each method” section before moving on to this one.

#### Setting up the function
- In the **CONSOLE** tab, write the following command and press `ENTER` :
```js
let giveInventoryItem = (target, amount) => {
    return worldServices.rewardService.giveInventoryReward({
        "reward": {"key": target, "amount": amount},
        "parent": worldServices.mapGridView._view.parent.parent.parent
    });
}
```

#### Use injection
You're all set! Now all you have to do is enter the following command in the **CONSOLE** tab and press `ENTER` :
```js
giveInventoryItem("item", amount);
```
Don't forget to replace the `item` argument with one of the parameters in the `What you can get with this method?` table of this method, and `amount` with the amount you want.
</details>

## [METHOD 2] : spawnUpgradeCard
<details>
<summary>Click to expand the information</summary>
Comming soon.
</details>

## [METHOD 3] : spawnBubbledObject
<details>
<summary>Click to expand the information</summary>
  
<details>
<summary>What you can get with this method ?</summary>
  
| Parameter       | Is reward | Description                      |
| :-------------- | :-------- | :------------------------------- |
| `coin_1`        | True      | Coins (up to coin_8)             |
| `gem_1`         | True      | Gems (up to gem_6)               |
| `crate_1`       | True      | Crates (up to crate_2)           |
| `energy_1`      | True      | Energy (up to energy_4)          |
| `wood_1`        | True      | Wood (up to wood_8)              |
| `stone_1`       | True      | Stone (up to stone_8)            |
| `tool_1`        | True      | Tool (up to tool_10)             |
| `flower_1`      | True      | Flower (up to flower_10)         |
| `greenhouse_1`  | True      | Greenhouse (up to greenhouse_12) |
| `golden_carrot` | True      | Golden carrot                    |
</details>

Make sure you've followed exactly the steps described in the “Common part of each method” section before moving on to this one.

#### Setting up the function
- In the **CONSOLE** tab, write the following command and press `ENTER` :
```js
let spawnBubbledObject = (target) => {
    return worldServices.rewardService.giveObjectReward({
      "rewards": [target],
      "container": worldServices.mapGridView._view.parent.parent.parent,
      "animationEndEvent": null,
      "bubblePosition": {"x": 0, "y": -200}
    });
}
```

#### Use injection
You're all set! Now all you have to do is enter the following command in the **CONSOLE** tab and press `ENTER` :
```js
spawnBubbledObject("item");
```
Don't forget to replace the `item` argument with one of the parameters in the `What you can get with this method?` table of this method.
</details>

## [METHOD 4] : removeAllObstacles
<details>
<summary>Click to expand the information</summary>
Make sure you've followed exactly the steps described in the “Common part of each method” section before moving on to this one.

#### Use injection
- In the **CONSOLE** tab, write the following command and press `ENTER` :
```js
worldServices.world.getAllGameObjects().filter(x=>x.hasBehavior("hitpoints") && !x.hasBehavior("shovelable") && !x.hasBehavior("movable")).forEach(x=>worldServices.world.removeGameObject(x))
```
</details>

## [METHOD 5] : setLuckyMergeChance
<details>
<summary>Click to expand the information</summary>
Make sure you've followed exactly the steps described in the “Common part of each method” section before moving on to this one.

#### Setting up the function
- In the **CONSOLE** tab, write the following command and press `ENTER` :
```js
let setLuckyMergeChance = (percentage) => worldServices.mapGridView._view.parent.parent.parent._systems.find(x => x._luckyMergeChance)._luckyMergeChance = percentage;
```

#### Use injection
You're all set! Now all you have to do is enter the following command in the **CONSOLE** tab and press `ENTER` :
```js
setLuckyMergeChance(percentage);
```
Don't forget to replace the `percentage` argument with a number between 0 and 100. Setting `100` as an argument means that the lucky merge will always take place, and setting `0` as an argument means that the lucky merge will never take place (the default value is 5).
</details>

## Additional Informations
Discord :
- Any question ? Any malfunction ? Contact me on `None`.
