# Decorum Scenario Generation
```query
children:.
```
---

[Decorum](https://boardgamegeek.com/boardgame/344554/decorum) is an amazing game, but initially included only 20 premade 2-player scenarios. They have finally created an 'app' (really just a website) to generate scenarios, but it has a number of problems. The main ones being:

* You need to connect to their servers with an account to use it -- why can't it be fully offline like the Search For series?
* You can only do one scenario a day (I suppose 2 if you pre-save one).
* Often the scenarios end up being trivial, with players having conditions that are obviously pointless and don't further constrain the solution space.

Some others that I'm not too fussed on are:

* No gifts and pets.
* No 4-player.

As a hobby project I'm going to try my own hand at a scenario generator. I can easily fix the first two of the main problems, but the third will require some serious thought. I'm sure the folks developing the current app are also facing this problem, so I don't expect it to be easy.

To start with, I'll stick to what they currently have - 2 players no gifts or pets, but have it offline similar to the Search For series.

## What makes a good scenario?

Here are my current thoughts on what makes a good scenario in Decorum. They are written in very vague terms here, to be clarified in separate pagesThese will likely be updated constantly.

* 4 conditions each.
  * Not 5, not 3. 4.
* Simple conditions
  * The conditions should be simple enough such that someone could get a rough idea of what it is, such that they can try to compromise.
* Limited strict conditions
  * Maximum 1 'strict' condition per player, that specifies exactly what 1 or more spaces on the board must be.
* [[restricting-solution-space|Always restrict solution space]]
  * Every condition restricts the solution space, i.e. if any condition is removed the solution space should increase in size.
* Red Herrings
  * There should be a number of configurations that are far from any solution, but still satisfy 7 of the 8 conditions.
* Good starting setup
  * The starting setup should be close to one of the configurations stated in the previous point, and equally far from all others (including any solutions).
* Clashing conditions
  * Conditions that clash the most should not be held by the same player.
