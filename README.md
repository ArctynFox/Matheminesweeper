# Matheminesweeper
Developed in a pair for a university course focusing on proficiency in Wolfram's Mathematica, this game attempts to recreate the classic Minesweeper in the aforementioned language, with the twist of using a tesselated pattern of dodecagons, hexagons, and squares.

Play by running the matheminesweeper.nb file via Wolfram Player: https://www.wolfram.com/player/

# Screenshots
![image](https://github.com/user-attachments/assets/6419e5cb-cf9b-435e-abf4-172332887f1a)
![image](https://github.com/user-attachments/assets/7e43ab7f-0c8a-4f58-8235-7f99b2c4ac09)
![image](https://github.com/user-attachments/assets/f2bcb1c4-3733-4a51-9626-40790cafeb60)
> Game boards of any size are possible, however Mathematica seems to limit the number of calculations that can be performed in a windowed graphic, so boards larger than a size of 7 (radial) will only run in the notebook view itself (and take a long time to process each action).

# Interesting Developmental Point About This Project
We had to determine a convenient data structure to use for grids that would work no matter the size of the board. In the end, we decided to use a polar tile index system, as shown in the following image:

![image](https://github.com/user-attachments/assets/4cbb62e8-5ed7-4bbb-a63f-2e930dd19c09)

We start with the center tile, then move out one layer and number them clockwise, and then move out another layer and repeat. Each of these tile indices would have three flags, those being whether it is a bomb, whether it has been flagged, and if it has been opened.

This also posed an interesting problem in which, because Mathematica is not a render engine, we needed to determine manually the correlation between what location in the graphic was clicked and what tile was actually clicked. 
