# UVIC Report Format

Automatic formatter for UVIC Computer Science work term reports.

## Introduction

I used this package to generate my co-op work-term reports for the Spring 2021 and
Summer 2021 terms at UVIC. The content for a report is written in markdown and yaml files
and generated using `latex` and `pandoc` templates.

## Installation

```shell script
pip install uvic-report-format
```

## Usage

### Configuration file

Create a `report.yml` file containing your report information.

```yml
info:
    title: Your Report Title
    institution: University of Victoria
    faculty: Engineering and Computer Science
    term: Spring | Fall | Summer
    year: 2021
    name: Your Name
    student_id: v00XXXXXX
    email: yourname@uvic.ca
    employer: Your Employer
    location: Victoria, BC, Canada

content:
  glossary: ./content/glossary.yml
  executive_summary: ./content/executive_summary.md
  personal_reflection: ./content/personal_reflection.md
  introduction: ./content/introduction.md
  body: ./content/body.md
  conclusion: ./content/conclusion.md
  references: ./content/refs.bib

config:
  output: ./report.pdf
```

### CLI Usage

> `uvic-report-format --help`

```text
Usage: uvic-report-format [OPTIONS] COMMAND [ARGS]...

Options:
  --help  Show this message and exit.

Commands:
  compile

```

> `uvic-report-format compile --help`

```text
Usage: uvic-report-format compile [OPTIONS]

Options:
  -o, --open
  -f, --yml-file PATH  The YAML config file.
  --help               Show this message and exit.
```

### Content

Create content files as layed out in your `report.yml` file.

### Generate the report

Once the content files are in place generate the report using the following:

```shell script
uvic-report-format compile -f report.yml --open
```

The resulting pdf will be opened in your browser for preview.
