# Post Mortem: *Blind Cartographer*

Seminar: Maps and the City (Summer 2026)
Jaber Rashki Ghaleh No
12452808

Prototype: browser-based video game (`blind-cartographer.html`) (may be played on any web browser)

## 1. Introduction: Project Overview and Game Description

*Blind Cartographer* is a single player adventure/exploration game that was developed specifically for the web. This concept came about through flipping one of the most common mechanics used within games; nearly every game that takes place in a city provides the player with a map, and then adds markers to the map as the player progresses. For my prototype, I decided to do the exact opposite – give the player a complete city, but do not provide them with a map.

The game begins as you take on the role of a mail carrier and arrive at Maya Sol, a port town with an elderly cartographer named Wade Wilson. When he died, he left behind five letters for you to deliver, however, the only requirement was that each letter must be delivered by someone who has never viewed a map of his home town (that is his wish I have nothing to do with it :D). Therefore, there are no mini-maps, compasses, or quest arrows within the game. The letters are written the same way people describe their path to someone else in everyday life; *"walk along side the water on your left, until the lighthouse comes into view above the pier."* A player will walk throughout the world viewing the skyline and have the option of creating his/her own map within a sketchbook in the game. It isn't until all letters have been delivered that the game reveals its first map, the blueprint of Maya Sol, which is presented next to the player's map.

![The arrival: fog hides everything the courier has not walked](figures/shot-title.png)
*Figure 1: The arrival. Only the ferry landing is known and the rest of Maya Sol is covered in fog.*

![Navigating by the skyline](figures/shot-lighthouse.png)
*Figure 2: Playing the first letter. The lighthouse is found, and the silhouette of the Cathedral floats above the fog as a distant cue.*

Technically the prototype is a top down 2D game written in one single HTML file (using Canvas and no actual game engine), with a hand built city that has five different districts, a river, a harbor and five landmarks.

## 2. About the Game: What Kind of Game and Why?

It is a short advanture exploration and navigation game that fits the topic of the seminar and it takes around 15 to 25 minutes to finish and I made it digital on purpose. The central question of the seminar "how orientation is created and whether a map should be shown at all" only becomes a question that can actually be played if the game is able to really hold information back from the player and that's what I tried to achieve as well. I don't think there is any way a board game could possibly do justice to this issue because the board itself is a complete map and to hide it you would need a game master for the players to be able to play. However, in video games it is a completely different world. We have fog of war, we can show landmarks based upon how far away they are from the player, and we can even give the player a private sketchbook. These are all things that a computer can easily create but are virtually impossible to create using cardboard. Therefore, I believe the theory dictated the form of media I would use.

The main design rule I set for myself was that every navigational aid in the game has to be a part of the city and not a part of the interface handet out to the player. Kevin Lynch's five elements of urban legibility (Lynch 1960) became my actual level design checklist for making the game (Figure 3). These are paths (a winding web of streets in the Old Town compared to the ruled grid of the New Quarter), edges (the harbor front and the river, which divide the city and force the player to make decisions at the bridges), districts (five wards, each with its own colors, roofs and street patterns), nodes (the fountain plaza where the market streets come together) and landmarks (the lighthouse, cathedral, clock tower and windmill, which are tall enough to be seen above the fog from far away, similar to the towers in *The Legend of Zelda: Breath of the Wild* (Nintendo 2017)).

![Design scribble of Maya Sol with Lynch's five elements](figures/fig-lynch.svg)
*Figure 3: Design scribble of Maya Sol, planned as an exercise in Lynch's five elements.*

### Story: What do I want to tell?

The story makes a similar argument as the mechanics. Wade Wilson spent all of his adult life creating maps. At some time he lost faith in the map and his final request was for his farewell letters to be delivered by someone who had to discover the city through exploration rather than simply reading it. As each letter was delivered, a brief message would open up linking each recipient to an aspect of the location. For example, the harbormaster is linked to the edge where Wade anchored his first survey; the baker to the plaza as a node ("the centre is wherever the bread is still warm"), the clockmaker to the landmark ("mercy for lost men") and the widow Alvey to the grid of the New Quarter, which is easy to read but has no character and which Wade drew himself and later regrets. And last but not least, the miller is connected to the farewell itself: *"the truest map of a city is worn into the soles of one's shoes."* By the time the player has reached the fifth letter in his journey, he is able to confidently move about a city that was merely fog just an hour earlier; moreover, he had already mentally mapped out that city and then sketched it. This is exactly what validates De Certeau's (1984) dichotomy of "view from above" versus "walker down in the streets" as being essentially the trajectory of the entire game. For the player is the walker the entire time, receiving only the "view from above" at the conclusion of the game.

![The plaza node](figures/shot-plaza.png)
*Figure 4: The plaza as a node. The paths gather at the fountain while the clock tower stands on the horizon of the fog.*

### Game Mechanics: How do I want to tell it?

1. No map and fog of war: Space that has not been walked yet is black, while space that has been walked stays dimly remembered. Knowledge of the city can only be earned by moving through it.
2. Landmark reveal: Tall landmarks break through the fog within a wide radius and are shown with their names, so the skyline takes the place of the compass.
3. Letters as navigation: All goals are described in relation to landmarks, edges and districts and never with coordinates or markers.
4. District feedback: When the player crosses into a new ward its name is shown once. This is Lynch's idea of legibility as a moment of arrival, and it is also the only text based orientation aid in the game.
5. The sketchbook (M key): A blank page, some ink and a small set of map stamps like a tower, a church, a windmill, a bridge and a door. Drawing is optional and never graded, it simply puts on paper the cognitive map that the player is already building in their head anyway. The stamps do not break the rule of not showing a map, because they know nothing about the city. The player decides where each one goes, so the knowledge still has to come from walking, just like the symbols the player places by hand in *Etrian Odyssey* (Atlus 2007). They only make it easier to draw, since drawing with a mouse is slow.
6. The reveal: After the fifth letter the game shows the surveyor's plan next to the player's sketch (Figure 7). The reward is this comparison and not a score.

![The gameplay loop](figures/fig-loop.svg)
*Figure 5: Scribble of the gameplay loop. Read, walk by the skyline, sketch and deliver, with each letter starting further away from what is already known.*

![The sketchbook](figures/shot-sketchbook.png)
*Figure 6: The sketchbook. The only map in the game is the one the player makes.*

![The final reveal](figures/shot-ending.png)
*Figure 7: The ending. The city as the player learned it, next to the city as the surveyors drew it.*

## 3. Formal Note

What went right: The decision to combine all elements of the game into a single HTML file with no engine allowed the game to have a reasonable size and was easy to distribute; anyone can run the game by simply clicking on the file. Using a 48 x 36 ASCII grid to create the city made the process of editing and experimenting much faster than using graphics software. Lynch's list was also helpful in practice, not just as a way of organizing my thoughts about game development. Creating the letters and creating the areas where those letters are found (districts) worked together throughout the entire development process.

What went wrong: Most of the problems were things that the theory had already predicted. My first direction texts used compass directions like "go north east", and they read like a GPS transcript because nobody actually talks like that. Every letter had to be rewritten around edges and landmarks, and one address in the New Quarter even had to be moved on the grid so that "at the third crossing turn south, first door past the corner" was actually true. The title screen at first showed the whole city behind the menu, which means a game about withholding the map was spoiling its own map before the player even pressed a key, so now the fog covers the title screen as well. Finally, editing the ASCII rows by hand silently created ten walkable tiles that were walled in by buildings. A small validation script that checks the row widths and runs a flood fill from the ferry to all five doors caught what my eyes did not.

### Playtesting

The first plan, which was only text directions and fog and nothing else, did not work. In the early runs the first part was fine because the player just follows the waterfront, but once they moved away from the water the fog turned every decision into blind guessing. Being lost was intended, but being blind was not. The solution ended up becoming the defining feature of the game, which is the tall landmarks that break through the fog. With a silhouette on the horizon "lost" turns into "somewhere relative to the tower," and this is exactly what Lynch claims about landmarks. There were two more findings. First, the fog radius had to become bigger until a full street junction fits inside it, because junctions are where the decisions are made. Second, my plan to score the player's sketch against the real map was cut, since grading turned the sketchbook into homework, while a silent side by side comparison invites the player to reflect instead. The New Quarter stayed confusing on purpose (identical blocks and counting corners) as the lowest point of legibility right before the finale. The next step would be playtesting with people outside of my own circle, mainly to see how much players actually draw.

## 4. Conclusion

The prototype I was working on demonstrated to me that orientation can be used as a design tool in itself. When we took the map away, we didn't eliminate wayfinding from the game; rather, we shifted wayfinding into the architecture of the game world. Because we were no longer able to use the map as a guide, our game world (the city) had to be easier to read, not more difficult. One of the greatest lessons I learned during the process of creating this prototype was just how relevant a book written in 1960 about real-world cities can be to designing levels. And the most rewarding part of the entire experience is still the big reveal at the end, when players compare their own shaky drawing to the surveyor's plan, and see every error.

## 5. Bibliography and Inspirations

de Certeau, M. (1984). "Walking in the City." In *The Practice of Everyday Life*. University of California Press.

Gazzard, A. (2013). *Mazes in Videogames: Meaning, Metaphor and Design*. McFarland.

Korzybski, A. (1933). *Science and Sanity* ("the map is not the territory").

Lynch, K. (1960). *The Image of the City*. MIT Press.

Ludography

*Etrian Odyssey* (Atlus 2007), maps drawn by the player

*Firewatch* (Campo Santo 2016), a map without a "you are here"

*Miasmata* (IonFX 2012), navigation by triangulation

*Sea of Thieves* (Rare 2018), charts without markers

*The Legend of Zelda: Breath of the Wild* (Nintendo 2017), towers and landmark navigation

## 6. Contributions

This was a solo project, so I did all of the work myself, from the concept and research to the level design, writing, programming, playtesting and this report.
