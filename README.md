# University of Amsterdam Thesis Template

This is an unofficial Typst port of the official Master of Artificial Intelligence thesis template for the University of Amsterdam.


## Usage

To use this template, run

```bash
typst init @preview/uva-thesis:0.0.1
```

from any directory to initialize a new project.

## Functions

The following code assumes all names from this template were imported beforehand.

```typst
#import "@preview/uva-thesis:0.0.1": *
```

### `uva-thesis`

An initialization function for show rules.

```typst
#show: uva-thesis
```

### `uva-titlepage`

Renders the first page of the thesis.

```typst
#show: uva-titlepage.with(
  title: "The Answer to Life, the Universe, and Everything",
  author: "John Q. Public",
  student-number: "12345678",
  supervisors: ("John Smith",),
  examiner: "Jane Doe",
  second-reader: "John Doe",
  degree: "MSc Artificial Intelligence",
  credits: "42 EC",
  // date: datetime(day: 1, month: 1, year: 1971),
  date: datetime.today(),
  period: "Period in which the research was carried out"
)
```

### `uva-abstract`

Renders an abstract for your thesis.

```typst
#uva-abstract[
  Your abstract here.
]
```

### `uva-chapter`

Introduces a new chapter. Replaces first level headings `=`, so section titles within your chapter should be prefixed by `==`.

```typst
#uva-chapter("Your Chapter Title")

== Your Section Title

...
```

### `definition`, `theorem`, `lemma`, `corollary`, `remark`, `proof`

Introduces the appropriate block.

```typst
#definition[
  We defined the language $cal(L)$ as follows:

  $ phi.alt ::= top | p | phi.alt and phi.alt $
]
```

### `mathcounter`

A counter keeping all the mathematical elements of this template in sync.

```typst
#import "@preview/great-theorems:0.1.1": *

#let axiom = mathblock(
  blocktitle: "Axiom",
  counter: mathcounter, // axioms follow the same numbering as definitions, etc.
)
```

## Attributions

- The original [Typst ILLC MoL thesis template by Stefano Volpe](https://codeberg.org/foxy/illc-mol-thesis) on which this template is based on.