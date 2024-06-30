# Slicing

![Slicing](../../static/images/slicing.png)

Slicing is similar to indexing, but instead of returning a single character, it returns a substring.

```python
some_words = "Heimdall is the Guardian of Asgard"
len(some_words) # 32 # this string is 32 characters long
some_words[0:4] # 'Heim'
some_words[1:33] # 'eimdall is the Guardian of Asgard'
some_words[0:13:2] # 'Hidl st' # start at index 0, stop at index 13, step by 2
```
