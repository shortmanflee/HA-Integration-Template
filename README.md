# Home Assistant Integration Template

A comprehensive template repository for developing Home Assistant custom integrations with best practices, testing, and development environment pre-configured.

## Features

- 🏗️ **Complete Integration Structure**: Pre-configured directory structure following Home Assistant standards
- 🐳 **DevContainer Ready**: Full VS Code devcontainer setup with Python 3.13, dependencies, and extensions pre-installed
- 🧪 **Testing Setup**: Includes pytest configuration with Home Assistant custom component testing
- 🔧 **Development Environment**: VS Code tasks and configuration for seamless development
- 📋 **Code Quality**: Ruff linting and formatting pre-configured
- 🐳 **HACS Ready**: Includes `hacs.json` configuration for Home Assistant Community Store
- 📝 **Documentation**: Template files and contribution guidelines

## Quick Start

### Using This Template

1. Click "Use this template" button on GitHub
2. Create your new repository from this template
3. Clone your new repository:
   ```bash
   git clone https://github.com/yourusername/your-integration-name.git
   cd your-integration-name
   ```

4. **🐳 Recommended**: Open in VS Code and use the devcontainer:
   - Open VS Code: `code .`
   - Click "Reopen in Container" when prompted
   - Everything will be automatically configured!

### Customizing Your Integration

1. **Rename the integration directory**:
   ```bash
   mv custom_components/integration_template custom_components/your_integration_name
   ```

2. **Update the integration files**:
   - Edit `custom_components/your_integration_name/__init__.py`
   - Update `hacs.json` with your integration details
   - Modify `README.md` for your specific integration

3. **Update repository references**:
   Run the provided task to update all references:
   ```bash
   ./.vscode/dependencies/update_repo_references.sh
   ```

## Development Environment

This template provides two development approaches, with **devcontainer being the recommended method** for the best development experience.

### 🐳 Recommended: DevContainer (VS Code)

The easiest way to get started is using the included devcontainer configuration:

1. **Prerequisites**:
   - [VS Code](https://code.visualstudio.com/)
   - [Docker Desktop](https://www.docker.com/products/docker-desktop/)
   - [Dev Containers extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)

2. **Setup**:
   - Open the repository in VS Code
   - When prompted, click "Reopen in Container" (or use Command Palette: "Dev Containers: Reopen in Container")
   - The devcontainer will automatically:
     - Set up Python 3.13 environment
     - Install all dependencies
     - Configure the development environment
     - Install recommended VS Code extensions

3. **Ready to develop**: Everything is pre-configured and ready to use!

### 💻 Alternative: Local Development

If you prefer local development without containers:

#### Prerequisites

- Python 3.11+
- Virtual environment (recommended)

#### Setup

1. **Create and activate virtual environment**:
   ```bash
   python -m venv .venv
   source .venv/bin/activate  # On macOS/Linux
   # or
   .venv\Scripts\activate     # On Windows
   ```

2. **Install dependencies**:
   Use the VS Code task "Install Dependencies" or run:
   ```bash
   pip install --upgrade pip
   pip install -r requirements.txt
   ```

3. **Setup development environment**:
   Use the VS Code task "Setup Config Directory" or run:
   ```bash
   mkdir -p config
   ln -sf $(pwd)/custom_components config/custom_components
   ```

### Available VS Code Tasks

- **Install Dependencies**: Install all required Python packages
- **Start Home Assistant (Development)**: Launch HA with your integration in debug mode
- **Setup Config Directory**: Configure the development environment
- **Run Tests**: Execute the test suite with pytest
- **Lint and Fix with Ruff**: Format and lint your Python code
- **Lint Markdown**: Check markdown files for formatting issues
- **Fix Markdown**: Automatically fix markdown formatting issues
- **Lint All (Python + Markdown)**: Run both Python and Markdown linting
- **Update Repository References**: Update template references to your integration

### Running Home Assistant

Start Home Assistant in development mode:
```bash
hass --config ./config --debug
```

Your integration will be available at `http://localhost:8080`

## Testing

Run tests using pytest:
```bash
python -m pytest tests/ -v
```

The template includes:
- Test configuration in `pyproject.toml`
- Coverage reporting
- Async test support
- Home Assistant custom component testing utilities

## Code Quality

This template uses multiple linting tools to ensure code quality:

### Python Code Quality (Ruff)
```bash
# Format code
ruff format .

# Check and fix issues
ruff check . --fix
```

### Markdown Linting (markdownlint)
```bash
# Lint markdown files
npm run lint:markdown

# Fix markdown issues automatically
npm run lint:markdown:fix
```

### Combined Linting
Use the "Lint All (Python + Markdown)" VS Code task or run:
```bash
# Python linting
source .venv/bin/activate && ruff format . && ruff check . --fix

# Markdown linting
npm run lint:markdown:fix
```

### Pre-commit Hooks
Pre-commit hooks are automatically installed in the devcontainer and will run both Python and Markdown linting before each commit:
```bash
# Manually run pre-commit on all files
pre-commit run --all-files
```

## Directory Structure

```
your-integration/
├── custom_components/
│   └── your_integration_name/
│       ├── __init__.py          # Integration entry point
│       ├── manifest.json        # Integration metadata
│       └── ...                  # Your integration files
├── tests/                       # Test files
├── config/                      # Development HA config
├── .vscode/                     # VS Code configuration
├── requirements.txt             # Python dependencies
├── pyproject.toml              # Project configuration
├── hacs.json                   # HACS configuration
└── README.md                   # This file
```

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on contributing to your integration.

## License

This template is released under the MIT License. See [LICENSE](LICENSE) for details.

## Resources

- [Home Assistant Developer Documentation](https://developers.home-assistant.io/)
- [Home Assistant Architecture](https://developers.home-assistant.io/docs/architecture/)
- [Integration Development](https://developers.home-assistant.io/docs/creating_component_index/)
- [HACS Documentation](https://hacs.xyz/docs/publish/start)


## Acknowledgements
This repo has been adapted from the [Integration Blueprint](https://github.com/ludeeus/integration_blueprint) repo maintained by [ludeeus](https://github.com/ludeeus).