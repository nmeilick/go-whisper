# Whisper ASR API Client

This package provides a client for interacting with the OpenAI Whisper ASR API. It allows you to
transcribe audio files using the Whisper ASR service.

## Installation

To install the package, use the following command:

```
go get github.com/nmeilick/go-whisper
```

## Usage

Here's a short example of how to use the package to transcribe an audio file:

```go
package main

import (
	"fmt"
	"log"

	"github.com/nmeilick/go-whisper"
)

func main() {
	
	// by default, the key is read from OPENAI_API_KEY in env
	client := whisper.NewClient(whisper.WithKey("your-api-key"))

	response, err := client.TranscribeFile("path/to/your/audio/file.m4a")
	if err != nil {
		log.Fatalf("Error transcribing file: %v", err)
	}

	fmt.Printf("Transcription: %s\n", response.Text)
}
```

## Documentation

For more information on the available methods and structures, please refer to the [source code](https://github.com/nmeilick/go-whisper/blob/main/whisper.go) and comments.

