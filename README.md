# dotdotdot
Dot-accessible python dictionaries, lists, and tuples.

## Create a dot-accessible dictionary from dict
```python
>>> from dotdotdot import DocDict
>>> d = {'query': {'match_phrase': {'message': 'test message'}}}
>>> dd = DotDict(d)
>>> dd.query.match_phrase.message
'test message'
```

## Create dot-accessible dictionary using dot-notation
```python
>>> from dotdotdot import DocDict
>>> dd = DotDict()
>>> dd.query.match_phrase.message = 'test message'
>>> dd
{'query': {'match_phrase': {'message': 'test message'}}}
```

## Accessing lists / tuples
Lists can be accessed via indexing `[1]`, or via a leading underscore `_1`.
```python
>>> dd = DotDict()
>>> dd.messages = ['test message', 'and this message', {'value': True}]
>>> dd.messages[2].value
True
>>> dd.messages._1
'and this message'
```
