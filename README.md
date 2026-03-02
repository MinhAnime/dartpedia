# Dartpedia

A Dart command-line application for searching and reading Wikipedia articles. Built using Dart Workspaces to efficiently manage multiple interrelated packages.

## Project Structure

This repository uses Dart Workspaces (requires Dart SDK `^3.11.0`) and is divided into the following internal packages:

- **`cli`**: The main command-line interface application that wires everything together.
- **`command_runner`**: A custom, lightweight command parser and execution library.
- **`wikipedia`**: A library responsible for interacting with the Wikipedia Web APIs and modeling the JSON responses.

## Getting Started

Because this project utilizes Dart feature Workspaces, make sure your Dart SDK is at least version `3.11.0`.

First, resolve dependencies from the workspace root:

```bash
dart pub get
```

## Usage

You can run the application by executing the main script inside the `cli` package:

```bash
cd cli
dart run bin/cli.dart <command> [options] <arguments>
```

### Available Commands

- **`help`**: Print usage information. 
  - Example: `dart run bin/cli.dart help`
- **`search`**: Search Wikipedia for a specific query. 
  - Example: `dart run bin/cli.dart search "Dart programming"`
- **`get_article`**: Fetch and display the extract of a Wikipedia article by its exact title.
  - Example: `dart run bin/cli.dart get_article "Dart_(programming_language)"`

### Logs

The `cli` application handles its own basic error logging, saving records to `cli/logs/` based on the current date, to make debugging any unhandled API errors or internal exceptions easier.
