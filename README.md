# go-media-devices-state

[![Go Report Card](https://goreportcard.com/badge/github.com/antonfisher/go-media-devices-state)](https://goreportcard.com/report/github.com/antonfisher/go-media-devices-state)
[![Conventional Commits](https://img.shields.io/badge/Conventional%20Commits-1.0.0-yellow.svg)](https://conventionalcommits.org)

Go module to get camera/microphone state (checks if camera or microphone is ON).

Module uses `cgo` to call native specific API on different platforms (currently only darwin is implemented.)

## Installation

```shell
go get github.com/antonfisher/go-media-devices-state
```

## Demo

```shell
git clone https://github.com/antonfisher/go-media-devices-state.git
go run -a cmd/demo.go
```

## Usage

```go
import {
  "fmt"

  mediaDevices "github.com/antonfisher/go-media-devices-state"
}

func main() {
  fmt.Println("Camera state:", mediaDevices.IsCameraOn())
  fmt.Println("Debug (calls every available API):", mediaDevices.Debug())
}
```

## Supported platforms

| Platform | Supported |
|----------|-----------|
| darwin   | YES       |
| linux    | NOT YET   |
| windows  | NOT YET   |

## Troubleshooting

Get list of cameras registered in the system:
```shell
// macOS
system_profiler SPCameraDataType
```

# License

MIT License.