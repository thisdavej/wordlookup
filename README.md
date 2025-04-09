# WordLookup

This repo serves as a companion resource for the [Packaging Python Command-Line Apps the Modern Way with uv](https://thisdavej.com/packaging-python-command-line-apps-the-modern-way-with-uv) tutorial found on [thisdavej.com](https://thisdavej.com).

## Intro

WordLookup is a command-line tool to fetch and display definitions for a given word using the [Dictionary API](https://dictionaryapi.dev/).

## Usage

Run the CLI tool with the word you want to look up as an argument:

```sh
wordlookup <word>
```

### Example

To look up the word "sojourn":

```sh
wordlookup sojourn
```

Output:

```text
Definitions for 'sojourn':

noun:
- A short stay somewhere.
- A temporary residence.

verb:
- To reside somewhere temporarily, especially as a guest or lodger.
```

## Notes

- The tool attempts to format the output to fit your terminal width.
- If the terminal width cannot be determined, it defaults to 80 characters.
- Ensure you have an active internet connection as the tool fetches data from an external API.

## Building from Source

### Prerequisites

- Python 3.13
- [uv](https://github.com/astral-sh/uv) package manager

### Installation

1. Clone the repository:

```sh
git clone https://github.com/thisdavej/wordlookup-tutorial.git
cd wordlookup-tutorial
```

1. Build using uv:

```sh
uv build
```

1. Test the Python wheel created during the build step:

```sh
uv tool run wordlookup

# You can also use `uvx` which is an alias for `uv tool run`
uvx wordlookup
```

1. Install the Python wheel persistently:

```sh
uv tool install wordlookup
```

### Distributing the Python wheel (.whl) file to others to install

1. Run/test the command provided in the wheel without explicitly installing into a persistent environment or adding it to our system's PATH.

```sh
uv tool run wordlookup-0.1.0-py3-none-any.whl

# You can also use `uvx` which is an alias for `uv tool run`
uvx wordlookup-0.1.0-py3-none-any.whl
``

1. Install the Python wheel

```sh
uv tool install wordlookup-0.1.0-py3-none-any.whl
```

### Development

To see your development changes in action instantly, use `uv run`:

```sh
uv run wordlookup <word>
```

This command will execute the tool with your most recent code modifications.

## License

This project is licensed under the Apache License, Version 2.0 - see the [LICENSE](LICENSE) file for details.
