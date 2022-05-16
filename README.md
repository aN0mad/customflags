# customflags
Package customflags implements a modified version of the golang command-line flag parsing.

## Changes
- UPDATED: Updated Parse() to pass []string variable instead of parsing from os.Args
- Updated: Updated Parse(arr_args []string) to handle error message and return an error instead of panic
- Updated: Updated "var CommandLine" to "ContinueOnError" instead of "ExitOnError"
- Updated: Added function NewCommandLine() which creates a NewFlagSet() and returns a pointer to FlagSet
- Added fsParsed() function

## Notes:
- Package was modified to allow flag parsing multiple times in the program with the same flag definitions.
- Each function that needs to parse flags can use the code snippet below to create a unique FlagSet for that function

## Examples

Parsing flag Int
```
package main

import (
	"fmt"

	"github.com/theRealFr13nd/customflags"
)

func main() {
	// Argument slice
	args := []string{"-n", "5"}

	// Create our FlagSet
	fs := customflags.NewCommandLine()

	// Create the flags we want in this FlagSet
	nFlag := fs.Int("n", 0, "Number passed in")

	// Parse the arg slice into the flags we defined
	err := fs.Parse(args)
	if err != nil {
		panic(err)
	}

	// Use the parsed flags
	fmt.Printf("nFlag: %d\n", *nFlag)
}

```
