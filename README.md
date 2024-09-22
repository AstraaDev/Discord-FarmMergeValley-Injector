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
- [x] - [spawnUpgradeCard](https://github.com/AstraaDev/Discord-FarmMergeValley-Injector) - Spawn an upgrade card.
- [x] - [spawnBubbledObject](https://github.com/AstraaDev/Discord-FarmMergeValley-Injector) - Spawn a bubble object (gift, coins, gems, energy, crates, chests, keys, decorations, etc.).
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

From now on, the next steps will depend on each method. Make sure you've followed exactly the steps described in this section before moving on.

## [METHOD 1] : giveInventoryItem
<details>
<summary>Click to expand the information</summary>
  
<details>
<summary>What you can get with this method ?</summary>
  
| Parameter       | Description           |
| :-------------- | :-------------------- |
| `coins`         | Yellow coins          |
| `gems`          | Purple gems           |
| `exp`           | Experience            |
| `levels`        | Levels                |
| `crates`        | Crates with items     |
| `energy`        | Energy for activities |
| `tickets`       | Train tickets         |
| `wheat`         | Wheat                 |
| `egg`           | Egg                   |
| `sunflower`     | Sunflower             |
| `milk`          | Milk                  |
| `sugarcane`     | Sugarcane             |
| `bacon`         | Bacon                 |
| `carrot`        | Carrot                |
| `goatmilk`      | Goat milk             |
| `soybeans`      | Soybeans              |
| `wool`          | Wool                  |
| `corn`          | Corn                  |
| `fur`           | Fur                   |
| `coffeebeans`   | Coffee beans          |
| `tomato`        | Tomato                |
| `avocado`       | Avocado               |
| `truffle`       | Truffle               |
</details>

Make sure you've followed exactly the steps described in the “Common part of each method” section before moving on to this one.

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

## [METHOD 2] : spawnUpgradeCard (found by @frightfully6610)
<details>
<summary>Click to expand the information</summary>
Make sure you've followed exactly the steps described in the “Common part of each method” section before moving on to this one.
  
#### Injection
- In `main.js` file,
- Search the file (by pressing `CTRL`+`F`)
- Write the following command and press `ENTER` :
```js
var _0x4cae7e = _0x162b74;
```
- Set a breakpoint by clicking on the left of the line in the grey area *(see image below)*
<img src="https://cdn.discordapp.com/attachments/1079127307656122501/1287316143928770621/image.png?ex=66f11a15&is=66efc895&hm=020dab4560266d509579a258e74ac3d1fe8c21eaf305d803e3ee08243e736010&" width="300">

- Return to the game and merge items *(the game should stop again)*
- In the **SOURCE** tab, find the loot section at `Local/this/_data/loot` *(see image below)*
<img src="https://cdn.discordapp.com/attachments/1079127307656122501/1287315989834235964/image.png?ex=66f119f1&is=66efc871&hm=82a5a1bcc6e6842ba8643b1f49e037abdc91d0e532cd051a3c18a36bdc956a31&" width="300">

- Replace one of the elements with `“upgrade_card_1”`, `“upgrade_card_2”` or `“upgrade_card_3”` to suit your needs *(see image below)*
<img src="https://cdn.discordapp.com/attachments/1079127307656122501/1287316020448595988/image.png?ex=66f119f8&is=66efc878&hm=97b93f52cf2bc2c658e6306c26b0cd0704a8e80901fb09866c45566729e5aeab&" width="300">

- You can now go back to the `main.js` file in the **SOURCE** tab, then remove the breakpoint *(by clicking on it again)* and click on the `Resume script execution` button again
- All you have to do now is click on the merged item in the game, and the upgrade card should appear.

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
| `reward_crate_daily_bonus`  | True                             | Daily bonus gift |
| `reward_crate_key_bronze`   | True                             | Bonze key        |
| `reward_crate_key_silver`   | True                             | Silver key       |
| `reward_crate_key_gold`     | True                             | Gold key         |
| `reward_crate_bronze`       | True                             | Bronze chest     |
| `reward_crate_silver`       | True                             | Silver chest     |
| `reward_crate_gols`         | True                             | Gold chest       |
| `golden_carrot` | True      | Golden carrot                    |
</details>

Make sure you've followed exactly the steps described in the “Common part of each method” section before moving on to this one.

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
- Any question ? Any malfunction ? Contact me on [here](discord.gg/PKR7nM9j9U).
