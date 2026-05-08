This is tip on how to make a snake game and I have a real website where you can play the snake game. 
The three parts of the file
The file is split into three sections that every webpage has:
The <head> is the setup section. It sets the page title ("Snake — SGC"), tells the browser it's in English, and makes it work on mobile screens. Nothing here is visible to the user.
The <style> block inside the head is the CSS — this controls how everything looks. The dark background (#0e0e0e), the green snake color (#1D9E75), the font, button styles, the d-pad grid layout, and the score display all live here.
The <body> is what the user actually sees — the title, score counters, the game canvas (a blank drawing surface), the Start/Pause buttons, and the d-pad arrows.
The <script> block at the bottom is the JavaScript — this is the actual game logic.

How the game logic works
The grid is 18×18 squares. The snake is stored as a list of {x, y} coordinates, one per square it occupies. Every game tick, the snake moves by adding a new head square in the current direction and removing the last tail square — so it appears to slide forward.
When the snake eats the food, the tail is NOT removed that tick, making the snake one square longer. New food is then placed randomly in any square the snake isn't occupying.
The game ends if the new head position goes out of bounds (past the grid edges) or lands on any square already in the snake's body.
The draw() function runs every tick and redraws the entire canvas from scratch — grid lines, each snake segment (with slight transparency fade toward the tail), and the food circle.

How scoring and levels work
Each food eaten gives you level × 10 points. Every 100 points, the level goes up by 1. As the level increases, the game tick interval gets shorter (starts at 160ms, minimum 60ms), making the snake move faster.


Controls
Arrow keys change the nextDir variable (next direction). The current direction only updates at the start of each tick, which prevents you from reversing into yourself by pressing two keys quickly. The d-pad buttons on screen do the exact same thing. Space starts the game or toggles pause.

When you're finished making it:
1. Enable GitHub Pages
Click Settings (top tab in your repo)
Scroll down to Pages in the left sidebar
Under "Branch", select main and keep the folder as / (root)
Click Save
2. Wait ~1 minute
Refresh the Pages settings and a green banner will appear with your live link: 
It will have your username and a website link.
