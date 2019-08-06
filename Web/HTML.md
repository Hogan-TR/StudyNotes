1. 元素

   ```html
   <p>...</p>                                          段落，单独一行呈现，块级元素
   <em>...</em>                                        使内容变成斜体强调，内联元素
   <strong>...</strong>                                着重强调
   <i>...</i>                                          斜体
   <b>...</b>                                          粗体
   <u>...</u>                                          下划线
   <img src="...">                                     插入指定图片
   <a href="..." title="..." target="...">...</a>      使被标签包裹的内容成为超链接
   ```

2. 元素属性

   1. 在元素和属性之间有个空格space (如果有一个或多个已存在的属性，就与前一个属性之间有一个空格)
   2. 属性后面紧跟着一个“=”符号
   3. 有一个属性值,由一对引号“ ”引起来
   4. **布尔属性**：没有值的属性，他们只能有跟它的属性名一样的属性值

3. HTML文档分析

   ```html
   <!DOCTYPE html>
   <html>
     <head>
       <meta charset="utf-8">
       <title>我的测试站点</title>
     </head>
     <body>
       <p>这是我的页面</p>
     </body>
   </html>
   ```

   ```html
   <!DOCTYPE html>                                     文档类型声明
   <html></html>                                       包裹整个完整的页面
   <head></head>                                       是一个容器，包含在搜索结果中出现的关键字和页面描述，CSS样式，字符集声明等等
   <meta charset="utf-8">                              设置文档使用utf-8字符集编码
   <title></title>                                     设置页面标题，出现在浏览器标签上，当你标记/收藏页面时它可用来描述页面
   <body></body>                                       包含了访问页面时所有显示在页面上的内容
   ```

4. HTML中的空白

   - 下方的代码片段是等价的：

       ```html
       <p>狗 狗 很 呆 萌。</p>

       <p>狗 狗        很
                呆 萌。</p>
       ```

   - 无论使用多少空白，当渲染这些代码的时候，HTML解释器会将连续出现的空白字符减少为一个单独的空格符

5. 特殊字符

   ![https://tva1.sinaimg.cn/large/0060lm7Tly1g5mk83g55kj30hz07taa5.jpg](https://tva1.sinaimg.cn/large/0060lm7Tly1g5mk83g55kj30hz07taa5.jpg)


6. 注释

   ```html
   <p>我在注释外！</p>
   
   <!-- <p>我在注释内！</p> -->
   ```

7. 分段设置语言

   ```html
   <p>Japanese example: <span lang="jp">ご飯が熱い。</span>.</p>
   ```

8. 文字处理 - 列表

   1. 无序：

       ```html
       <ul>
         <li>豆浆</li>
         <li>油条</li>
         <li>豆汁</li>
         <li>焦圈</li>
       </ul>
       ```
       
   2. 有序： 
      
      ```html
      <ol>
        <li>沿着条路走到头</li>
        <li>右转</li>
        <li>直行穿过第一个十字路口</li>
        <li>在第三个十字路口处左转</li>
        <li>继续走 300 米，学校就在你的右手边</li>
      </ol>
      ```

9. 链接 - Download属性

   - 使用 download 属性来提供一个默认的保存文件名

       ```html
       <a href="https://download.mozilla.org/?product=firefox-latest-ssl&os=win64&lang=en-US"
          download="firefox-latest-64bit-installer.exe">
         Download Latest Firefox for Windows (64-bit) (English, US)
       </a>
       ```

10. 链接 - 电子邮件链接

    形式为：mailto:link

    ```html
    <a href="mailto:nowhere@mozilla.org?cc=name2@rapidtables.com&bcc=name3@rapidtables.com&subject=The%20subject%20of%20the%20email&body=The%20body%20of%20the%20email">
      Send mail with cc, bcc, subject and body
    </a>
    ```

11. 描述列表

    ```html
    <dl>
      <dt>内心独白</dt>
        <dd>戏剧中，某个角色对自己的内心活动或感受进行念白表演，这些台词只面向观众，而其他角色不会听到。</dd>
      <dt>语言独白</dt>
        <dd>戏剧中，某个角色把自己的想法直接进行念白表演，观众和其他角色都可以听到。</dd>
      <dt>旁白</dt>
        <dd>戏剧中，为渲染幽默或戏剧性效果而进行的场景之外的补充注释念白，只面向观众，内容一般都是角色的感受、想法、以及一些背景信息等。</dd>
    </dl>
    ```

12. 缩略语

    - 元素 **abbr** - 用来包裹一个缩略语或缩写，并且提供缩写的解释（包含在`title`属性中）

    ```html
    <p>我们使用 <abbr title="超文本标记语言（Hypertext Markup Language）">HTML</abbr> 来组织网页文档。</p>
    ```

13. 上标和下标

    - 元素 <sup>(上标) 和 <sub>(下标)

    ```html
    <p>咖啡因的化学方程式是 C<sub>8</sub>H<sub>10</sub>N<sub>4</sub>O<sub>2</sub>。</p>
    <p>如果 x<sup>2</sup> 的值为 9，那么 x 的值必为 3 或 -3。</p>
    ```

14. 代码展示

    ```html
    <code>: 用于标记计算机通用代码。
    <pre>: 对保留的空格（通常是代码块）——如果您在文本中使用缩进或多余的空白，浏览器将忽略它，您将不会在呈现的页面上看到它。但是，如果您将文本包含在<pre></pre>标签中，那么空白将会以与你在文本编辑器中看到的相同的方式渲染出来。
    <var>: 用于标记具体变量名。
    <kbd>: 用于标记输入电脑的键盘（或其他类型）输入。
    <samp>: 用于标记计算机程序的输出。
    ```

    ```html
    <pre><code>const para = document.querySelector('p');
    
    para.onclick = function() {
      alert('噢，噢，噢，别点我了。');
    }</code></pre>
    
    <p>请不要使用 <code>&lt;font&gt;</code> 、 <code>&lt;center&gt;</code> 等表象元素。</p>
    
    <p>在上述的 JavaScript 示例中，<var>para</var> 表示一个段落元素。</p>
    
    
    <p>按 <kbd>Ctrl</kbd>/<kbd>Cmd</kbd> + <kbd>A</kbd> 选择全部内容。</p>
    
    <pre>$ <kbd>ping mozilla.org</kbd>
    <samp>PING mozilla.org (63.245.215.20): 56 data bytes
    64 bytes from 63.245.215.20: icmp_seq=0 ttl=40 time=158.233 ms</samp></pre>
    ```

15. 专用标签

    ```
    <header> : 页眉
    <nav> :    导航栏
    <main> :   主内容，主内容中还可以有各种子内容区段，可用<article>、<section> 和 <div> 等元素表示
    <aside> :  侧边栏，经常嵌套在 <mian> 中
    <footer> : 页脚
    ```

16. 换行与水平分割线

    ```html
    <br>        换行
    <hr>        水平分割线图片  - 语义容器
    ```

    ```html
    <figure>
      <img src="https://raw.githubusercontent.com/mdn/learning-area/master/html/multimedia-and-embedding/images-in-html/dinosaur_small.jpg"
         alt="一只恐龙头部和躯干的骨架，它有一个巨大的头，长着锋利的牙齿。"
         width="400"
         height="341">
      <figcaption>曼彻斯特大学博物馆展出的一只霸王龙的化石</figcaption>
    </figure>
    ```

    **注**： **<figure>** 可以是几张图片、一段代码、音视频、方程、表格或别的

17. 表单常用类型

    |   Type   | Function |
    | :------: | :------: |
    |   text   |  文本框  |
    | password | 密码字段 |
    |  radio   | 单选按钮 |
    | checkbox |  复选框  |
    |  submit  | 提交按钮 |

    

18. 文本格式化

    ```html
    <b>粗体文本</b>
    <code>计算机代码</code>
    <em>强调文本</em>
    <i>斜体文本</i>
    <kbd>键盘输入</kbd> 
    <pre>预格式化文本</pre>
    <small>更小的文本</small>
    <strong>重要的文本</strong>
     
    <abbr> （缩写）
    <address> （联系信息）
    <bdo> （文字方向）
    <blockquote> （从另一个源引用的部分）
    <cite> （工作的名称）
    <del> （删除的文本）
    <ins> （插入的文本）
    <sub> （下标文本）
    <sup> （上标文本）
    ```

19. Loading...