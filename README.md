# Neat Grid Lab Session 2/6/2019

# Talk Notes:
Neat Grid documentation: https://neat.bourbon.io/docs/latest/

Good Tutorial:
https://robots.thoughtbot.com/the-release-of-neat-2-0-a-lightweight-and-flexible-sass-grid

## What is a Grid System?
* Web learned about grid systems from print.  Check out  https://99designs.com/blog/tips/history-of-the-grid-part-1/ for a history of grid systems.  Generally, grids align a visual space into columns and rows and then defines what portion of that space a module should inhabit.
* CSS wasn't originally created by visual designers and it has lacked fairly basic layout tools.  Grid system frameworks have been with us for quite a while to help fill in the gaps.  Flexbox and CSS grids were meant to be released together. Someday when IE11 is gone we will have a lot more layout flexibility and I don't think we will need external grid frameworks.
* Grid systems started to become popular when we moved away from fixed width designs and table based layouts.  Once responsive was born they became even more popular.  Many places have adopted larger UI frameworks like Bootstrap primarily to get a grid-system.
* There are many kinds of grid-systems  (half-gutter grids, simple-gutter grids, percentage grids...) .  If you've used a grid system before and Neat feels 'odd' it is probably because it is a different type of grid-system.  https://robots.thoughtbot.com/building-the-future-of-floated-css-grids talks about some different types of grid systems and the thought process that went into Neat Grid.
## Neat Grid
Neat is a Push-left-grid.  The library author lists these as the factors he had in mind when developing Neat:
* Low selector specificity and no nth-child selectors
* Gutters that can be defined in relative values like 2% as well as fixed values like 2rem or 16px
* A simple and understandable codebase with a limited set of well focused features
* Generate as little code as possible, maintaining flexibility, while not over restricting objects
* Coexist seamlessly with flexbox objects and containers
* Be compatible with both Lib Sass and Ruby Sass
## Neat 3.0 vs Neat 1.0:
* Neat 1 was a push-right system (It was based around adding margins to the right of column to create a gutter.).  Neat 3 is push-left.
* Neat 3 has about a third of the mixins Neat 1 had and overall tries to accomplish only 1 thing.
* Mixins are named more clearly.  Every mixin starts with the word grid. I think this a good thing.  We ended up using neat 1 in a lot of places that were not grid-related partially because the mixins had really general names.  This made upgrading tough.
* 3.0 is a small and streamlined system.
    * Neat 3.0 is a Sass only library.  It contains just a few mixins that can be employed to generate a grid.
    * Each mixin takes two arguments.  One relevant to the mixin and then an optional grid map.

 Behind the scenes, Neat looks at the element it is positioning, the size of it's container, and the definition of the grid that it is working with.  It calculates the width of the element, floats it left, and adds a margin on the left to create the gutter.

## What are some advantages of a Grid System?   Do we need it?
 Anything that you can do with a grid system you can also do by hand.  However:
* It saves time
* It can make things easier for the next engineer to look at the code. If I see a mixin called grid-column(3) I understand what is happening.  A float, a left-margin, and a calculated width declaration in the midst of 6 other styles may well get lost.
* It works well across our supported browsers.
## When should we use Neat grid?
* Any time you have a block level element that you want to break into columns. (particularly if the columns need to behave differently in a responsive setting)
