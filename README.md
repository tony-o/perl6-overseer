#Overwatch

Perl6 Overwatch can be used to restart programs when they crash or 
when files are modified.  

##Usage: 

```
overwatch [options] <program> [<program arguments>]
```
    
##Required:

```
  <program>
```
    
A program/script name is required.

##Options:

```
  -e=<executable> | --execute=<executable>
```
Default: 'perl6'
The executable that runs the specified <program>.

  -k | --keep-alive
    Default: True
    Automatically rerun the program.
 
  -x | --exit-on-error
    Default: False
    Stop overwatch if the <program> exited with a
    non-zero code.

  -q | --quiet
    Default: False
    Prevents overwatch from printing informative
    messages to stdout. 

  -w | --watch
    Default: []
    Directories/files to watch for changes, when a
    file is changed the <program> is restarted.

Notes:
  Multiple -w switches may be specified
  To negate a [True|False} value you can use -/q (same as -q=False)

Examples:
  overwatch app.pl6
  overwatch -w=models mvc.pl6
  overwatch -w=/tmp/ -e=/bin/sh shellscript.sh --shellarg=go