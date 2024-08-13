# minecraft-functions
Here's my functions for command block functions for farms without ridiculous amount of grinding which is not possible for me.

## Installation

Clone the repository to your worlds datapack folder (windows example: `C:\Users\YourUserName\AppData\Roaming\.minecraft\saves\YourWorldName\datapacks\minecraft-functions`)

## Usage example

Wither skeleton farm function
```
/function comblock-farm:wither-skeleton
```
Or in command block
```
function comblock-farm:wither-skeleton
```
## Functions
### Load
Just a simple "hello world" type of a indicator that datapack has been loaded.

### Wither skeleton farm
Kills following mobs within 128 blocks:
- Piglins
- Piglin brutes
- Zombified piglins
- Ghasts

Removes following items (drops from killed mobs)
- Rotten flesh
- Gold Nuggets
- Gold ingots
- Golden armors(helmet, chest, pants, boots)
- Crossbows
- Warped fungus sticks
- Ghast tears

## Information
`Data` folder contains your **definitions** and **functions**.  
`Minecraft/tags/function` contains all of your definition files  
Any other folders in data contains "_namespace_" folders which contains function code

### Folder structure
```
minecraft-functions
├── data
│   ├── comblock-farm
│   │   └── function
│   │       └── wither-skeleton.mcfunction
│   ├── minecraft
│   │   └── tags
│   │       └── function
│   │           ├── load.json
│   │           └── wither-skeleton.json
│   └── namespace
│       └── function
│           └── load.mcfunction
├── LICENSE
├── pack.mcmeta
└── README.md
```
## Add a new function

1. Add a new folder to `Data` folder. for example: `hello-world`. 
2. Add a folder called `function` to `hello-world`
3. Add your function commands to a new file for example `hi.mcfunction`

Reload your datapack by running `/reload` in-game (or start your world)
Use the function by running `/function hello-world:hi` 

## Explanations for commands

### Explanation of the kill mobs components:

1. **`/kill`**: This is the Minecraft command used to instantly remove or "kill" entities. It can be applied to any entity in the game, including mobs, items, or even players.

2. **`@e[...]`**: This is a target selector that specifies which entities the command should affect. The `@e` selector targets all entities in the world, but you can apply filters to narrow it down to specific types, distances, etc.

3. **`type=minecraft:zombified_piglin`**: The `type` filter narrows the selection to only entities of the specified type. This filter ensures that only Zombified Piglins are targeted by the command.

4. **`distance=..128`**: `distance=..128` means that only mobs specified in `pype` within a 128-block radius from the command's execution point will be affected. The `..` syntax indicates a range from 0 to 128 blocks. Without this, the command would target all entities of the specified type regardless of distance.

#### **What the Command Does**

- When executed, this command kills all Zombified Piglins within a 128-block radius from the point where the command is issued (whether from a player or a command block).
- This can be useful in scenarios where you want to clear out a specific area of a particular mob, such as when you're trying to manage mob spawns in the Nether or a farm.
### Explanation of the kill item components:

- **`/kill`**: This command removes entities from the world.
  
- **`@e[...]`**: Targets entities based on specified criteria.
  
- **`type=item`**: Filters the target to entities that are dropped items.
  
- **`distance=..128`**: Targets entities within a radius of 128 blocks from the command execution point.
  
- **`nbt={Item:{id:"minecraft:rotten_flesh"}}`**: Further filters the items to only those whose item ID is "minecraft:rotten_flesh".
  

## Useful links

[Pack formats - Minecraft wiki](https://minecraft.fandom.com/wiki/Pack_format)