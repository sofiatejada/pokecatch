## Making a plan
1) Make a drawing of your app. Simple "wireframes"
2) Once you have a drawing, name the HTML elements you'll need to realize your vision
3) For each HTML element ask: Why do I need this?
4) Once we know _why_ we need each element, think about how to implement the "Why" as a "How"
5) Is there some state we need to initialize?
6) Find all the 'events' (user clicks, form submit, etc) in your app. Ask one by one, "What happens when" for each of these events.
7) Think about how to validate each of your steps
8) Consider your data model. What objects will you be using? What are the key/value pairs? What arrays do you need? What needs to live in local storage?
9) Consider what features _depend_ on what other features. Use this dependency logic to figure out what order to complete tasks.



## HTML Setup
1) Button
    - Why? to throw the pokeball to capture the pokemon
        - change the data in localStorage when we CLICK.
        - Rerender the DOM
2) Three or more radio buttons 
    - with 3 images
    - Why? to select which pokemon was CAUGHT
3) 3 images
    - why? to display which pokemon have been encountered



## Events
1) on load
    - call `generateThreePokemon`


2) on click/ on clicking "capture" button
    - Get:
        - current "cart" (pokedex)
        - figure out the ID of the pokemon that the user selected
    - we use the ID and the cart to
        - use find by id to get the selected pokemon from the pokedex
        - we increment the captured property of the selected pokemon by 1
    - call `generateThreePokemon`

## make code DRYer with functions
- `generateThreePokemon`
    - Generate three new random pokemon
        - how do we prevent repeats? (use a `while` loop)
    - Look at the three pokemon and increment their encountered properties by 1
        - if this is the first time we encountered this pokemon, initialize a new item { id: 'pikachu', encountered: 1, captured: 0}
        - otherwise, just increment the `encountered`
    - Rerender the pokemon images
