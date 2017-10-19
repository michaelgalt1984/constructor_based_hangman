# constructor_based_hangman

Normally I don't really fill this out, which I should probably get in the habit of doing.  Since I sincerely doubt that I am going to be able to get this to function... I might as well explain what I think needs to happen and how it should be done.  

I think that there needs to be either: an array with a large selection of words OR an API request which will pull a random word to be used for the game.  

If an array of words is used, it would need to have a math.random function to randomly select from the words, so that you won't end up with the same words in the same order every time that you play it. 

After the word was selected, it would have to be stored in a variable which is tied to a constructor.  So, the constructor would be Random_Word, and it would be new Random_Word.  That would be so that the word could have a bunch of different functions applied to it, and set keys and values.

Inside that constructor, I think that there would need to be a function which splits up the word string into each of its individual letters.  These letters would then need to get pushed into a new constructor for letters.  So, there would be Random_Word_Letters constructor, and the random word would get its letters pushed to new Random_Word_Letters.  

As an example, if the random word was "leather", that would get stored in new Random_Word. Inside that would be a function that would split each letter and push it into new Random_Word_Letters.  So, that would be an array ["l", "e", "a", "t", "h", "e", "r"].  

There would need to be some sort of function in new Random_Word_Letters to display those letters as underscores on load.  This would then need to trigger (.then) inquirer to prompt for user guesses via the console.  

There would need to be a counter set with every new Random_Word_Letters which would indicate how many guesses remained and decrement with incorrect guesses (letters not in the new Random_Word_Letters array).  I would set the number of guesses to be 7 (head, body, 2 legs, 2 arms, and sad face), with the counter being set to 6.  If the counter decrements to 0, the user loses.  

Once the user begins entering their guesses, there would need to be a function which captures those entries and stores them in a variable.  A for loop would then need to iterate through the Random_Word_Letters array to see if the user entry(ies) matched any of the letters displayed as underscores.  If a match(s) were found, then a function would need to run which would reveal that letter(s).

Additionally, for every match found, that value would need to be set to false so that it couldn't be matched again, and a reverse counter equal to the number of letters in the word would need to increment or decrement to indicate the number of letters matched.  If the number of letters matched equaled the number of letters in the word, then the player would win.  Alternately, this could possibly be accomplished by a function which iterates throught the displayed word, and if it doesn't encounter any underscores, the player wins.

These would have to be be if else conditions where the if the letters were all displayed, it would trigger a new prompt recognizing the success of the player and then it would ask them if they wanted to play again.  If the player exhausted all their guesses, then they would be told they lost and asked if they wanted to play again (different prompt).  Either way, a reset function would have to be run whether they won or lost, reseting both the counters (for letters displayed and guesses remaining), drawing a new random word, and then repeating all of the earlier processes.