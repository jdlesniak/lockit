# Lock-it or Leave-it

This repo contains all development and testing for the Lock-it or Leave-it app. This app contains two primary components 1) a computational statistics approach to estimate the probability of observing a score greater than or equal to the most recent score, and 2) a streamlit app that helps users decide to lock or leave a particular score.

## What is Lock-In Fantasy Basketball?

Lock-in fantasy basketball is a relatively new approach to fantasy basketball where players decide to keep a player's score *after* the game is completed. Most fantasy sports games require players to choose their lineup at the start of a day or week, whereas Lock-in allows players to decide to keep a score after the fact. Sleeper fantasy sports provides an [overview article](https://support.sleeper.com/en/articles/6522833-lock-in-mode-details) for the game.

## How does this app help fantasy managers?

After a game is completed, fantasy managers have to decide if they should lock-in a game, or wait for the next one. Sometimes this is easy - if Jokic puts up 30/20/20, then it's pretty clear you should lock that. Other times, it's a really tough decision. If a player has a good game the first night of the week, should a manager lock-in that game? Fundamentally, this app aims to help fantasy managers make that decision. This app will provide an estimated probability of a player scoring better based on a player's historic performances and the team they are facing next.

## What do users need to do?

Launch the app, select your player, input your league's scoring metrics, and run the simulation. 

## How does the simulation work?

The simulation considers two distributions 1) the player scoring distribution and 2) the opponent defense distribution. In general, better players score more points and better defenses concede fewer points. This app accounts for both of these effects. The player distribution is based solely on a player's previous games. The opponent defense distribution considers a player's position and the league median points conceded. These two distributions are combined in a simulation to estimate the joint distribution of the player and opponent's defense. For example, a guard facing a defense that tends to concede fewer points to guards will have a lower estimate than if they faced a poorer defense.  In essence, the distribution for the defense is a modifier on the player's performance.

Outlier values will occur in both directions.

## What assumptions does the app make?

1) Players will play a full game in their next game. They will not be benched.
2) Players will not be injured in their next game.
3) Past performances are a good estimate of players' produciton in the NBA.
4) Opponents will play their best team. Key defenders will not be out.

## Moving forward

I hope the app helps you in the upcoming fantasy season. Feel free to reach out to me with any questions. My email is on my main GitHub page.
