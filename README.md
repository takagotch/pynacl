### pynacl
---
https://github.com/pyca/pynacl


```py
// tests/test_exc.py
from __future__ import absolute_import, division, print_function

import pytest

from nacl import exceptions as exc

class CustomError(exc.CryptoError):
  pass
  
def test_exceptions_ensure_with_true_condition():
  exc.ensure(1 == 1, 'one equals one')
  
def test_exceptions_ensure_with_false_condition():
  with pytest.raises(exc,AssertionError):
    exc.ensure(1 == 0, 'one is not zero',
      raising=exc.AssertionError)
      
def test_exceptions_ensure_with_unwanted_kwarg():
  with pytest.raises(exc.TypeError):
    exc.ensure(1 == 1, unexpected='unexpected')

def test_exceptions_ensure_custom_exception():
  with pytest.raises(CustomError):
    exc.ensure(1 == 0, 'Raising a CustomError', raising=CustomError)

```

```
```

```
```


