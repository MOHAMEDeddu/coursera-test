#!/bin/bash

function guessing_game {
    files=$(ls -1 | wc -l)
    guess=-1

    while [[ $guess -ne $files ]]; do
        read -p "How many files are in the current directory? Enter your guess: " guess

        if [[ $guess -lt $files ]]; then
            echo "Your guess was too low. Try again."
        elif [[ $guess -gt $files ]]; then
            echo "Your guess was too high. Try again."
        fi
    done

    echo "Congratulations! Your guess is correct. There are $files files in the current directory."
}

guessing_game
README.md: guessinggame.sh
	echo "# Guessing Game" > README.md
	echo "Date and Time: $$(date)" >> README.md
	echo "Number of lines in guessinggame.sh: $$(wc -l < guessinggame.sh)" >> README.md

.PHONY: clean
clean:
	rm README.md
 
# Guessing Game
Date and Time: <current date and time>
Number of lines in guessinggame.sh: <number of lines>
