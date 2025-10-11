# Changelog

All notable changes to the Directory Content Analysis Tool will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Project Structure
- Reorganized project structure by moving backup files to `archive/` directory
- Added comprehensive CHANGELOG.md
- Added archive documentation

## [2.0.0] - 2025-10-11

### Added
- **Directory Tree Generation**: Visual representation of project structure
- **Smart Tree Exclusions**: Separate exclusion rules for tree vs file processing
- **Force Include Options**: 
  - `--include-files`: Force include specific files while scanning others normally
  - `--only-include-files`: Process ONLY specified files, ignore everything else
- **Enhanced Configuration**: INI-based configuration with command-line overrides
- **Trusted Extensions**: Configurable list of extensions never treated as binary
- **Performance Improvements**: Better binary file detection with lower confidence threshold
- **Advanced Filtering**: 
  - File size limits
  - Multiple extension inclusion/exclusion modes
  - Directory-specific exclusions
- **Rich Output Options**:
  - Timestamped duplicate files (`--duplicate`)
  - Optional summary section (`--no-summary`)
  - Optional tree generation (`--no-tree`)
  - Console output mode (`--console`)
- **Detailed Statistics**: Line counts, processing time, file categorization
- **Error Handling**: Comprehensive error handling and permission management

### Changed
- **Complete Rewrite**: Major architectural improvements from backup version
- **Configuration System**: Moved from hardcoded values to flexible INI configuration
- **Command Line Interface**: Extensive CLI options with help system
- **Output Format**: Enhanced with metadata, statistics, and better organization
- **Binary Detection**: Improved algorithm using chardet library
- **File Processing**: More intelligent filtering and inclusion logic

### Enhanced
- **Documentation**: Comprehensive README with usage examples and scenarios
- **Code Quality**: Better error handling, type hints, and code organization
- **User Experience**: Progress indicators, detailed feedback, and debugging options

## [1.0.0] - Previous Version (Archived)

### Features (Historical - see archive/print_project_bkp.py)
- Basic directory scanning and file content extraction
- Simple filtering by extensions and directories
- Basic binary file detection
- Single output file generation
- Minimal configuration options

### Limitations (Addressed in 2.0.0)
- Limited filtering capabilities
- No tree structure visualization
- Basic binary detection
- Hardcoded configuration values
- Limited output customization
- No performance optimizations

---

## Migration Guide from 1.0.0 to 2.0.0

### Configuration Changes
- Create `config.ini` file for default settings (see provided template)
- Command line arguments have been expanded and some renamed
- Tree generation is now enabled by default (use `--no-tree` to disable)

### New Capabilities
- Use `--include-files` to force include specific files while scanning normally
- Use `--only-include-files` for focused analysis of specific files only
- Customize tree exclusions separately from file processing exclusions
- Enable console output with `--console` for real-time feedback

### Backward Compatibility
- Basic usage (`python print_project.py`) still works with enhanced defaults
- All core functionality preserved and extended
- Output format enhanced but remains readable

## Contributing

When adding new features or making changes:

1. Update the version number following semantic versioning
2. Add entries to the `[Unreleased]` section during development
3. Move entries to a new version section when releasing
4. Include migration notes for breaking changes
5. Document new configuration options and CLI arguments

## Version History Summary

- **v2.0.0**: Complete rewrite with tree generation, advanced filtering, and comprehensive configuration
- **v1.0.0**: Initial version with basic directory scanning and content extraction (archived)