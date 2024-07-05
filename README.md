# one-shot-calculator

There's a saying in some RPGs: the best debuff for your enemies is *dead*.

In edition 3.5 of Dungeons and Dragons, it is possible to make a character that does vastly more damage than you will ever need. Once you can reliably one-shot the kinds of monsters you're likely to face, you can focus the rest of your character's resources on doing other things, like not dying.

Thus, one-shot-calculator. This is a set of Python modules made to calculate your chances of one-shotting monsters of a particular challenge rating. It can print out a histogram of your chances for one-shotting monsters, and has various other functions you can use to calculate various other useful things.

## Install

In order to use these modules, you have to know at least a little bit about programming in Python. It's easier than you might think!

Assuming you're using `conda`, say via [miniconda](https://docs.anaconda.com/miniconda/miniconda-install/), you'll need to install the `pandas` library and the `charset_normalizer` library with

    conda install pandas
    conda install charset_normalizer

Currently, one-shot-calculator isn't set up to be installed with `pip` or the like. You should put the folder one_shot_calculator in your PYTHONPATH with a command like this:

    export PYTHONPATH="folder/this/is/in"

Finally, there is a Jupyter notebook of examples, so if you want to access that you need to be able to use [Jupyter](https://jupyter.org/).

## Usage

The project contains three modules, a jupyter notebook of examples, and a CSV file full of monsters.

The CSV is derived from [an Excel sheet created by Giant in the Playground Forum user ezjakii](https://forums.giantitp.com/showthread.php?402179). It contains nearly all monsters published by Wizards of the Coast for D&D 3.0 and D&D 3.5.

The jupyter notebook, `one_shot_calculator_examples_3e.ipynb`, has a series of examples showing how to use the modules.

`process_csv.py` contains functions for processing the CSV file so it can be used in the other modules.

`discrete_dists.py` contains general functions for manipulating discrete probability distributions with integer outcomes.

`one_shot_calculator_3e.py` contains functions for manipulating probability distributions that describe your chance of one-shotting opponents in D&D 3.5. This includes distributions for damage dealt by attacks and for saving throws. You build a distribution describing your chance of one-shotting opponents, then use the function one_shot_histogram to make a histogram of your chance of one-shotting opponents.

## Future Extensions

That's up to you! Here are some things I could do if people are interested:

- More professionalism: I could set up this to actually work with `pip`, or otherwise do more "real Python package" things.

- More user-friendliness: I could set this up so you don't have to know as much about Python to use it, possibly with some sort of web interface.

- More editions: I could do this for a different edition of D&D, Pathfinder, or some other appropriate RPG. In order to do that I need a CSV full of monsters for that edition. I have one for AD&D 1e and 2e, so I might do that next.

- More examples: I'd love to include a super-high-optimization build in the examples notebook. If someone can walk me through a standard opener for the Mailman or Cindy or the like I can add that as an example.

- More sensitivity: In order for the one-shot histograms to be fully accurate they need to take into account immunities. I could add some code to process_csv to add columns for common types of immunities so you can condition on them in your one-shot distributions.

- More versatility: If you're skeptical about one-shotting things, there is a more "normal" concept, average damage per round (DPR). It would be easy to add a DPR calculator. I could also give you an overall one-shot percentage with a given encoutner table, or even try to make a setup to answer more complicated questions like whether you can kill a monster before it kills you.

- More efficiency: This code is quite slow! It could probably be a lot faster.

- More fun stuff: Want code for specific spells? Anarchic Initiate Chaotic Surges? Other specialized things?


## Acknowledgements

This project would not be possible without ezkajii's laboriously compiled [Monster Compendium](https://forums.giantitp.com/showthread.php?402179).