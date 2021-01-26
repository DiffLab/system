### gitless


#### 0001-Update-requirements.patch
***
A trivial solution to make gitless work seamlessly. The current configuration established by the developers causes errors every time pygit2/libgit2 is updated. This simple patch fixes the aforementioned inconvenience.
***

#### 0002-Fix-gitless-error.patch
***
Another simple solution that fixes a bug that prevents the application from working.

```
$ gl init
✔ Local repo created
$ gl track PKGBUILD
Traceback (most recent call last):
  File "/usr/lib/python3.9/site-packages/gitless/cli/gl.py", line 40, in <module>
    pprint.DISABLE_COLOR = not repo.config.get_bool('color.ui')
  File "/usr/lib/python3.9/site-packages/pygit2/config.py", line 219, in get_bool
    check_error(err)
  File "/usr/lib/python3.9/site-packages/pygit2/errors.py", line 65, in check_error
    raise GitError(message)
_pygit2.GitError: failed to parse 'auto' as a boolean value

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File "/usr/bin/gl", line 33, in <module>
    sys.exit(load_entry_point('gitless==0.8.8', 'console_scripts', 'gl')())
  File "/usr/bin/gl", line 25, in importlib_load_entry_point
    return next(matches).load()
  File "/usr/lib/python3.9/importlib/metadata.py", line 77, in load
    module = import_module(match.group('module'))
  File "/usr/lib/python3.9/importlib/__init__.py", line 127, in import_module
    return _bootstrap._gcd_import(name[level:], package, level)
  File "<frozen importlib._bootstrap>", line 1030, in _gcd_import
  File "<frozen importlib._bootstrap>", line 1007, in _find_and_load
  File "<frozen importlib._bootstrap>", line 986, in _find_and_load_unlocked
  File "<frozen importlib._bootstrap>", line 680, in _load_unlocked
  File "<frozen importlib._bootstrap_external>", line 790, in exec_module
  File "<frozen importlib._bootstrap>", line 228, in _call_with_frames_removed
  File "/usr/lib/python3.9/site-packages/gitless/cli/gl.py", line 42, in <module>
    prrint.DISABLE_COLOR = (
NameError: name 'prrint' is not defined
$ gl add
Traceback (most recent call last):
  File "/usr/lib/python3.9/site-packages/gitless/cli/gl.py", line 40, in <module>
    pprint.DISABLE_COLOR = not repo.config.get_bool('color.ui')
  File "/usr/lib/python3.9/site-packages/pygit2/config.py", line 219, in get_bool
    check_error(err)
  File "/usr/lib/python3.9/site-packages/pygit2/errors.py", line 65, in check_error
    raise GitError(message)
_pygit2.GitError: failed to parse 'auto' as a boolean value

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File "/usr/bin/gl", line 33, in <module>
    sys.exit(load_entry_point('gitless==0.8.8', 'console_scripts', 'gl')())
  File "/usr/bin/gl", line 25, in importlib_load_entry_point
    return next(matches).load()
  File "/usr/lib/python3.9/importlib/metadata.py", line 77, in load
    module = import_module(match.group('module'))
  File "/usr/lib/python3.9/importlib/__init__.py", line 127, in import_module
    return _bootstrap._gcd_import(name[level:], package, level)
  File "<frozen importlib._bootstrap>", line 1030, in _gcd_import
  File "<frozen importlib._bootstrap>", line 1007, in _find_and_load
  File "<frozen importlib._bootstrap>", line 986, in _find_and_load_unlocked
  File "<frozen importlib._bootstrap>", line 680, in _load_unlocked
  File "<frozen importlib._bootstrap_external>", line 790, in exec_module
  File "<frozen importlib._bootstrap>", line 228, in _call_with_frames_removed
  File "/usr/lib/python3.9/site-packages/gitless/cli/gl.py", line 42, in <module>
    prrint.DISABLE_COLOR = (
NameError: name 'prrint' is not defined
$ gl status
Traceback (most recent call last):
  File "/usr/lib/python3.9/site-packages/gitless/cli/gl.py", line 40, in <module>
    pprint.DISABLE_COLOR = not repo.config.get_bool('color.ui')
  File "/usr/lib/python3.9/site-packages/pygit2/config.py", line 219, in get_bool
    check_error(err)
  File "/usr/lib/python3.9/site-packages/pygit2/errors.py", line 65, in check_error
    raise GitError(message)
_pygit2.GitError: failed to parse 'auto' as a boolean value

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File "/usr/bin/gl", line 33, in <module>
    sys.exit(load_entry_point('gitless==0.8.8', 'console_scripts', 'gl')())
  File "/usr/bin/gl", line 25, in importlib_load_entry_point
    return next(matches).load()
  File "/usr/lib/python3.9/importlib/metadata.py", line 77, in load
    module = import_module(match.group('module'))
  File "/usr/lib/python3.9/importlib/__init__.py", line 127, in import_module
    return _bootstrap._gcd_import(name[level:], package, level)
  File "<frozen importlib._bootstrap>", line 1030, in _gcd_import
  File "<frozen importlib._bootstrap>", line 1007, in _find_and_load
  File "<frozen importlib._bootstrap>", line 986, in _find_and_load_unlocked
  File "<frozen importlib._bootstrap>", line 680, in _load_unlocked
  File "<frozen importlib._bootstrap_external>", line 790, in exec_module
  File "<frozen importlib._bootstrap>", line 228, in _call_with_frames_removed
  File "/usr/lib/python3.9/site-packages/gitless/cli/gl.py", line 42, in <module>
    prrint.DISABLE_COLOR = (
NameError: name 'prrint' is not defined
```

***
