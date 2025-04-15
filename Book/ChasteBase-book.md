# ChasteBase

## Chastity's Chess Database

# Who This Book is For

After I published my first Chess book, [Chastity's Chess Chapters](https://chastitychesschallenge.com/chastitys-chess-chapters/), I was going to write a book on the Queen's Gambit. However, I realized the huge amount of research that would be required in order to teach the best moves in games starting with that opening. Therefore, I decided, why don't I document the entire process while writing a book about how I keep my database of Chess games organized. In my first book, I mentioned a lot of software. Two of them are for managing databases and can really help you learn where you went right or wrong in a game. This book is for those people who not only want to play Chess but to learn by analyzing a database of their own games!

# What is ChasteBase?

ChasteBase is a new idea for a Chess Database invented by Chastity White Rose. It started because she invented a Tetris game called [Chaste Tris](https://store.steampowered.com/app/1986120/Chaste_Tris/) Chaste is the root word of Chastity. In the context of the Tetris game as well as ChasteBase, it means it is the pure form of something without extra, unnecessary, or corrupt things added. Just as Chastity wanted to make a Tetris game that is free from the greed of the Tetris company, she also saw that many Chess players are using ChessBase, which is the world's largest collection of software and databases that the top professional Chess players use when preparing for their over the board games.

ChasteBase is not a replacement for ChessBase, but it is a helpful resource that Chastity uses to remind herself of what she learned and also to teach students. There are very few pictures in this book page because it would take forever designing pictures for infinite Chess positions. It would also make the printing cost of the paperback higher. Instead, I recommend using the [Lichess Analysis Board](https://lichess.org/analysis) to follow along with the Chess notation. For example, if you copy paste ["1.d4 d5 2.c4 dxc4 3.Nf3 Nf6 4.e4 Nxe4 5.Bxc4 Bg4 6.Ne5 Bxd1 7.Bxf7#"](https://lichess.org/C7xSjA8g) into the PGN field of that page and click import, you will then be able to step through each move of a 13 move checkmate. Chess notation is well defined and supported by more Chess software than you can possibly imagine!

Also, anyone serious about Chess will probably want to play Chess online on lichess.org anyway. You can play with [chastitywhiterose](https://lichess.org/@/chastitywhiterose) almost anytime by sending a challenge!

# Obtaining a Chess Database

The best way to obtain a free database is to play games on lichess.org and then go to your profile and find the export options.

![chastitywhiterose-lichess-profile-dropdown.png](https://chastitychesschallenge.wordpress.com/wp-content/uploads/2025/04/chastitywhiterose-lichess-profile-dropdown.png)

Then you will want to make sure you have selected only the standard variant and the time controls you want to be included. Chess database programs almost never support anything other than standard Chess. This is unfortunate because I would love to see how a Crazyhouse database would look. Maybe software for other variants will be invented or exists that I don't know about. In the meantime, stick with standard.

![chastitywhiterose-export-games.png](https://chastitychesschallenge.com/wp-content/uploads/2025/04/chastitywhiterose-export-games.png)

When you have downloaded a database to the filename of your choice, you will want to install a program such as [ChessX](https://chessx.sourceforge.io/) which can help you play the games out on a graphical chessboard. There are many other applications like [Scid vs. PC](https://scidvspc.sourceforge.net/) or various products sold by the Chessbase company. However, I don't recommend paying for a program unless you are a professional Chess player who wins prize money to justify the cost of it. Therefore, I have chosen only to recommend free and open-source tools.


# Using a Chess Database

## pgn-extract

Once you have a database of your own games, or perhaps games of other people, you may want to filter them by certain criteria. The program [pgn-extract](https://www.cs.kent.ac.uk/people/staff/djb/pgn-extract/help.html) is exactly what you can do this with. It is a command line only program. You will have to read the documentation to know all of its options but here are some commands that I commonly use to keep track of my best wins.

These commands use the file "lichess_chastitywhiterose.pgn" which I downloaded directly from lichess.org. There is a built in export feature that allows you to select games of different time controls and/or variants and decide which ones to export to pgn file. pgn-extract can only handle standard chess games but it can sort them extremely fast. For example:

This first command takes all of the games where chastitywhiterose was the white player and won the game by checkmate.

`pgn-extract -Twchastitywhiterose -Tr1-0 lichess_chastitywhiterose.pgn -ochastitywhiterose_white_wins_lichess.pgn --checkmate`

The second does the reverse and finds every time that chastitywhiterose played as black and then black won the game by checkmate.

`pgn-extract -Tbchastitywhiterose -Tr0-1 lichess_chastitywhiterose.pgn -ochastitywhiterose_black_wins_lichess.pgn --checkmate`

I have said for years that only games ending in a checkmate are reliable information. If your opponent timed out because they fell asleep or got distracted, that doesn't really feel like a win, does it? It also doesn't tell you whether your moves you played were good or bad. That is why I always filter my games to end in checkmate.

Unfortunately, because many of my opponents resign as soon as I capture their queen, there are many games that are missed by this filter. Be a good sport and finish your live chess games with your opponent. It is the polite thing to do. Also, you may still have a chance to win or at least draw the game by a stalemate.

## ChessX

The best currently available free and open source Chess database management program is [ChessX](https://chessx.sourceforge.io/). It allows you to open a pgn file and actually play through all the games with a graphical user interface. This is the best way to analyze your games and see visually where you made the mistakes. I have not fully explored everything that the program can do but I read that it also has filtering capabilities similar to what you could have done with pgn-extract which I previously mentioned.

# The Quality of Games


Commands for extracting wins against the lichess AI which is technically Fairy Stockfish.
In this example, I am extracting wins against the level 4 AI.

`pgn-extract -Twchastitywhiterose -Tb"lichess AI level 4" -Tr1-0 lichess_chastitywhiterose.pgn -ochastitywhiterose_white_wins_lichess.pgn --checkmate`

`pgn-extract -Tw"lichess AI level 4" -Tbchastitywhiterose -Tr0-1 lichess_chastitywhiterose.pgn -ochastitywhiterose_black_wins_lichess.pgn --checkmate`