# ChasteBase

## Chastity's Chess Database

# Who This Book is For

After I published my first Chess book, [Chastity's Chess Chapters](https://chastitychesschallenge.com/chastitys-chess-chapters/), I was going to write a book on the Queen's Gambit. However, I realized the huge amount of research that would be required in order to teach the best moves in games starting with that opening. Therefore, I decided, why don't I document the entire process while writing a book about how I keep my database of Chess games organized. In my first book, I mentioned a lot of software. Two of them are for managing databases and can really help you learn where you went right or wrong in a game. This book is for those people who not only want to play Chess but to learn by analyzing a database of their own games!

# What is ChasteBase?

ChasteBase is a new idea for a Chess Database invented by Chastity White Rose. It started because she invented a Tetris game called [Chaste Tris](https://store.steampowered.com/app/1986120/Chaste_Tris/) Chaste is the root word of Chastity. In the context of the Tetris game as well as ChasteBase, it means it is the pure form of something without extra, unnecessary, or corrupt things added. Just as Chastity wanted to make a Tetris game that is free from the greed of the Tetris company, she also saw that many Chess players are using ChessBase, which is the world's largest collection of software and databases that the top professional Chess players use when preparing for their over the board games.

ChasteBase is not a replacement for ChessBase, but it is a helpful resource that Chastity uses to remind herself of what she learned and also to teach students. There are very few pictures in this book page because it would take forever designing pictures for infinite Chess positions. It would also make the printing cost of the paperback higher. Instead, I recommend using the [Lichess Analysis Board](https://lichess.org/analysis) to follow along with the Chess notation. For example, if you copy paste ["1.d4 d5 2.c4 dxc4 3.Nf3 Nf6 4.e4 Nxe4 5.Bxc4 Bg4 6.Ne5 Bxd1 7.Bxf7#"](https://lichess.org/C7xSjA8g) into the PGN field of that page and click import, you will then be able to step through each move of a 13 move checkmate. Chess notation is well defined and supported by more Chess software than you can possibly imagine!

Therefore, ChasteBase is this book, but it is also a philosophy and method I will teach you so that you can make your own Chess Database and name it after yourself if you feel like it. I will teach you not only how to download your own lichess database, using my own as an example case, but I will also tell you how to make the most of it.

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

As mentioned before, games ending in Checkmate are more reliable than games ending by other means. However, there is something else to consider. Who are you playing against and how good of a player are they? This can be difficult to determine or control. Therefore, contrary to my previous advice in my last book of playing against humans, I recommend playing against Stockfish level 4 on lichess. I have good reasons for this.

- Stockfish levels less than 4 are too easy.
- Higher levels, especially 8 are near impossible.
- The computer will never resign.
- You can take back mistakes.

Therefore, I will make use of these commands to show how you can extract games with a certain opponent. Which in this case, is the "lichess AI level 4".

Commands for extracting wins against the lichess AI which is technically Fairy Stockfish.

`pgn-extract -Twchastitywhiterose -Tb"lichess AI level 4" -Tr1-0 lichess_chastitywhiterose.pgn -ochastitywhiterose_white_wins_lichess.pgn --checkmate`

`pgn-extract -Tw"lichess AI level 4" -Tbchastitywhiterose -Tr0-1 lichess_chastitywhiterose.pgn -ochastitywhiterose_black_wins_lichess.pgn --checkmate`

# White vs Stockfish

I recommend starting with d4 whenever you are playing as white.

![d4.png](https://chastitychesschallenge.com/wp-content/uploads/2025/03/d4.png)

You don't know what white will do, but I will cover some rules I think you might want to follow that will get you through the opening.

# Black vs Stockfish

When you are playing as black, it is very common for the computer to start with either d4 or d5 as the first move. Therefore, this book will cover cases where black starts with either of these moves.

## French Defense vs Stockfish

If white plays e4, you could go with many different openings, however, the French Defense is the one I choose to teach in this book.

This is the start of the French Defense. White has moved king's pawn to e4 and we are moving our king's pawn only one square instead of the usual two.

![e4-e6.png](https://chastitychesschallenge.com/wp-content/uploads/2025/03/e4-e6.png)

I know it looks weird and uncomfortable to move a pawn only one square when it could have moved two, but the reason for this will become clear very soon.

Almost all the time, white will move their queen's pawn two squares and in this case you will copy them.

![e4-e6-d4-d5.png](https://chastitychesschallenge.com/wp-content/uploads/2025/03/e4-e6-d4-d5.png)

In this position, white has the option of capturing the d5 black pawn. If they take it, it is called the exchange variation of the French Defense. White will capture the pawn but then we capture it right back. Then the board will look like this.

![e4-e6-d4-d5-exd5-exd5.png](https://chastitychesschallenge.com/wp-content/uploads/2025/03/e4-e6-d4-d5-exd5-exd5.png)

As the black player, this is precisely what you wanted to happen because now the path is open for you to move either of your bishops or your queen out if you need to.

The other alternative is when white does not take the pawn and instead advances it to e5.

![e4-e6-d4-d5-e5.png](https://chastitychesschallenge.com/wp-content/uploads/2025/03/e4-e6-d4-d5-e5.png)

This is called the advanced variation of the French Defense, not because it is advanced in the sense of complicated but because the white pawn has advanced instead of capturing. When this happens, the best thing to do is to move a pawn to c5 and offer the "black queen's gambit" and hope that white takes it so you can capture back with the bishop. From that point the game continues like normal and it follows much of the same logic as I use when I play the Queen's Gambit.

If the next move by white is moving a knight to d2, they have blocked the bishop from attacking the dark squares. This means that the black knight can safely move to h6 with the idea of going to f5 and attacking white's d4 pawn. At this point, they will try to defend that pawn with a knight or a pawn. You then want to move a pawn to c5 and also threaten it.

## 1. e4 e6 2. d4 d5 3. Nd2 Nh6 4. Ngf3 c5

 If they take the pawn with their pawn, capture it back with the bishop.