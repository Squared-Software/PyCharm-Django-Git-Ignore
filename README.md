# PyCharm-Django-Git-Ignore
A git ignore useful for publishing a Django website as open-source. Ignores the the default SqlLite database, .idea files from PyCharm, and provides for private setting files. You can keep private setting files out of the github repository by naming a file _private.py.

An example of a private settings file is:

At the end of your settings file, import the private settings file. This will over write any properties in the public settings file with properties from the private.
settings.py:
```python
import os
BASE_DIR = os.path.dirname(os.path.dirname(os.path.abspath(__file__)))
...
...
...

try:
    from settings_private import *
except ImportError:
    pass
```

Create a file called settings_private.py in which to store all your private settings
settings_private.py:
```python
import os
BASE_DIR = os.path.dirname(os.path.dirname(os.path.abspath(__file__)))
...
...
...

```
