# osint-handle-dataset

A dataset of handle transformation patterns for OSINT purposes.
 
One of the core problems when searching for a person by username — people rarely use the same handle everywhere. Instead, they apply various transformations: leet speak, script switching, diminutive suffixes, semantic variations, and combinations thereof.
 
This dataset collects and formalizes such patterns so they can be used in tools for generating handle variations.
 
## Structure
 
```
dataset/
  leet.json           # character substitution with digits/special chars
  script_switch.json  # script switching (latin ↔ cyrillic, homoglyphs) | WIP
  suffixes.json       # diminutive and semantic suffixes | WIP
  combined.json       # examples combining multiple transformations | WIP
  ...                 
schema.md             # file format description
```
 
## Transformation types
 
| Type | Description | Example |
|------|-------------|---------|
| `leet` | Character substitution with digits/special chars | `kwotah` -> `kw074h`, `leet` -> `1337` |
| `script_switch` | Script switching or homoglyph usage | `BoPk` -> `Ворк` (anglicism in Ruissian), `MoHeTka` -> `Монетка`|
| `suffix` | Adding diminutive or semantic suffixes | `kwotah` -> `kwotahxd`, `kwotah` -> `kwot'yah` (`квотах` -> `квотях`) |
| `combined` | Combination of multiple transformations | `разочарование` -> `Pa3o4aPoBaHue` (leet + script_switch), `заработок` -> `3aPa6oTok` (leet + script_switch)|
 

## Format
 
Each file contains:
- a substitution/rule table (`substitutions`)
- application pattern descriptions (`patterns`)
- verified real-world examples (`verified_examples`)
See [schema.md](schema.md) for details.
 
## Origin
 
The dataset is based on real observations of how people transform their own (or mostly mine) handles across different platforms.
# osint-handle-dataset

A dataset of handle transformation patterns for OSINT purposes.
 
One of the core problems when searching for a person by username -- people sometimes don't use the same handle everywhere. Instead, they apply various transformations: leet speak, script switching, diminutive suffixes, semantic variations, and combinations thereof.
 
This dataset collects and formalizes such patterns so they can be used in tools for generating handle variations.
 
## Structure
 
```
dataset/
  leet.json           # character substitution with digits/special chars
  script_switch.json  # script switching (latin ↔ cyrillic, homoglyphs) | WIP
  suffixes.json       # diminutive and semantic suffixes | WIP
  combined.json       # examples combining multiple transformations | WIP
  ...                 
schema.md             # file format description
```
 
## Transformation types
 
| Type | Description | Example |
|------|-------------|---------|
| `leet` | Character substitution with digits/special chars | `kwotah` -> `kw074h`, `leet` -> `1337` |
| `script_switch` | Script switching or homoglyph usage | `BoPk` -> `Ворк` (anglicism in Ruissian), `MoHeTka` -> `Монетка`|
| `suffix` | Adding diminutive or semantic suffixes | `kwotah` -> `kwotahxd`, `kwotah` -> `kwot'yah` (`квотах` -> `квотях`) |
| `combined` | Combination of multiple transformations | `разочарование` -> `Pa3o4aPoBaHue` (leet + script_switch), `заработок` -> `3aPa6oTok` (leet + script_switch)|
 

## Format
 
Each file contains:
- a substitution/rule table (`substitutions`)
- application pattern descriptions (`patterns`)
- verified real-world examples (`verified_examples`)
See [schema.md](schema.md) for details.
 
## Origin
 
The dataset is based on real observations of how people transform their own (or mostly my) handles across different platforms.
