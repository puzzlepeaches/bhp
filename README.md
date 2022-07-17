<div align="center">

# bhp

bhp is a BloodHound user file parser!

<br>

[Installation](#installation) •
[Getting started](#getting-started) •
[Usage](#usage) •
[Coming Soon](#coming-soon)

</div><br>

</div>
<br>

## Installation

bhp supports all major operating systems and can be installed for the PyPi using the following command:

```
pipx install bhp
```

If this tool is not yet availible via PyPi, you can install it directly from the repository using:

```
git clone https://github.com/puzzlepeaches/bhp.git
cd bhp && pip3 install .
```

For development, clone the repository and install it locally using poetry.

```
git clone https://github.com/puzzlepeaches/bhp.git && cd bhp
poetry shell && poetry install
```

<br>

## Getting started

bhp supports the latest BloodHound user json file format. Let's say you ran a BloodHound export on an enagement last summer and now the client is back and asking for social engineering servies. If you want to cheat and get as much coverage as possible, you can parse your previous BloodHound export for users with mailboxes for phishing.

```
bhp gophish 20210414091456_users.json acmecorp.gophish.csv
```

With the output file, you can go into the Gophish web application and add the users to the campaign super easily.

<br>

## Usage

The bhp help menu is shown below:

```
Usage: bhp [OPTIONS] COMMAND [ARGS]...

  Parse BloodHound JSON userfiles for external use.

Options:
  -h, --help  Show this message and exit.

Commands:
  gophish  Outputs a gophish import compatible csv file.
  stdout   Outputs specified type to stdout.
  txt      Outputs specified type to a text file.
```

The stdout and txt modules allow the user to specify a desired output type. Let's say you want to get an idea of the most common title for users in your export. You can do something like:

```
bhp stdout title 20210414091456_users.json | sort -u
```

<br>

## Thanks

- The BloodHound team for making me stare a graphs all day
- The [Gophish](https://gophish.io/) team for making me mod their project to land phishing emails.
- The Sprocket team member that created the first iteration of this tool way back.
