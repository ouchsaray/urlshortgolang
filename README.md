# URL Shortener in Go
## Project Overview
This is a simple URL shortener application written in Go. The application serves as an HTTP handler that redirects users to different URLs based on path mappings, similar to how URL shortening services work.
## Features
- Map-based URL redirects
- YAML-based URL redirects
- Fallback to a default handler when a path isn't matched

## Prerequisites
- Go 1.23 or later
- [gopkg.in/yaml.v2](https://github.com/go-yaml/yaml) package

## Project Structure
``` 
urlshortgolang/
├── README.md
├── src/
│   ├── main.go         # Application entry point
│   └── utils/
│       └── handler.go  # URL shortening handlers implementation
```
## Installation
1. Clone this repository:
``` bash
   git clone https://github.com/yourusername/urlshortgolang.git
   cd urlshortgolang
```
1. Install the required YAML package:
``` bash
   go get gopkg.in/yaml.v2
```
## Running the Application
From the project root directory:
``` bash
go run src/main.go
```
This will start an HTTP server (typically on port 8080) that handles URL redirection.
## How It Works
The application handles HTTP requests and checks if the requested path matches any configured redirects:
1. When a request comes in (e.g., `/dogs`), the handler checks if this path exists in its mapping
2. If found, it redirects the user to the corresponding URL (e.g., `https://www.somesite.com/a-story-about-dogs`)
3. If not found, it falls back to the default handler

## Implementation Details
The application uses two types of handlers:
1. **MapHandler**: Uses a Go map to match paths to their destination URLs
2. **YAMLHandler**: Parses YAML data to build a map of paths to destination URLs

## Example YAML Format
``` yaml
- path: /urlshort
  url: https://github.com/gophercises/urlshort
- path: /urlshort-final
  url: https://github.com/gophercises/urlshort/tree/solution
```
## Advanced Features
You can extend this application with:
1. JSON-based configuration support
2. Database integration for storing redirect mappings
3. Command-line flags for specifying configuration files

## License
[Your License Information]
## Contributing
Contributions are welcome! Please feel free to submit a Pull Request.
