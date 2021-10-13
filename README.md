# INFR3110-L4E2

My approach to this Exercise, using my Assignment 1/Midterm as a base, was implementing a singleton pattern to save the Death Count value, that is to say, the amount of times the player has died in the level. For the Observer patter, again in the instance of a death, an oof sound will be played.

The DeathCount script is identical to the Persistant Manager Script as shown in the lab. It is a singleton pattern that keeps track of a value within the instance.
The Manager script is similar to the Scene Manager script as shown in the lab. As it does not need the functionality of switching scenes, that code with discarded, keeping only the creation of a text variable, and storing the instance value within the string. That line of code was put in the update rather than start, as I found that while within start, the value would stay at zero even though the DeathCount was increasing. Hence it was placed in the update function so the value would reflect appropriately upon increase.
As for the increase itself, it can be found in the Move script under Death in the OnCollisionEnter function.

For the Audio Source, the DAudioPlayer script is identical to the ClickAudioPlayer as shown in the lab, with the exception of calling for "Move.died" in place of "ClickScore.clicked", as I stored the died event Action within the Move script. With that said, as the lab had "clicked?.Invoke()" within the ClickScore script in order to increase the score on a mouse click, I instead placed my "died?.Invoke()" within the Move script again under Death in the OnCollisionEnter function, as this sound will play upon a players death.
