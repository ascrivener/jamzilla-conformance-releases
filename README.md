# jamzilla-fuzzserver

A fuzzing interface server for JAM (JavaScript Analysis and Manipulation) that provides a Unix domain socket interface for fuzzing operations.

## Overview

jamzilla-fuzzserver is a Go-based server that creates a Unix domain socket interface for fuzzing JavaScript engines and related targets. It uses an in-memory state repository for efficient operation and provides a clean interface for fuzzing tools to interact with JAM targets.

## Features

- **Unix Domain Socket Interface**: Communicates via Unix domain sockets for efficient IPC
- **In-Memory State Management**: Uses an in-memory database for fast state operations
- **Signal Handling**: Graceful shutdown on SIGINT/SIGTERM signals
- **Configurable Socket Path**: Customizable socket location via command-line flags

## Usage

### Command Line Options

```bash
jamzilla-fuzzserver [options]
```

**Options:**
- `-socket <path>`: Path for the Unix domain socket (default: `/tmp/jam_target.sock`)

### Example

```bash
# Start server with default socket path
./jamzilla-fuzzserver

# Start server with custom socket path
./jamzilla-fuzzserver -socket /tmp/custom_jam.sock
```

## Available Binaries

This repository contains pre-built binaries for multiple architectures:

| Binary | Architecture | Size | Description |
|--------|-------------|------|-------------|
| `jamzilla-fuzzserver-full-amd64-linux` | Linux x86_64 | ~25MB | Full-featured version |
| `jamzilla-fuzzserver-full-arm64-darwin` | macOS ARM64 | ~23MB | Full-featured version |
| `jamzilla-fuzzserver-tiny-amd64-linux` | Linux x86_64 | ~14MB | Minimal version |
| `jamzilla-fuzzserver-tiny-arm64-darwin` | macOS ARM64 | ~11MB | Minimal version |

### Choosing a Binary

- **Full versions**: Include all features and debugging capabilities
- **Tiny versions**: Stripped-down versions for production or resource-constrained environments

## Architecture

The server consists of several key components:

1. **Socket Server**: Handles Unix domain socket communication
2. **State Repository**: Manages fuzzing state in memory
3. **Fuzz Interface**: Provides the main fuzzing API
4. **Signal Handler**: Ensures clean shutdown

## Integration

The server is designed to work with fuzzing frameworks that can communicate over Unix domain sockets. It provides a standardized interface for:

- Target initialization
- Test case execution
- State management
- Result collection

## Development

The server is built with Go and uses the following key packages:
- Standard library for socket handling and signal management
- Custom `staterepository` package for state management
- Custom `fuzzinterface` package for fuzzing operations

## License

🦖
