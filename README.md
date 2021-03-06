# Burger
Burger is a tiny "framework" for automatically extracting data
from the minecraft game for the purpose of writing the protocol
specification, interoperability, and other neat uses.

## The Idea
Burger is made up of *particles*, which can provide and satisfy
simple dependencies, and which can be run all-together or just
a few specifically. Each particle is then aggregated by
`aggregate.py` into the whole and output as a JSON dictionary.

## Usage
The simplest way to use Burger is to pass it the path to either
the client or the server JAR.

    $ python aggregate.py minecraft_server.jar

We can redirect the output from the default `stdout` by passing
`-o <path>`.
    
    $ python aggregate.py minecraft_server.jar -o output.json

We can also run specific particles (assuming you also specify all
the required dependencies) by passing a comma-delimited list.

    $ python aggregate.py minecraft_server.jar -p language,stats

The above example would only extract the language information, as
well as the stats and achievements (both part of `stats`).
