# SocketBasics
Project 1: SocketBasics CS3700

  For this assignment, my high level approach was to keep track of all of the 0's and 2's that would come up in the message from the 
server, as these would be the most useful to me. When I first approached this problem I knew that I wasn't going to use the 1's to 
my advantage, as it would be a big hurdle for me to try and code them correctly without errors or getting sidetracked, especially 
with repeating letters. Therefore, I implemented this with the thought that a 1 was just as useful as a 0, meaning that the letter 
in that index was not the correct letter for that particular index. Therefore, I kept track of each 0 and 1 at each index and stored 
them in lists. Then, every new word that is brought up is compared to this list, and if there is a letter in that word that has been 
previously marked as a 0 or 1 in that particular spot, then we know that it is not the correct word and we move on. When we found a 2, 
we added it to the list that tracked correct letters, then compared that to every word, until the correct word was found. This is not as 
efficient as other solutions, as we essentially ignored the 1's and look at every word in the list, maybe even more than once, and had 
to store and keep track of many things. However, this implementation never makes an unnecessary guess to the server.
 
  Some challenges I faced along the way was actually building the socket and understanding all of the parameters that had to be implemented. 
JSON strings and syntax was something I had never seen before, but it was easy to learn, as well as the argparser from python. This was my 
first time using python meaningfully and it was very easy to pick up and at a very low level, easy to use. By far the most difficult was 
keeping track of everything that I wanted to and understanding what the server was giving me as a response.
 
  The guessing strategy my client used was primarily based on earlier guesses. The code reads the file in order, starting with the first word. It 
then checked the list that stores each recorded 0 and 1 in each index, and if each letter in that word was not seen in that list, then it did not 
use that word as a guess. If the word in question passed that check, it was then compared to the list that tracked 2's, and if there was a 
previously established two that the word in question did not have, we moved on. This occurred until the correct word was guessed.
 
  I tested my code with various print statements, making sure that all of my indices and lists were in sync with each other. I made sure to check my 
lists against the current word and made sure that my algorithm accurately assigned each letter to its respective list in comparison to the actual 
answer. These were my only means of testing and helped me out quite a bit when trying to produce the secret flag. As for the socket and parameters, 
I just tried out various combinations of running client with different parameters and making sure that it was both working as intended and 
throwing correct error messages.
