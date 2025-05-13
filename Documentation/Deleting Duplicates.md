# Deleting Duplicate Chess Games from a Database

On my machine, I have two files. The All_white.pgn and All_black.pgn files are the files which contain wins for white and black for my favorite openings. However, because they were extracted from popular free Chess databases, there may be duplicate games.

Therefore, I used these commands to reprocess them and remove extra games with the exact same move sequences. This will save disk space but also time loading them into ChessX.

## Commands to remove dupes

`pgn-extract All_white.pgn -oAll_white-noduplicates.pgn -D`

`pgn-extract All_black.pgn -oAll_black-noduplicates.pgn -D`

After the process was done, I then deleted the original files with the duplicates because they were no longer necessary. If I update the entire database with more sources and openings, I will need to repeat this process though.

More specifically, this database on my machine, while not yet open to the public, is based upon the downloadable sources included in [En Croissant](https://encroissant.org/). All I did was download them, export them to .pgn files, and then sort them according to these openings. Therefore, anyone could create the same thing with this information.

## The Queen's Gambit

`1. d4 d5 2. c4`

## The London System

`1. d4 d5 2. Bf4`

## The Indian Defense

## 1. d4 Nf6


## The French Defense

`1. e4 e6`

## The Sicilian Defense

1. e4 c5

These openings were chosen because of their popularity and my preference. Interestingly, I did not include the Caro Kann because my preference is for the French Defense and I don't want to divide my attention when studying openings any more than I already have.

For more information on using pgn-extract to manage Chess databases, I recommend the official [pgn-extract](https://www.cs.kent.ac.uk/people/staff/djb/pgn-extract/help.html) documentation.

