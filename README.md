<p align="center">
  <img src="https://venturebeat.com/wp-content/uploads/2022/11/press_release_banner.jpg" width="800">
</p>

<h1 align="center">[Discord] - FarmMergeValley Injector</h1>

<p align="left">
  FMV Injector lets you set up various methods for modifying content in the Farm Merge Valley discord game. This project follows on from @wooslow's repositorie on the same subject. Perform these steps preferably from a Google Chrome browser. There is currently no guarantee that these methods will work on other browsers.
</p>


## Disclaimer

|FMV Injector was made for Educational purposes|
|-------------------------------------------------|
This project was created only for good purposes and personal use.
By using this Tool, you agree that you hold responsibility and accountability of any consequences caused by your actions.

## Features

- [x] - [giveInventoryItem](https://github.com/AstraaDev/Discord-FarmMergeValley-Injector) - Obtain any object in unlimited quantities.
- [ ] - [removeHeavyObj](https://github.com/AstraaDev/Discord-FarmMergeValley-Injector) - Remove heavy objects (trees and stones) from the map.
- [ ] - [spawnCollectable](https://github.com/AstraaDev/Discord-FarmMergeValley-Injector) - Spawn a collectible item (coins, gems, energy, etc.).
- [ ] - [spawnUpgradeCard](https://github.com/AstraaDev/Discord-FarmMergeValley-Injector) - Spawn an upgrade card.
- [ ] - [spawnBubbledObject](https://github.com/AstraaDev/Discord-FarmMergeValley-Injector) - Spawn a bubble object (gift, coins, gems, energy, crates, etc.).
- [ ] - [setLuckyMergeChance](https://github.com/AstraaDev/Discord-FarmMergeValley-Injector) - Set the lucky merge chance of objects.

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
- Click on the `Resume script execution` button *(see image below)*
<img src="">
- In the **SOURCE** tab, find the file named main.js located at `top/1187.discordsays.com/1187.discordsays.com/main.1401.js` *(see image below)*
<img src="">

From now on, the next steps will depend on each method. Make sure you've followed exactly the steps described in this section before moving on.

## [METHOD 1] : giveInventoryItem
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

#### Injection
- In `main.js` file,
- Search the file (by pressing `CTRL`+`F`)
- Write the following command and press `ENTER` :
```js
this['servi' + 'ces']['mapGr' + 'id']['setCo' + 'ntent']
```
- There will normally be 4 results. Navigate to the third result and set a breakpoint by clicking on the left of the line in the grey area *(see image below)*
<img src="">

- Return to the game and place a crate *(the game should stop again)*
- In the **CONSOLE** tab, write the following command and press `ENTER` :
```js
worldServices = this.services
```
- You can now go back to the `main.js` file in the **SOURCE** tab, then remove the breakpoint *(by clicking on it again)* and click on the `Resume script execution` button again *(see image below)*
<img src="">

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
You're all set! Now all you have to do is enter the following command in the **CONSOLE** tab and press `ENTER` :
```js
giveInventoryItem("item", amount);
```
Don't forget to replace the `item` argument with one of the parameters in the `What you can get with this method?` table of this method, and `amount` with the amount you want.

## [METHOD 2] : removeHeavyObj
Comming soon.

## [METHOD 3] : spawnCollectable
Comming soon.

## [METHOD 4] : spawnUpgradeCard
Comming soon.

## [METHOD 5] : spawnBubbledObject
<details>
<summary>What you can get with this method ?</summary>
  
| Parameter       | Is reward | Description           |
| :-------------- | :-------- | :-------------------- |
| `coin_1`        | True      | 1 coin        |
| `coin_2`        | True      | 3 coins       |
| `coin_3`        | True      | 9 coins       |
| `coin_4`        | True      | 27 coins      |
| `coin_5`        | True      | 81 coins      |
| `coin_6`        | True      | 243 coins     |
| `coin_7`        | True      | 729 coins     |
| `coin_8`        | True      | 2187 coins    |
| `gem_1`         | True      | 1 gems        |
| `gem_2`         | True      | 3 gems        |
| `gem_3`         | True      | 9 gems        |
| `gem_4`         | True      | 27 gems       |
| `gem_5`         | True      | 81 gems       |
| `gem_6`         | True      | 233 gems      |
| `crate_1`       | True      | 20 crates     |
| `crate_2`       | True      | 60 crates     |
| `energy_1`      | True      | 10 energy     |
| `energy_2`      | True      | 30 energy     |
| `energy_3`      | True      | 90 energy     |
| `energy_4`      | True      | 270 energy    |
| `key_1`         | False     | Bronze key    |
| `key_2`         | False     | Silver key    |
| `key_3`         | False     | Gold key      |
| `chest_1`       | False     | Bronze chest  |
| `chest_1`       | False     | Silver Chest  |
| `chest_1`       | False     | Gold chest    |
| `golden_carrot` | True      | Golden carrot |
| `golden_carrot_key`         | False         | Golden carrot key |
| `golden_carrot_chest`       | False         | Golden carrot chest |
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
<img src="">

- Return to the game and place a crate *(the game should stop again)*
- In the **CONSOLE** tab, write the following command and press `ENTER` :
```js
worldServices = this.services
```
- You can now go back to the `main.js` file in the **SOURCE** tab, then remove the breakpoint *(by clicking on it again)* and click on the `Resume script execution` button again *(see image below)*
<img src="">

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
You're all set! Now all you have to do is enter the following command in the **CONSOLE** tab and press `ENTER` :
```js
spawnBubbledObject("item");
```
Don't forget to replace the `item` argument with one of the parameters in the `What you can get with this method?` table of this method.

## [METHOD 6] : setLuckyMergeChance
Comming soon.

### Additional Informations
Discord :
- Any question ? Any malfunction ? Contact me on `None`.
