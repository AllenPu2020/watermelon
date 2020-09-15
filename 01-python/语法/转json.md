# python转json支持datetime格式


```python
import json
import datetime
json.JSONEncoder.default = lambda self, obj: (obj.isoformat() if isinstance(obj, datetime.datetime) else None)
```

```
import json
  ...: import datetime
  ...: json.JSONEncoder.default = lambda self, obj: (obj.isoformat() if isinstance(obj, datetime.datetime) else None)
a = {'t': datetime.datetime(2020,9,18)}
json.dumps(a)
Out[4]: '{"t": "2020-09-18T00:00:00"}'
```