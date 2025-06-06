# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added
- **HTTP Transport Support**: Added HTTP server functionality alongside existing stdio transport
- Command-line options for transport selection (`--transport`, `--host`, `--port`)
- Environment variable support for HTTP configuration (`MCP_TRANSPORT`, `MCP_HOST`, `MCP_PORT`)
- Nginx reverse proxy compatibility for production deployments
- FastMCP framework integration for MCP server implementation
- Comprehensive test suite using FastMCP client
- Support for both in-memory and stdio transport testing
- Useful links section in GUIDELINES.md with FastMCP documentation

### Changed
- Enhanced `SPARQLConfig` to include HTTP server settings (host, port, transport)
- Modified `run_server()` function to support both stdio and HTTP transports
- Updated command-line argument parser with transport configuration group
- Updated imports to use `fastmcp` instead of `mcp.server.fastmcp`
- Improved test file structure with proper FastMCP client usage
- Enhanced requirements.txt with all necessary dependencies

### Removed
- Legacy test files (`basic_test.py`, `test_server.py`)
- Outdated MCP client implementations

### Fixed
- HTTP transport implementation using correct FastMCP `streamable-http` transport
- Pydantic validation error: replaced deprecated `regex` parameter with `pattern`
- Installation script (install.sh) with proper systemd service configuration
- Service files with correct Python paths and virtual environment setup
- Import errors in server.py and test files
- FastMCP client integration and response parsing
- Dependencies in requirements.txt

## [1.0.0] - 2025-05-27

### Added
- Initial SPARQL-enabled MCP server implementation
- Support for SPARQL query execution against configurable endpoints
- Multiple caching strategies (LRU, LFU, FIFO)
- Result formatting options (JSON, Simplified, Tabular)
- Daemon mode support for background operation
- Comprehensive configuration system with environment variable support
- MCP protocol compliance with tool definitions
- Cache management tools
- Systemd service configuration
- Modular architecture with separation of concerns

### Features
- **SPARQL Integration**: Execute SPARQL queries against any endpoint
- **Caching System**: Configurable caching with multiple replacement strategies
- **Result Formatting**: Multiple output formats for query results
- **MCP Tools**: 
  - `query`: Execute SPARQL queries with optional formatting
  - `cache`: Manage query cache (stats, clear operations)
- **Production Ready**: Daemon mode, logging, and systemd integration
- **Configurable**: Environment variables and command-line arguments
- **Error Handling**: Comprehensive error handling and logging

### Technical Details
- Built with FastMCP framework for MCP protocol implementation
- Uses SPARQLWrapper for SPARQL endpoint communication
- Pydantic for configuration validation
- Modular cache system with pluggable strategies
- Comprehensive test coverage
- Type hints throughout codebase
- Production-ready logging and error handling