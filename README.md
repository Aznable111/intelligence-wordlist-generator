# Intelligence Wordlist Generator

## About
WLGEN pretends to be something between crunch and CUPP. Permutations are based on a list of keywords and then you can add different options (connectors,abbreviations, reverse, replacements ...) to extend the final wordlist.

Modified to accept a wordlist as input with a -w

## Usage
You can simply execute the following command to serve the purpose immediately. The default `config.cfg` will be the source of configuration and the `output.txt` will be created after the execution as a result. 
`$ python iwlgen.py`

You can also set your custom configuration filename instead of using `config.cfg` and set the output filename as well.
`$ python iwlgen.py -c <config_filename> -o <output_filename>`
For example
`$ python iwlgen.py -c myconfig.cfg -o myoutput.cfg`

When using the parameters please use `-c` and `-o` parameters altogether, otherwise the script will use the default setting.

### Configuration
The following settings can be configured through `config.cfg`:
- `keywords` (list): Main list to permutate.
- `connectors` (list): For each permutation we will use this list to concatenate keywords.
- `num_tails` (list): For each permutation we will add (at the end of the string) a number (`10`) or a range of numbers (`20-40`)
- `tails` (list): We will add an extra string (i.e. `@hotmail.com`)

### Options
This options will **extend** our wordlist generated with `[Params]` section.
- `string_replacements` (bool): If true we will replace strings defined in `[Replacements]` section for each element of `keywords` param. i.e. `hello` -> `h3ll0`
- `abbreviation` (bool): If true we will use elements abbreviations of `keywords` param. i.e. `hello` -> `h`
- `reverse` (bool): If true we will reverse elements of `keywords`. i.e. `hello` -> `olleh`
- `to_lower` (bool): If true we will duplicate all elements and use `.lower()` in all duplicated elements.
- `min_length` and `max_length` (num): We filter result list by length element.

### Files
- `output`: Output file name.

## TODO
- Needs status timer, and chunking for better usage of large input files
- Threading
