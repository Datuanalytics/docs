
This repository contains the documentation for the datu core, a simple yet powerful framework for building and running AI agents. The documentation is built using [MkDocs](https://www.mkdocs.org/) and provides guides, examples, and API references.

The official documentation is available online at: 

## Local Development

### Prerequisites

- Python 3.10+

### Setup and Installation

```bash
# Create and activate virtual environment
python -m venv .venv
source .venv/bin/activate  # On Windows use: .venv\Scripts\activate

pip install -r requirements.txt
```

### Building and Previewing

To generate the static site:

```bash
mkdocs build
```

This will create the site in the `site` directory.

To run a local development server:

```bash
mkdocs serve
```

This will start a server at http://127.0.0.1:8000/ for previewing the documentation.

## Contributing ❤️

We welcome contributions! See our [Contributing Guide](CONTRIBUTING.md) for details on:
- Reporting bugs & features
- Development setup
- Contributing via Pull Requests
- Code of Conduct
- Reporting of security issues

## License

This project is licensed under the Apache License 2.0 - see the [LICENSE](LICENSE) file for details.

## Security

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.
