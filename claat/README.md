# Codelabs command line tool

The program takes an input in form of a resource location,
which can either be a Google Doc ID, local file path or an arbitrary URL.
It then converts the input into a codelab format, HTML by default.

For more info run `claat help`.

## Install

The easiest way is to download pre-compiled binary.
The binaries, as well as their checksums are available at the
[Releases page](https://github.com/Noname-SA/claat-tool/releases/latest).

Alternatively, if you have [Go installed](https://golang.org/doc/install):

    go install github.com/Noname-SA/claat-tool/claat@latest


If none of the above works, compile the tool from source following Dev workflow
instructions below.

## Dev workflow

Workaround for some Go version issues & .sh permission errors

1. Clone this repo into a nn-tools directory `git clone https://github.com/Noname-SA/claat-tool.git nn-tools`

2. Navigate to the claat command directory `cd nn-tools/claat`

3. Build the claat command `go build .` This will create a `claat` command executable that you can use.

4. Now update youur PATH env variable, using the default mac terminal, the command is `vi ~/.zshrc`

5. To edit the file press `i` and then insert this line at the end `export PATH=$PATH:$HOME/na-tools/claat` and then hit `ESC` and type `:x` to save and exit.

6. Now open a NEW terminal window and type `claat`, should be working.

**Prerequisites**

1. Install [Go](https://golang.org/dl/) if you don't have it.
2. Make sure this directory is placed under
   `$GOPATH/src/github.com/Noname-SA/claat-tool`.
3. Install package dependencies with `go get ./...` from this directory.

To build the binary, run `make`.

Testing is done with `make test` or `go test ./...` if preferred.

Don't forget to run `make lint` or `golint ./...` before creating a new CL.

To create cross-compiled versions for all supported OS/Arch, run `make release`.
It will place the output in `bin/claat-<os>-<arch>`.
