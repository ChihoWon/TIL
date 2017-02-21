Simple snippet  

```python
def get_subdirectories():
    ret = list()

    for x in glob('*/'):
        ret.append(x.split('/')[0])

    return sorted(ret)
```
