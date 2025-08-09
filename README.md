# jamzilla-fuzzserver

A fuzzing interface server for jamzilla that provides a Unix domain socket interface for fuzzing operations.

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

## License

🦖
