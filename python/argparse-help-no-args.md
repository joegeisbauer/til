# Print Help in argparse when no Command Line Arguments

I was researching how to print the help statement along with the usage statement while using argparse in python when lo and behold no command line arguments are actually provided. Here is a link to the issue in stackoverflow [StackOverflow Discussion](https://stackoverflow.com/questions/4042452/display-help-message-with-python-argparse-when-script-is-called-without-any-argu?answertab=active#tab-top). Most of the answers there required another module, such as sys, to be imported or were using optional arguments. I wanted to discover an answer that used only argparse, worked with required arguments, and if possible worked without catching exceptions. I ended up with the following:

```python
import argparse

if __name__ == '__main__':

    arg_parser = argparse.ArgumentParser(add_help=False)
    arg_parser.add_argument('input_file', type=str, help='The path to the input file.')
    arg_parser.add_argument('output_file', type=str, help='The path to the output file.')
    arg_parser.add_argument('-h','--help', action='store_true', help='show this help message and exit')
    arg_parser.usage = arg_parser.format_help()
    args = arg_parser.parse_args()
```

The main idea was to use the format_help function in order to provide the help string to the usage statement. Setting add_help to False in the call to ArgumentParser() prevents the help statement from printing twice in certain circumstances. However, I had to create an argument for the optional help argument that mimicked the typical help message once it was set to False in order to display the optional help argument in the help message. The action is set to 'store_true' in the help argument to prevent the help message from filling in a value like 'HELP' for the parameter when it prints the help message.