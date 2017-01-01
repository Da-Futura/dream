IF YOU CAN DREAM IT YOU CAN BUILD IT

Installation

1) Clone recipies into working folder

folder called, DreamRecipies.

this folder contains a set of .drcp files which have the format:

TOML might be a good idea as the format for the .drcp (https://github.com/toml-lang/toml)

make_cake.drcp

%= preheat oven

%= mix ingredients

%= bake for 30mins

%= cool

2) Run dream init inside the root folder.

This looks at all the files in the DreamRecipies and makes an associative array

Something like:

{ 'make_cake' => [preheat_oven, mix ingredients, bake, cool], 'shower' => [remove clothes, turn on water, wet, lather, turn off, dry]  }

3) To make a cake, we then run

   dream start make_cake

   which returns, STEP 1/4: Preheat Oven

4) After you've completed the step,

   dream next

   which returns, STEP 2/4: Mix ingredients

   (You can't have more than on active recipie)

5) After the final step, /dream next/ displays

   "You've successfully completed make_cake", here are a list of all avaliable recipies/last recipies.

6) At any time 

dream status

Displays the current step

GIT INTEGRATION 

1. dream git next

Alias of git commit -am"<completed step>”

Displays next step

2) dream git next -m"ice cream”

Alias of git commit -am"<completed step>” + "ice cream”

3) dream git rewind (rollback?)

Rollbacks to previous commit, rollbacks dream status and displays updated status.

The idea is that you not only use external recipies, but that you make your own recipie *every* time you start to build a new feature

so that you can reproduce it later, and because it makes tyou carefully consider what you're actually doing, and imposes some sort of planning.

