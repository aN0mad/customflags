# customflags
Package customflags implements a modified version of the golang command-line flag parsing.

## Changes
- Updated: Updated Parse() to pass []string variable instead of parsing from os.Args
- Updated: Updated Parse(arr_args []string) to handle error message and return an error instead of panic
- Updated: Updated "var CommandLine" to "ContinueOnError" instead of "ExitOnError"

## Examples

Parsing flag Int
```
args := []string{"-n", "1"}
var nFlag = customflag.Int("n", 1234, "help message for flag n")
customflag.Parse(args)
fmt.Printf("nFlag: %d\n", *nFlag)
```
