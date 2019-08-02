1. **str**与**bytes**之间的转换

   ```python
   # bytes object
   b = b"example"
   
   # str object
   s = "example"
   
   # str to bytes
   bytes(s, encoding = "utf8")
   
   # bytes to str
   str(b, encoding = "utf-8")
   
   # an alternative method
   # str to bytes
   str.encode(s)
   
   # bytes to str
   bytes.decode(b)
   ```

2. Loading...