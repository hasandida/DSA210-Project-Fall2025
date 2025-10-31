# The Anatomy of Victory: A Win-Prediction Analysis for League of Legends

## 1. Project Description
This project conducts a comprehensive analysis of League of Legends ranked game data to answer a central question: How does in-game factors contribute to chances of victory within a game? Which in-game factors are the most powerful predictors of a win?

Players often debate the value of specific objectives such as `firstBlood` vs. `firstTower`, this project aims to move beyond single statistics. It uses a large dataset to build a machine learning model that weighs the collective importance of multiple factors—including major and basic objectives, team composition ("champion classes"), and economic advantages—to determine the "anatomy" of a winning game.

## 2. Motivation
As a player of the game myself, I have always been interested in the data behind the game's strategies. I have seen multiple videos regarding the League of Legends data and wanted to recreate the same myself, aiming to answer the questions I have always wondered. Specifically, "What truly wins a game" has been a constant debate since I got my hands on this game, I have witnessed these debates during my games and across many forums. However, these arguments are mostly based on personal experiences and opinions of the players themselves. The goal of this project is to apply the data science techniques from DSA 210 to statistically test these theories, quantify the value of objectives, and build a model that reflects the true drivers of victory.

## 3. Explaining Game Concepts & Data
To understand the features used in this analysis, it's helpful to first understand the game itself.

### 3.1 What is League of Legends?
League of Legends is a 5v5 multiplayer online battle arena (MOBA) game. Each member of the team selects a champion (Character of their choice) and gets placed in one of the two teams, Blue and Red, to compete on a map with the goal of destroying the enemy's base. The "base" has a unique name of its own called the **"Nexus."** To achieve this, players collect **gold**, gain **experience points**, and work together to control the map by securing **key objectives**.

### 3.2 Understanding The Data: Key Objectives
The project mainly relies on quantifying the value of in-game objectives. These can be broken into two main categories that the dataset tracks:

#### Major Objectives (Game Changing Level "Bosses")
* **Baron Nashor:** The most powerful neutral monster. Killing it grants a temporary, powerful buff that helps the entire team push into the enemys base to win the game. The dataset tracks these objectives as `firstBaron` and `totalBaronKills`.
* **Dragons:** A series of monsters that grant small but permanent statistical buff to the entire team. Collecting four dragons grants a "Dragon Soul" a very powerful, permanent buff. The dataset tracks these objectives as `firstDragon` and `totalDragonKills`.
* **Rift Herald:** An early-game monster that can be summoned to charge at enemy towers, dealing massive damage and helping gain an early gold lead. The dataset tracks this objective as `firstRiftHerald`.

#### Basic Objectives (Map Control & Milestones)
* **Towers:** Defensive structures that protect each team's base and the way thats leading up to it. Destroying them opens up the map and provides gold. The dataset tracks these objectives as `firstTower` and `totalTowerKills`.
* **Inhibitors:** Key structures found deep in around the base of both teams. Destroying one allows your team to spawn powerful helpers called the "Super Minions" increasing the pressure on the enemy. The dataset tracks this objective as `firstInhibitor`.
* **First Blood:** A statistical milestone for the first kill of the game. Securing it grants bonus gold.

### 3.3 Understanding The Data: Champion Classes
In Leage of Legends there are different classes for each champion. As part of our enrichment step, we will categorize each champion into a class to analyze **team composition.** These classes include:
* **Tank:** A durable, defensive champion that protects their team.
* **Mage:** A champion who deals high magical damage from a distance.
* **Assassin:** A champion designed to quickly eliminate a single high priority target.
* **Marksman:** A ranged champion that deals high, sustained physical damage.
* **Fighter:** A close-range brawler that balances both damage and durability.
