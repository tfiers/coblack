# comform

<em><a href="https://black.readthedocs.io">black</a></em>-compliant formatter for multiline comments.

## Example

Before:
```python
def care_for(my_favorite_plant):
    my_favorite_plant.water(100 * mL)  # This is a nice and useful comment, but it is too long to fit on one line, given the recommended line length.
```

After:
```python
def care_for(my_favorite_plant):
    my_favorite_plant.water(100 * mL)  # This is a nice and useful comment, but it is
    #                                  # too long to fit on one line, given the
    #                                  # recommended line length.
```
(The extra `#`'s at the beginning of each line are necessary to be _black_-compliant
— _black_ would pull the comments to the start of the line if they were not there).


## Usage

In your terminal (or as a [PyCharm _External Tool_](https://www.jetbrains.com/help/pycharm/configuring-third-party-tools.html),
or a [VS Code _Task_](https://code.visualstudio.com/docs/editor/tasks)):
```
$ cblack my_file.py
```
This wraps & fills out multiline comments, and then passes the result through `black`.\
The file is edited in-place.

You can list additional options (such as eg `-l 80` to set the line length) 
using `cblack -h`.


## Python API

```python
import comform

comform.format_file("path/to/my_file.py")
```
The file may also be given as a <em><a href="https://docs.python.org/3/library/pathlib.html">pathlib.Path</a></em>.
