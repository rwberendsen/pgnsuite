# pgnsuite

Software that will let you edit PGN (Portable Game Notation, a commonly used format for chess games) by moving pieces around, adding variations, and comments. You can save to PGN. It will be possible to convert the PGN to formats for:

1. reading, e.g., HTML, epub, PDF; It will look beautiful, on screen and on paper, after printing.
2. interactive viewing, i.e., using an interface much like the editor itself.
3. lazy viewing, i.e., it should be possible to auto-play the game(s).

To support these three conversions, some conventions in PGN format are followed in PGN suite:

1. Comments are understood to pertain to the positions at that moment in the PGN, the position achieved just prior to the occurence of a comment in a PGN. This is because in interactive and lazy viewing mode, there is always a single space (or time window, if comments are spoken) for a comment, alongside the board position. The comments needs to be about the current position for it to be readily understood.
2. Comments are interpreted as actions in interactive or lazy viewing mode, in the same way as moves are actions. Since the viewing space for a comment may be limited, editors may opt to add several consecutive PGN comments right after each other. Browsing through the PGN with a play button or viewing the PGN on autoplay will display the comments one after the other, before executing the next move. Also, a comment before the first move of a RAV (recursive annotated variation(!?)) will be shown after a comment on the same position in the parent variation.
3. RAV's can precede the main line in a PGN. This way, the editor can first expose some side lines, before proceeding with the main line. This holds true also for nested RAVs and the main line withing the parent RAV.
4. In addition to the null move, there will be a 'backtrack' move. This way, editors can offer sidelines in a RAV that branch out from the current line a couple of moves back. Sometimes, this improves clarity of presentation. As a side note, another way of achieving the same functionality and more is to allow a FEN string at the beginning of a RAV, so that a variation can start from a wholly different position. Yet another way is to allow nested PGN in a RAV or comment, so that an author can discuss a relevant position from another game.

## The editor interface

The editor interface consists of

1. A board
2. A space for a single comment, with a button that will expand consecutive spaces for comments.
3. A list of variations that branch out of the current position, with, for each variation, buttons to:
  1.   make this variation the main line
  2.   move this variation up / down in the presentation order
  3.   delete this variation
  4.   select the activation as the currently active one (e.g., by clicking on the move itself. This will clear the comment area, without executing the move, to enable the editor to add a comment on the current position that is only relevant to the variation that is currently active. Only executing the next action will execute the move).


## The viewer interface
### Single game mode
### Multi-game mode
