Simple snippet  

```python
def get_file_list(dirname):
    ret = list()

    for f in os.listdir(dirname):
        if os.path.isfile(dirname + '/' + f):
            ret.append(f)

    return sorted(ret)
```
