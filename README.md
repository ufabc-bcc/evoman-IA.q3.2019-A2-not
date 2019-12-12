# EvoMan

Organized by Fabricio Olivetti de Franca (folivetti@ufabc.edu.br), Karine Miras (karine.smiras@gmail.com), Denis Fantinato, Patricia Vargas, A.E. Eiben.

## Introduction

EvoMan [1] is a framework for testing competitive game-playing agents in a number of distinct challenges such as:

- Learning how to win a match against a single enemy
- Generalizing the agent to win the matches against the entire set of enemies
- Coevolving both the agent and the enemies to create intelligent enemies with increasing difficulties.

This framework is inspired on the boss levels of the game MegaMan II [2] in which a robot with a simple arm cannon must beat more sophisticated robots (8 in total) with different powers.

## Challenge

In this challenge, the contestants should train their agent on a set of four enemies (defined by the contestant) and evaluate how general is their learned strategy when fighting against the whole set of enemies.

Since each enemy behavior greatly differs from each other, the player should learn how to identify and react to general patterns like avoiding being shot or shoot at the direction of the enemy. For different learning algorithms this has already proven to be a challenge [1,3].

The agent will have a total of $20$ sensors, with $16$ of them corresponding for horizontal and vertical distance to $8$ different bullets (maximum allowed), $2$ to the horizontal and vertical distance to the enemy, and $2$ describing the direction the player and the enemy is facing.

The framework is freely available at https://github.com/karinemiras/evoman_framework and it’s compatible with Python 3.6 and 3.7 (Python 3.8 is not compatible at the moment). There is also an extensive documentation at https://github.com/karinemiras/evoman_framework/blob/master/evoman1.0-doc.pdf.

##  Evaluation

Both the agent and the enemies start the game with 100 energy points. Everytime one player gets hit, it loses one point. Whoever reaches 0 points loses the match.

The final performance of the agent after the end of a match is calculated by the energy gain, as a maximization problem, calculated by the difference between the player and the enemy energy:

$$Gain = ep - ee$$

where ee, ep are the final amount of energy of the enemy and the player, respectively, so we want to maximize the gain.

The main goal of this competition is that a given agent perform equally good for every boss. So, each contestant agent will be tested against all of the enemies, and they will be ranked by the harmonic mean of the performance over the different bosses. 

## Deadline

All submissions should be sent until March 31st, 23:59 (GMT).

## Installing the framework

The initial code, manual and every other resources needed are available at this Github repository:

- follow the installation instructions in the file *evoman1.0-doc.pdf*
- run the demo script demonstração *controller_specialist_demo.py* to test if the framework is working
- play the game using your own keyboard to understand the difficulties of the problem. Use the script *human_demo.py*.

The agent should be trained using the *Individual Evolution* mode with the goal of beating each one of the four adversaries chosen for training.

## Submission

The contestants should submit their code via GitHub Classroom, following the instructions at the [https://classroom.github.com/g/YEQprX27](https://classroom.github.com/g/YEQprX27), additionally, it should also be submitted a paper following the same template as used on WCCI describing your solution to the problem.

The paper should report the chosen bosses for training, the values of the average *player energy* (ep) and *enemy energy* (ee) obtained by your best agent for each one of the eight bosses and the average duration of the match  (this will be used in case of a drawn).

## Notes

It is not allowed to:

- change the *core* of the framework (*evoman* folder).
- The parameter `level` should be set to $2$ and `contacthurt` to `player` (both are the default values).


## References

[1] de Araújo, Karine da Silva Miras, and Fabrício Olivetti de França. "An electronic-game framework for evaluating coevolutionary algorithms." arXiv preprint arXiv:1604.00644 (2016).
[2]  M. MEGA, “Produced by capcom, distributed by capcom, 1987,” System: NES.
[3] de Araujo, Karine da Silva Miras, and Fabrício Olivetti de Franca. "Evolving a generalized strategy for an action-platformer video game framework." 2016 IEEE Congress on Evolutionary Computation (CEC). IEEE, 2016.
