1. 格式要求：**双引号**作为key或value的边界符号

2. json.loads()  ->  解码python json**格式**
   json.load()    ->  加载python json**格式文件**

3. 加载Json格式为Dict

   ```python
   import json
   a=json.loads('{"a":"1","b":"2"}')
   print a
   ```

4. Json的存数据到文件

   ```python
   import json
   info = {
   	"name":"ztr",
   	"age":"20"
   }
   with open("1.txt","w",encoding="utf-8") as f:
   	f.write(json.dumps(info))
   	
   # 此处json存数据时使用unicode的16进制格式，中文在保存文件中是\u开头
   # 当使用json.load()时会自动逆向识别，转为可读中文
   # 若想保留中文的显示，可添加参数ensure_ascii = False，文件即可保留中文
   ```

5. Json的取数据

   ```python
   import json
   with open("1.txt","r",encoding="utf-8") as f:
   	data = json.loads(f.readline())
   	print(data["age"])
   ```

6. 收藏

   ```python
   print (a[0].encode('utf-8').decode('unicode_escape'))
   ```

   