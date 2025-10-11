# Directory Content Analysis Tool

A comprehensive Python utility for analyzing and extracting the contents of source code files across a project directory structure, outputting them into a single organized document for easier review and analysis.

## Features

- **Recursive Directory Scanning**: Analyzes entire project structures including subdirectories
- **File Type Filtering**: Include/exclude files by extension or specific filenames
- **Smart Binary Detection**: Automatically skips binary files while allowing trusted text extensions
- **Directory Tree Generation**: Creates visual directory structure representation
- **Configurable Output**: Customizable output formatting with summary statistics
- **Size Limits**: Configurable maximum file size processing limits
- **Flexible Configuration**: INI-based configuration with command-line overrides

## Installation

No special installation required. Just ensure you have Python 3.6+ installed.

```bash
git clone https://github.com/smaxiso/print-project.git
cd print-project
```

## Usage

### Basic Usage

```bash
# Analyze current directory
python print_project.py

# Analyze specific directory
python print_project.py -f /path/to/project

# Show console output during processing
python print_project.py --console
```

### Advanced Options

```bash
# Skip specific directories
python print_project.py -s "tests,docs,build"

# Include only specific file extensions
python print_project.py -e py,js,ts

# Exclude specific file extensions
python print_project.py -x txt,log,tmp

# Force include specific files
python print_project.py --include-files "config.local.properties,.env.production"

# Process only specific files
python print_project.py --only-include-files "main.py,config.py,README.md"

# Custom output filename
python print_project.py -o my_project_analysis

# Create timestamped output (don't overwrite existing)
python print_project.py --duplicate

# Skip directory tree generation
python print_project.py --no-tree

# Custom tree exclusions (different from file processing)
python print_project.py --tree-exclude ".git,venv,node_modules"
```

## Command Line Options

| Option | Description |
|--------|-------------|
| `-f, --folder` | Directory to process (default: current directory) |
| `-s, --skip` | Comma-separated list of directories to exclude |
| `-e, --extensions` | Comma-separated list of file extensions to include |
| `-x, --exclude-ext` | Comma-separated list of file extensions to exclude |
| `-i, --ignore-files` | Comma-separated list of specific files to exclude |
| `--include-files` | Force include specific files (overrides filters) |
| `--only-include-files` | Process ONLY these specific files |
| `--max-size` | Maximum file size in bytes to process |
| `--console` | Show console output during processing |
| `-o, --output` | Output filename (without extension) |
| `--duplicate` | Create timestamped output instead of overwriting |
| `--no-summary` | Exclude summary from output file |
| `--no-tree` | Skip directory tree generation |
| `--tree-exclude` | Override directory exclusions for tree generation |
| `-h, --help` | Show help message |

## Configuration

The tool uses a `config.ini` file for default settings. You can customize:

- Default directories to skip
- File extensions to exclude
- Trusted text file extensions
- Maximum file size limits
- Default output behavior

## Output

The tool generates a `.txt` file containing:

1. **Directory Tree**: Visual representation of the project structure
2. **File Analysis**: Content of each processed file with:
   - File path and metadata
   - Line numbers
   - Syntax highlighting markers
3. **Summary Statistics**: 
   - Total files processed
   - Files skipped (with reasons)
   - Processing time and performance metrics

## Files

- `print_project.py` - Main application (current version)
- `config.ini` - Configuration file with default settings
- `VERSION` - Current version number
- `CHANGELOG.md` - Version history and release notes
- `CONTRIBUTING.md` - Guidelines for contributors
- `archive/` - Archived versions and backup files
  - `print_project_bkp.py` - Previous version (v1.0.0)
  - `README.md` - Archive documentation

## Use Cases

- **Code Reviews**: Generate comprehensive project snapshots
- **Documentation**: Create detailed project overviews
- **Analysis**: Understand project structure and content
- **Migration**: Prepare project content for analysis or transfer
- **AI/LLM Input**: Generate context-rich project representations

## Contributing

We welcome contributions! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for detailed guidelines on:

- Setting up the development environment
- Code style and testing requirements
- Submitting bug reports and feature requests
- Pull request process and release guidelines

For version history and recent changes, see [CHANGELOG.md](CHANGELOG.md).

## License

This project is open source. See the repository for license details.