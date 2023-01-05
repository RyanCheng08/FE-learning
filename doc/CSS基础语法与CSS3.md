## 什么是CSS
- CSS（cascading style sheet，层叠式样式表）是用来给HTML标签添加样式的语言
- 作用：静态的修饰网页，并且可以配合各种脚本语言动态地对网页各元素进行格式化（修改样式）。
- 前端最基础的三层结构：

|  | 语言 | 功能 |
| --- | --- | --- |
| 结构层 | HTML | 搭建网页结构，描述语义，放置各种部件 |
| 样式层 | CSS | 美化页面，实现布局 |
| 行为层 | JavaScript | 实现交互效果、数据收发、表单验证等 |

## 为什么使用CSS

- 随着HTML标签越来越多，比如带样式的文本格式化标签等，HTML越来越杂乱，并且页面变得越臃肿，所以CSS就诞生了。
- CSS能够使我们页面的样式和结构分离开来，结构层专门搭建结构，样式层专门编写样式。
- CSS的功能很强大，可以实现很多样式。
### 发展过程
![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667203593618-e583c7e9-09de-463f-861b-a53f9ee12063.png#averageHue=%23f2f1f0&clientId=u54c8bda8-3222-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=387&id=ud6d2eacf&margin=%5Bobject%20Object%5D&name=image.png&originHeight=387&originWidth=1031&originalType=binary&ratio=1&rotation=0&showTitle=false&size=129750&status=done&style=none&taskId=u2fbb3204-208f-4360-948e-8ec56c951f6&title=&width=1031)
## CSS基本语法
### CSS的书写位置和注释
#### 内联式（行内式）

- 内联式的缺点：
   1. 内联式必须写在标签上，没有完全脱离 HTML 标签。
   2. css 样式代码让标签结构繁重，不利于 HTML 结构的解读。
   3. 一个内联式的 css 代码，只能给一个标签使用，如果多个标签有相同的样式，同样的 css 代码需要书写多次，增加代码量。
   4. 所以实际工作中不会使用内联式
```html
    <!-- 行列式是在每个具体的标签内设置样式,行列式不常使用，因为需要每个标签单独配置 -->
    <h3 style="color: red;background-color:blue">我是一个三级标题</h3>
    <h3 style="color: rgb(12, 134, 18);">我是一个三级标题</h3>
    <h3 style="color: red;background-color:blue">我是一个三级标题</h3>
```
![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1656913256416-aa3481ed-0e05-4480-a53a-a2acfb1ba986.png#averageHue=%23bbba6c&clientId=u90ec9498-6c53-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=122&id=cCfhD&margin=%5Bobject%20Object%5D&name=image.png&originHeight=122&originWidth=294&originalType=binary&ratio=1&rotation=0&showTitle=false&size=9617&status=done&style=none&taskId=ud65d6ae5-5a25-415c-bc70-2ef16752b91&title=&width=294)
#### 内嵌式

- 内嵌式特点：
   - 优点：
      - 实现了结构和样式的初步分离，css 只负责样式，HTML 负责结构。
      - 多个标签可以利用一段代码设置相同的样式，节省代码量。
   - 缺点：
      - 结构和样式并没有完全分离，代码依旧书写在 HTML 文件的<style>标签内部。
      - css 样式只能给一个 HTML 文件使用，不能够被多个 HTML 文件同时利用。
      - 在 HTML 中如果 css 代码太多，会造成文件头重脚轻。
```html
<!DOCTYPE html> 
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS的书写</title>
    <!-- 内嵌式的CSS样式设置，在HTML文件的head标签里 -->
    <style>
        h1{
            color: red;
        }
        h2{
            color: yellow;
        }
    </style>
</head>
<body>
    <h1>我是一个一级标题</h1>
    <h2>我是一个二级标题</h2>
    <h2>我是一个二级标题</h2>
    <h2>我是一个二级标题</h2>
    <h2>我是一个二级标题</h2>
</body>
</html>
```
![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1656907244618-03b75421-3895-4621-9be3-64871b2b8008.png#averageHue=%23fef5f5&clientId=u90ec9498-6c53-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=237&id=u9981b717&margin=%5Bobject%20Object%5D&name=image.png&originHeight=237&originWidth=320&originalType=binary&ratio=1&rotation=0&showTitle=false&size=14357&status=done&style=none&taskId=u36d9258c-0505-4087-9253-bcb8155f4c5&title=&width=320)

#### 外链式

- 外联式 CSS，也可以叫做外链式 CSS、外部 CSS。
- 书写位置：在一个单独的扩展名为 .css 的文件中。
- 书写语法：内部代码与内嵌式样式表中 <style> 标签内部的代码一样的。需要通过选择器去选中标签，添加对应的样式，然后在HTML代码里面添加link标签引用这个css文件。![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667204278946-74f81994-6ecf-49ab-b6db-9184de0a270b.png#averageHue=%23efeeed&clientId=u54c8bda8-3222-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=280&id=u4124f160&margin=%5Bobject%20Object%5D&name=image.png&originHeight=280&originWidth=913&originalType=binary&ratio=1&rotation=0&showTitle=false&size=71323&status=done&style=none&taskId=u916aea82-2586-4809-af4e-4c4539d2ade&title=&width=913)
- 注意：在 .css 文件中书写时，不需要再加 <style> 标签
- 优点：
   - 实现了 HTML 和 css 完全分离。
   - 多个 HTML 文件可以共用一个 css 文件，便于提取公共 css，减少代码量。
   - 可以实现一个 css 变化，多个 HTML 页面同时变化，减少工作量。
   - 一个 HTML 文件可以引入多个 css 文件，可以实现同一个页面中 css 代码分层。
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS的书写</title>
    <!-- 内嵌式的CSS样式设置，在HTML文件的head标签里 -->
    <!-- <style>
        h1{
            color: red;
        }
        h2{
            color: yellow;
        }
    </style> -->
    <!-- 外链式，外链式是由link标签来实现的，rel属性的值是stylesheet，
  		href属性的值则是css文件的路径
  	-->
    <link rel="stylesheet" href="css/css.css">
</head>
<body>
    <h1>我是一个一级标题</h1>
    <h2>我是一个二级标题</h2>
    <h2>我是一个二级标题</h2>
    <h2>我是一个二级标题</h2>
    <h2>我是一个二级标题</h2>

    <p>
        我是一个段落我是一个段落我是一个段落我是一个段落我是一个段落我是一个段落我是一个段落我是一个段落我是一个段落我是一个段落我是一个段落我是一个段落我是一个段落我是一个段落我是一个段落我是一个段落我是一个段落我是一个段落
    </p>
</body>
</html>
```
![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1656913345525-d339f1ed-3252-4689-89e0-f3e5d786278e.png#averageHue=%23fcd289&clientId=u90ec9498-6c53-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=79&id=u8fbd7b1d&margin=%5Bobject%20Object%5D&name=image.png&originHeight=79&originWidth=1357&originalType=binary&ratio=1&rotation=0&showTitle=false&size=10056&status=done&style=none&taskId=u5ceb184c-c6c6-4c60-b893-9391133f3dd&title=&width=1357)
#### 导入式

- 书写位置：在内嵌式样式表 <style> 标签内部，或者在外联式样式表内部，导入其他的外部的 .css 文件。
- 导入方式：利用一条 @import url(路径) 语句进行引入。
  ![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667204435777-d438c7e4-d5c0-4428-9e17-fc8cc9610824.png#averageHue=%23282d36&clientId=u54c8bda8-3222-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=242&id=u57622d17&margin=%5Bobject%20Object%5D&name=image.png&originHeight=242&originWidth=394&originalType=binary&ratio=1&rotation=0&showTitle=false&size=62268&status=done&style=none&taskId=u24947580-60ad-47ae-bf27-b447cf5cda7&title=&width=394)
- 导入式问题：![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667204454768-c39175f1-2e8b-43a6-a66b-f85e7cad433a.png#averageHue=%23434852&clientId=u54c8bda8-3222-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=252&id=u9603ecd8&margin=%5Bobject%20Object%5D&name=image.png&originHeight=252&originWidth=1126&originalType=binary&ratio=1&rotation=0&showTitle=false&size=71098&status=done&style=none&taskId=u250fb437-2d32-4973-8402-9a93cbdcbee&title=&width=1126)
#### 实际应用

- 小型案例：使用内嵌式CSS
- 实际工作、大型网站项目：使用外链式CSS
### 基本书写规则<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667204669018-a179bdbe-4da7-43b4-81fa-57c416cd9aac.png#averageHue=%23282a21&clientId=u54c8bda8-3222-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=269&id=u83cf1fe1&margin=%5Bobject%20Object%5D&name=image.png&originHeight=269&originWidth=1106&originalType=binary&ratio=1&rotation=0&showTitle=false&size=142286&status=done&style=none&taskId=u9944f215-cedb-4937-840a-343b45b96f6&title=&width=1106)

1. 所有的 css 代码都必须书写在 <head> 标签内部的一对 <style> 标签内。
2. css 在给某个标签设置样式前，必须使用选择器先选中标签。
3. css 样式的属性，属性名和属性值的键值对写法为 k:v; 。
4. 给每个选择器添加的样式属性都必须写在一对大括号 {} 之内。
5. 给一个标签添加的所有需要的样式，都要在 {} 内部一一罗列出来
6. css的编写由各种选择器和样式表组成。
7. 首先指定需要编写样式的选择器，比如标签选择器h1、h2、p等，然后在大括号中用k:v的方式来编写样式列表。
8. 最后一条样式可以不书写分号。
9. 多个选择器之间不需要用符号隔开。
10. css 中所有属性与属性之间对空格、换行、缩进不敏感。

### CSS注释语法

- 语法格式：
  	/*中间部分为注释内容 */
- vs code快捷键：ctrl+/
```css
p{
    /* CSS 的注释 */
    color:green;
    background-color: orange;
}
```
### CSS 样式格式

- 展开格式：开发过程使用，代码可读性强，便于调错。<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667204836313-ffa542ca-99fb-4f25-ace1-371786b6b175.png#averageHue=%23282e38&clientId=u54c8bda8-3222-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=206&id=uac5ab7b1&margin=%5Bobject%20Object%5D&name=image.png&originHeight=206&originWidth=413&originalType=binary&ratio=1&rotation=0&showTitle=false&size=63873&status=done&style=none&taskId=uc99c8414-d511-4cb4-8448-f2edad142c8&title=&width=413)
- 紧凑格式：上传服务器时使用，减少不必要的空白字符，压缩文件大小，利于传输。<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667204846105-dae74b31-5d74-4a12-986e-42f427083db6.png#averageHue=%23292e38&clientId=u54c8bda8-3222-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=85&id=u3a4c3b1a&margin=%5Bobject%20Object%5D&name=image.png&originHeight=85&originWidth=796&originalType=binary&ratio=1&rotation=0&showTitle=false&size=49589&status=done&style=none&taskId=ude892a9f-29c7-4ff1-ae1a-e545ba39d88&title=&width=796)
### 英文大小写

- CSS 中的英文可以使用大写，也可以使用小写。
- 建议：css 中的选择器和样式属性名、属性值等都使用小写英文，特殊情况除外。
### 空格规范

- 选择器与大括号 {} 之间保留一个空格。
- 冒号后面，属性值前面，保留一个空格。
## CSS选择器
CSS2.1的选择器有7种选择器

- 基本选择器：标签选择器、id 选择器、类选择器、通配符选择器（*，选择所有标签）。
- 高级选择器：后代选择器、交集选择器、并集选择器。
### 标签选择器

- 标签选择器也称元素选择器，直接使用标签的名字当作选择器，将会选择页面上的所有该标签应用样式，无论这个标签所处位置的深浅。
- 标签选择器“覆盖面”非常大，所以通常用于标签的初始化。
- 所有span标签都应用了样式，颜色变为了红色![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1657020354748-9251aeb5-a574-4570-9930-44ac688cd3e9.png#averageHue=%23fbf9f7&clientId=u82ffecd6-0d55-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=130&id=ua6f114af&margin=%5Bobject%20Object%5D&name=image.png&originHeight=143&originWidth=1045&originalType=binary&ratio=1&rotation=0&showTitle=false&size=14164&status=done&style=none&taskId=u69cb529e-8abf-4a98-a4e0-f8c2f6a211c&title=&width=949.999979409305)
- 缺点是不能对局部的标签添加特殊样式。
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>CSS选择器学习</title>
    <style>
        span{
            color: red
        }

        /* 初始化标签 */
        /* 去掉无序列表的小圆点 */
        ul{
            list-style: none
        }

        /* 去掉超链接的下划线 */
        a{
             text-decoration:none 
        }
    </style>
</head>
<body>
    <div>
        <p>
            我是一个段落标签<span>这是一span标签包裹的文字</span>
        </p>
        <div>
            <ul>
                <li>
                    广东省广州市<span>天河区</span>
                    <p>
                        天河区是广州经济<span>最发达的地方</span>，因为广州的<span>CBD</span>在天河。
                        广州图书馆也在天河，就在广州的CBD，广图的网址是:
                        <a href="http://www.gzlib.org.cn" target="blank">www.gzlib.org.cn</a>
                    </p>
                </li>
                
            </ul>
        </div>
    </div>
</body>
</html>
```
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    p {
      color: red;
    }
    h3 {
      color: green;
    }
  </style>
</head>
<body>
  <h3>三级标题标签内容</h3>
  <p>段落标签内容</p>
  <p>段落标签内容</p>
  <h3>三级标题标签内容</h3>
  <p>段落标签内容</p>
  <p>段落标签内容</p>
  <h3>三级标题标签内容</h3>
  <p>段落标签内容</p>
  <p>段落标签内容</p>
  <div>
    <div>
      <div>
        <div>
          <div>
            <p>这是一个嵌套很深的段落</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</body>
</html>
```
### id选择器

- 每个标签都有id属性，属性的值是唯一的，是这个标签的唯一标识，同一个页面上不能有相同的id的标签。
- id的名称只能由**字母、数字、下划线、短横**构成，且不能以数字开头，字母区分大小写，但习惯上一般为小写字母。
- 缺点：id 选择器只能实现单选，不能帮我们完成多选的功能。![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1657030980469-6a969b95-eb07-4a2a-ad8b-14f0f5a08648.png#averageHue=%23fdf4ea&clientId=u82ffecd6-0d55-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=79&id=ud3e9462f&margin=%5Bobject%20Object%5D&name=image.png&originHeight=87&originWidth=1101&originalType=binary&ratio=1&rotation=0&showTitle=false&size=15938&status=done&style=none&taskId=ua088311a-868b-419f-bf57-93259099d16&title=&width=1000.909069214971)
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>id选择器学习</title>
    <style>
        /* id选择器由#号+id构成 */
        #div1{
            background-color: bisque;
        }
        /* id的命名不可以用数字开头，但是可以用下划线开头 */
        #_div{
            background-color:chartreuse;
        }

        span{
            color:red;
        }

        #span1{
            font-weight: bold;
        }

        #span2{
            font-style:oblique
        }
        /* 虽然说id选择器在有多个id的情况下还能正常使用，但是这不符合编写规范 */
        #p_1{
            color:darkmagenta
        }

        /* 后面写的样式会覆盖掉前面的样式，不过一般不要写重复的样式，减少代码冗余 */
        #span3{
            color:darkturquoise
        }

    </style>
</head>
<body>
    <div id="div1">
        <p id="p_1">
            广东梅州是世界客都，生活在哪里的人都是客家人，客家人经历了<span id="span1">5次迁徙</span>，最终形成了现在的分布，客家人<span id="span2">都是汉族</span>，并不是什么少数民族。
        </p>
    </div>

    <div id="_div">
        <p id="p_1">
            广东省最主要的方言是<span id="span3">粤语、客家话以及潮汕话</span>，并不是所有广东人都是说粤语的。
        </p>
    </div>
</body>
</html>
```
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    #para1 {
      color: red;
    }
    #para2 {
      color: red;
    }
  </style>
</head>
<body>
  <h3>三级标题标签内容</h3>
  <p>段落标签内容</p>
  <p>段落标签内容</p>
  <h3>三级标题标签内容</h3>
  <p id="para1">段落标签内容</p>
  <p id="para2">段落标签内容</p>
  <h3>三级标题标签内容</h3>
  <p>段落标签内容</p>
  <p>段落标签内容</p>
</body>
</html>
```
### class选择器

- class属性表示类名，类名的命名规范和id的命名规范相同。
- class选择器由. + 类名构成
- 与id不同的是，多个标签可以有相同的类名，单个标签也可以有多个类名，多个类名之间用空格隔开。
- 优点：
   - 通过一个类选择器进行多选，选中多个标签，添加公共样式。
   - 一个标签可以被多个类选择器选中，可以将所有样式进行分离，分别提取公共样式和单独样式，节省代码量。
   - 实际工作中，通常我们有一个使用规律：类上样式(CSS)，id 上行为(JavaScript)![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1657031630325-c4cca41b-5ff5-46c3-b1e4-f057c2e6d0a5.png#averageHue=%23feefe1&clientId=u82ffecd6-0d55-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=82&id=ufb4b30bb&margin=%5Bobject%20Object%5D&name=image.png&originHeight=90&originWidth=1087&originalType=binary&ratio=1&rotation=0&showTitle=false&size=17875&status=done&style=none&taskId=u94571395-6d82-41c9-93a3-2dd70545dca&title=&width=988.1817967635545)
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>class（类)选择器</title>
    <style>
        /* 类选择器由.号+类名构成 */
        .div1{
            background-color: bisque;
        }
        /* class的命名不可以用数字开头，但是可以用下划线开头 */

        span{
            color:red;
        }

        .span-strong{
            font-weight: bold;
        }

        .span-oblique{
            font-style:oblique
        }
        /* 多个标签可以使用同一个类 */
        .p_1{
            color:darkmagenta
        }

    </style>
</head>
<body>
    <div class="div1">
        <p class="p_1">
            <!-- 一个标签可以有多个class属性值 -->
            广东梅州是世界客都，生活在哪里的人都是客家人，客家人经历了<span class="span-strong span-oblique">5次迁徙</span>，最终形成了现在的分布，客家人<span class="span-strong">都是汉族</span>，并不是什么少数民族。
        </p>
    </div>

    <div class="div1">
        <p class="p_1">
            广东省最主要的方言是<span class="span-strong span-oblique">粤语、客家话以及潮汕话</span>，并不是所有广东人都是说粤语的。
        </p>
    </div>
</body>
</html>
```
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    .demo {
      color: red;
    }
    .ps {
      font-size: 30px;
    }
  </style>
</head>
<body>
  <h3 class="demo">三级标题标签内容</h3>
  <p class="demo ps">段落标签内容</p>
  <p class="demo">段落标签内容</p>
  <h3>三级标题标签内容</h3>
  <p>段落标签内容</p>
  <p>段落标签内容</p>
  <h3>三级标题标签内容</h3>
  <p>段落标签内容</p>
  <p>段落标签内容</p>
</body>
</html>
```
##### 原子类

- 在做网页项目前，可以将所有的常用字号、文字颜色、行高、外边距、内边距等都设置为单独的类，需要用到的时候就可以直接拿出来使用了。<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1657186750862-94898710-f7d5-4faf-bb78-0a097376a9f4.png#averageHue=%23fefbf7&clientId=u5f7b9d3e-e89c-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=199&id=u30ce6835&margin=%5Bobject%20Object%5D&name=image.png&originHeight=199&originWidth=294&originalType=binary&ratio=1&rotation=0&showTitle=false&size=11688&status=done&style=none&taskId=ub5071ee4-03e5-4233-a677-6373cf228b5&title=&width=294)
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>选择器练习-原子类</title>
    <style>
        .color_blue{
            color: blue;
        }

        .color_pink{
            color:pink;
        }

        .color_green{
            color: green;
        }

        .color_red{
            color: red;
        }
        
        .color_orange{
            color: orange;
        }

        .font_size14{
            font-size: 14px;
        }

        .font_size18{
            font-size: 18px;
        }
    </style>
</head>
<body>
    <p class="font_size18 color_blue">我是一个p标签，我的字体是18</p>
    <p class="font_size14 color_pink">我是一个p标签，我的字体是14</p>
    <p class="font_size18 color_green">我是一个p标签，我的字体是18</p>
    <p class="font_size14 color_red">我是一个p标签，我的字体是14</p>
    <p class="font_size18 color_orange">我是一个p标签，我的字体是18</p>
    
</body>
</html>
```
#### 指定属性或者属性值的选择器
| 举例 | 意义 |
| --- | --- |
| img[alt] | 选择有alt属性的img标签 |
| img[alt="广州塔"] | 选择alt属性为广州塔的img标签 |
| img[alt^="CBD"] | 选择alt属性是以CBD开头的img标签 |
| img[alt$="夜游"] | 选择alt属性以夜游结尾的img标签 |
| img[alt*="吃"] | 选择alt属性中含有吃字的img标签 |
| img[alt~="王宫"] | <br />1. 选择alt属性中有2边都用空格隔开的王宫字样<br />2. 王宫是属性值最后的字符串且王宫前面有空格<br /> |
| img[alt&#124;="广州特色"] | 选择alt属性以“广州特色-”开头的img标签，注意是有符号-的 |

![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1657161154303-f0224eef-0ec5-4285-bc13-c8f4203b4145.png#averageHue=%239e814b&clientId=u7098b3b9-ddbb-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=292&id=ud92384c7&margin=%5Bobject%20Object%5D&name=image.png&originHeight=292&originWidth=1249&originalType=binary&ratio=1&rotation=0&showTitle=false&size=362269&status=done&style=none&taskId=ua2bb8126-2530-4c29-a3c5-34920f866ad&title=&width=1249)
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>属性选择器</title>
    <style>
        /* 给图片标签加上边框 */
        img{
            border: 1px solid;
            width: 200px;
        }

        /* 选择有选择有alt属性的img标签 */
        img[alt]{
            border:4px solid red;
        }

        /* alt属性值为广州塔 */
        img[alt="广州塔"]{
            border:10px double blue
        }

        /* alt属性以CBD开头 */
        img[alt^="CBD"]{
            border:10px outset green
        }

        /* alt属性以夜游结尾 */
        img[alt$="夜游"]{
            border: 10px dotted yellow;
        }

        /* alt属性含有吃 */
        img[alt*="吃"]{
            border:10px rebeccapurple dashed
        }

        /* alt属性值里有2边都用空格隔开的王宫 */
        img[alt~="王宫"]{
            border: 10px groove gold;
        }

        /* alt属性以广州特色-开头的img标签 */
        img[alt|="广州特色"]{
            border:10px brown;
            border-style: dashed solid;
        }

    </style>
</head>
<body>

    <img src="images/九寨沟.jpg" >
    <img src="images/广州塔.jpg" alt="广州塔">
    <img src="images/广州CBD大厦.jpg" alt="CBD大厦">
    <img src="images/珠江夜游.jpg" alt="珠江夜游">
    <img src="images/广州早茶.jpg" alt="早茶吃的点心">
    <img src="images/广州南越王宫博物馆.jpg" alt="南越 王宫 博物馆">     
    <img src="images/广州珠江.jpg" alt="广州特色珠江">
    <img src="images/广州镇海楼.jpg" alt="广州特色-镇海楼">
    
    
</body>
</html>
```
### 复合选择器
#### 后代选择器

- 通过标签之间存在的嵌套关系去选择元素，基本组成部分就是基础选择器。
- CSS选择器中，使用空格表示“后代”，会将前面那个选择器中的所有后面选择器选择的标签都应用样式，不仅仅是子标签。
- 可以使用很多个空格隔开好几代来选择<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1657033409571-28003055-562d-484f-a973-0a676b46f1cf.png#averageHue=%23faf4f2&clientId=u6ed55435-479e-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=340&id=ua9ca3f45&margin=%5Bobject%20Object%5D&name=image.png&originHeight=374&originWidth=315&originalType=binary&ratio=1&rotation=0&showTitle=false&size=15684&status=done&style=none&taskId=uc9f39e26-2fcb-4690-b271-337ee2e35e1&title=&width=286.36363015687186)![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667206902062-8169caf6-9c85-4c06-9b52-7de864503006.png#averageHue=%23fcfbfa&clientId=u54c8bda8-3222-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=502&id=ua1b89353&margin=%5Bobject%20Object%5D&name=image.png&originHeight=502&originWidth=607&originalType=binary&ratio=1&rotation=0&showTitle=false&size=31321&status=done&style=none&taskId=uaa79094f-fbdf-41f3-9429-2b482762511&title=&width=607)
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>后代选择器</title>

    <style>
        /* 寻找类名first-div的后代类名em，可以看出来em不是子标签，而是孙子标签 */
        .first-div .em{
            font-weight: bolder;
            color: red;
        }

        /* 后代选择器可以是类名、标签也可以是id选择器 */
        .first-div ul{
            list-style:none
        }

        .second-div #para-x{
            color: orange
        }

        .second-div .italic{
            font-style: italic
        }

        .second-div .oblique{
            font-style: oblique
        }

        .second-div .oltag{
            color: aqua
        }

        .second-div .oltag-p{
            color: blue
        }
      
    </style>
</head>

<body>
    <div class="first-div">
        <ul>
            <li>这是一个<span class="em">这是一无序列表项</span></li>
            <li>这是一个<span class="em">这是一无序列表项</span></li>
            <li>这是一个<span class="em">这是一无序列表项</span></li>

            <li>
                <p class="first-p">我是一个在列表项里的段落</p>

            </li>
        </ul>
    </div>

    <div class="second-div">
        <ol>
            <li>这是一个<span class="italic">有序列表项</span></li>
            <li>这是一个<span class="oblique oltag">有序列表项</span></li>
            <li>这是一个<span class="oltag">有序列表项</span></li>

            <li>
                <p>我是一个在<span class=" oltag-p">有序列表项</span>里的段落</p>

                <p id="para-x">我是一个特殊的段落</p>
                <p>我是段落</p>
                <p>我是段落</p>

            </li>
        </ol>

    </div>
</body>
</html>
```
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    /* .box1 ul li p {
      color: red;
    } */
    .box1 p {
      color: green;      
    }
  </style>
</head>
<body>
  <div class="box1">
    <ul>
      <li><p>这是 box1 标签中 li 标签内部的段落</p></li>
      <li><p>这是 box1 标签中 li 标签内部的段落</p></li>
      <li><p>这是 box1 标签中 li 标签内部的段落</p></li>
      <li><p>这是 box1 标签中 li 标签内部的段落</p></li>
    </ul>
    <p>这是 box1 标签内部的段落</p>
  </div>
  <div class="box2">
    <ul>
      <li><p>这是 box2 标签中 li 标签内部的段落</p></li>0
      <li><p>这是 box2 标签中 li 标签内部的段落</p></li>
      <li><p>这是 box2 标签中 li 标签内部的段落</p></li>
      <li><p>这是 box2 标签中 li 标签内部的段落</p></li>
    </ul>
    <p>这是 box2 标签内部的段落</p>
  </div>

</body>
</html>
```
#### 交并集选择器

- 交集选择器表示是在某个标签里面的某个标签，比如div标签里的p标签或者某个类某个id里面的某个选择器。
- 并集选择器是2个选择器应用同一个样式。<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1657036678060-fb95443a-66ef-4fc0-b640-f94692db28ff.png#averageHue=%23f7f5f3&clientId=u722068b6-fe15-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=689&id=ue432a605&margin=%5Bobject%20Object%5D&name=image.png&originHeight=758&originWidth=362&originalType=binary&ratio=1&rotation=0&showTitle=false&size=28042&status=done&style=none&taskId=u0159e75d-d448-4fd5-8c06-10292493c0d&title=&width=329.0909019580559)![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667206922642-ff17870e-9fe2-4fe8-b2da-5ce51877c712.png#averageHue=%23f7f5f3&clientId=u54c8bda8-3222-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=444&id=ue6d1b6e1&margin=%5Bobject%20Object%5D&name=image.png&originHeight=444&originWidth=452&originalType=binary&ratio=1&rotation=0&showTitle=false&size=31978&status=done&style=none&taskId=u6d3fba5e-c633-4c37-a2a3-60f3268eda6&title=&width=452)
- ![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667207012494-77d2571d-e800-4cc6-9ea5-46d144083615.png#averageHue=%23eae6e1&clientId=u54c8bda8-3222-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=153&id=u1e49a842&margin=%5Bobject%20Object%5D&name=image.png&originHeight=153&originWidth=320&originalType=binary&ratio=1&rotation=0&showTitle=false&size=8189&status=done&style=none&taskId=u44e0b7a3-4f3c-4248-90ed-6f702966de1&title=&width=320)
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>交并集选择器</title>

    <style>
        /* 某2个标签具有相同类名的时候可以使用交集选择器选中特定的一个类应用样式 */
        p.spec{
            font-weight: bold;
            color: red
            
        }

         /*某2个标签，例如ul标签和ol标签应用同一个样式，2个选择器用,号隔开  */
         ol,ul{
             list-style: none;
         }
    </style>
</head>
<body>
    <div class="div1">
        <p>我是一个div1里的段落</p>
        <p>我是一个div1里的段落</p>
        <p><span class="spec">我是一个div1里的段落</span></p>
        <p>我是一个div1里的段落</p>
        <p>我是一个div1里的段落</p>
        <p>我是一个div1里的段落</p>
        <p>我是一个div1里的段落</p>

    </div>

    <section class="div2">
        <p>这是一个div2的段落</p>
        <p>这是一个div2的段落</p>
        <p class="spec">这是一个div2的段落</p>
        <p>这是一个div2的段落</p>
        <p>这是一个div2的段落</p>
        <p>这是一个div2的段落</p>
    </section>

    <div>
        <ul>
            <li>这是一个无序列表</li>
            <li>这是一个无序列表</li>
            <li>这是一个无序列表</li>
            <li>这是一个无序列表</li>
            <li>这是一个无序列表</li>
            <li>这是一个无序列表</li>
        </ul>

        <ol>
            <li>这是一个有序列表</li>
            <li>这是一个有序列表</li>
            <li>这是一个有序列表</li>
            <li>这是一个有序列表</li>
            <li>这是一个有序列表</li>
        </ol>
    </div>
</body>
</html>
```
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    /* p.ps.demo {
      color: red;
    } */
    .box1 p.demo {
      color: green;
    }
  </style>
</head>
<body>
  <h2 class="demo">这是一个二级标题</h2>
  <div class="box1">
    <ul>
      <li><p>这是 box1 标签中 li 标签内部的段落</p></li>
      <li><p class="demo ps">这是 box1 标签中 li 标签内部的段落</p></li>
      <li><p>这是 box1 标签中 li 标签内部的段落</p></li>
      <li><p>这是 box1 标签中 li 标签内部的段落</p></li>
    </ul>
    <p>这是 box1 标签内部的段落</p>
  </div>
  <div class="box2">
    <ul>
      <li><p>这是 box2 标签中 li 标签内部的段落</p></li>
      <li><p class="demo">这是 box2 标签中 li 标签内部的段落</p></li>
      <li><p>这是 box2 标签中 li 标签内部的段落</p></li>
      <li><p>这是 box2 标签中 li 标签内部的段落</p></li>
    </ul>
    <p>这是 box2 标签内部的段落</p>
  </div>

</body>
</html>
```
并集：
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    /* h2 {
      color: red;
    }
    .demo {
      color: red;
    } */
    /* h2,.demo {
      color: red;
    } */
    body,h2,div,ul,li,p {
      margin: 0;
      padding: 0;
    }
  </style>
</head>
<body>
  <h2>这是一个二级标题</h2>
  <div class="box1">
    <ul>
      <li><p>这是 box1 标签中 li 标签内部的段落</p></li>
      <li><p class="demo">这是 box1 标签中 li 标签内部的段落</p></li>
      <li><p>这是 box1 标签中 li 标签内部的段落</p></li>
      <li><p>这是 box1 标签中 li 标签内部的段落</p></li>
    </ul>
    <p>这是 box1 标签内部的段落</p>
  </div>

</body>
</html>
```
### 伪类选择器

- 伪类是添加到选择器上的特定状态的描述，指定要选择的元素的特殊状态。查看标准伪类索引可以访问这个地址（[标准伪类索引](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Pseudo-classes#%E6%A0%87%E5%87%86%E4%BC%AA%E7%B1%BB%E7%B4%A2%E5%BC%95)）
- 超链接有4个特殊状态
| 伪类 | 意义 |
| --- | --- |
| a:link | 超链接还没有被访问的状态 |
| a:visited | 超链接被访问了的状态 |
| a:hover | 悬浮在超链接文本的时候的状态 |
| a:active | 点击超链接还没有松开时的状态 |

- 四个状态如果需要都编写，有严格的顺序：link>visited>hover>active，因为层叠的原因，后面的放前面原来前面的就不会不显示，举个例子如果visited放前面，后面的link会层叠掉visited设置的样式。

没松开时![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1657088262944-6cffb9f1-7ebe-4b86-b6a6-7e8268494431.png#averageHue=%23fffcfc&clientId=uab3bcd56-f6ff-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=231&id=u919952ec&margin=%5Bobject%20Object%5D&name=image.png&originHeight=231&originWidth=198&originalType=binary&ratio=1&rotation=0&showTitle=false&size=7426&status=done&style=none&taskId=ub2f30782-f051-4cad-aff9-9ce709b5f75&title=&width=198)悬浮![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1657088240982-c2d7d73b-81d7-4aec-a9e7-372eeaa5b022.png#averageHue=%23fefcfc&clientId=uab3bcd56-f6ff-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=189&id=u42749383&margin=%5Bobject%20Object%5D&name=image.png&originHeight=189&originWidth=210&originalType=binary&ratio=1&rotation=0&showTitle=false&size=5709&status=done&style=none&taskId=u59f43345-3278-4d07-8e76-58aaa7d52c2&title=&width=210)
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>伪类选择器学习</title>
    <style>
        /* 未访问前的状态 */
        a:link{
            color: blueviolet;
        }
        /* 访问后的状态 */
        a:visited{
            color: tomato;
        }
        /*鼠标悬浮在超链接的状态*/
        a:hover{
            font-size: 50px;
            color: violet;
        }
        /* 鼠标按住超链接没松开时 */
        a:active{
            font-size: 100px;
            color: greenyellow;
        }
    </style>
</head>
<body>
    <p><a href="http://www.baidu.com">百度一下，你就知道</a></p>
    <p><a href="http://www.gzlib.org.cn">广州图书馆</a></p>
    <p><a href="http://www.yuque.com">语雀</a></p>
    <p><a href="http://www.bilibili.com">小破站</a></p>
</body>
</html>
```
#### CSS3新增伪类
| 伪类 | 意义 |
| --- | --- |
| :empty | 选择空标签（标签里没有内容） |
| :focus | 选择当前获得焦点的表单元素 |
| :enabled | 选择当前可以编辑的表单元素 |
| :disabled | 选择当前不可以编辑的表单元素 |
| :checked | 选择当前已勾选的单选框或者复选框 |
| :root | 选择根元素，即html标签 |

![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1657163643263-df0ed498-b32f-4089-bda3-6079281d5881.png#averageHue=%235d3e96&clientId=u7098b3b9-ddbb-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=351&id=u707fb4c3&margin=%5Bobject%20Object%5D&name=image.png&originHeight=351&originWidth=532&originalType=binary&ratio=1&rotation=0&showTitle=false&size=9401&status=done&style=none&taskId=u463ae8d7-c981-401c-9196-7b21d52aa9c&title=&width=532)
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS3新增伪类学习</title>
    <style>
        /* 选择空标签 */
        .box>p{
            border:10px solid red 
        }
        p:empty{
            border-color: green;
        }

        /* 选择当前获取焦点的表单元素 */
        input:focus{
           border: 10px dashed gold;
        }

        /* 选择当前可编辑的表单元素 */
        input:enabled{
            background-color: greenyellow;
        }

        /* 选择当前不可编辑的表单元素，背景颜色为灰色 */
        input:disabled{
            border: 10px dotted black;
            background-color: grey  ;
        }

        /* 选择当前已经勾选的单选框或者复选框，变红，边框大小改变 */
        input:checked+span{
            color: red;
            border: 10px solid;
        }

        /* 选择根元素，即<html> 把背景颜色变成粉红色，还可以设置css全局变量*/
        :root{
            --main-color: hotpink;
            --pane-padding: 5px 42px;
            background-color: hotpink;
        }
    </style>
</head>

<body>
    <div class="box">
        <p></p>
        <p>我不是空标签</p>
        <!-- 有空格或者回车也不是空标签 -->
        <p> </p>
    </div>

    <div>

        <p>
            <input type="text">
            <input type="text" disabled>
        </p>
        
        <p>
            <input type="checkbox"> <span>篮球</span>
            <input type="checkbox"> <span>足球</span>
            <label><input type="radio" name="sex"><span>男</span></label>
            <label><input type="radio" name="sex"><span>女</span></label>
        </p>
        


    </div>
</body>
</html>
```
#### 伪元素

- 伪元素表现得是像你往标记文本中加入全新的 HTML 元素一样，而不是向现有的元素上应用类。伪元素开头为双冒号::
##### 特殊的伪元素::before和::after

- ::before表示的是在匹配元素之前创建一个内容，而after是在之后，一般用来在页面上引入图片。
- ::before和::after伪元素与content属性的共同使用，在 CSS 中被叫做“生成内容”
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>伪元素学习</title>
    <style>
        div{
            border:1px solid black
        }
        /* 块级元素p的第一行应用样式，字体大小变粗，颜色变成goldenrod */
        p::first-line{
            font-size: large;
            color: goldenrod;
        }
       /* 第一个字母大写,颜色为绿黄色 */
        .first-em::first-letter{
            text-transform: uppercase;
            color:greenyellow
        }

        /* 改变选中文字的颜色 */
        .select::selection{
            color: violet;
        }

        /* 在span标签前后加上content的内容，可以是文字也可以是颜文字，可以通过css来绘制图片 */
        .welcome::before{
            content: "❥(^_-)";
        }

        .welcome::after{
            content: "ヾ(◍°∇°◍)ﾉﾞ";
        }
    </style>
</head>
<body>
    <!-- <div>
        <h2>伪元素::first-letter和::first-line</h2>
        <p class="select first-em">Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore.Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore.Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore.Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore.Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore.Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore.Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore.
        </p>-->

        <!-- 只有在块级元素例如div、p里才可以使用这2个伪元素 -->
        <!--<span class="first-em">i am very favorite to learn CSS3</span>

        <p class="first-em">i am very favorite to learn CSS3</p>
    </div> -->
    
    <div>
        <span class="welcome">热烈欢迎</span>
    </div>
    
</body>
</html>
```
![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1657180133034-9a191d30-905c-43ff-b3cd-18bc75f3c9a7.png#averageHue=%23d2d1cf&clientId=u5f7b9d3e-e89c-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=40&id=ub2cd9f78&margin=%5Bobject%20Object%5D&name=image.png&originHeight=40&originWidth=350&originalType=binary&ratio=1&rotation=0&showTitle=false&size=2614&status=done&style=none&taskId=u38fa11d4-1668-4f04-b9f0-cc2a3cc3d82&title=&width=350)
##### ::selection

- ::selection伪元素应用于文档中被用户高亮的部分（比如使用鼠标或其他选择设备选中的部分）
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>伪元素学习</title>
    <style>
        div{
            border:1px solid black
        }
        /* 块级元素p的第一行应用样式，字体大小变粗，颜色变成goldenrod */
        p::first-line{
            font-size: large;
            color: goldenrod;
        }
       /* 第一个字母大写,颜色为绿黄色 */
        .first-em::first-letter{
            text-transform: uppercase;
            color:greenyellow
        }

        /* 改变选中文字的颜色 */
        .select::selection{
            color: violet;
        }
    </style>
</head>
<body>
    <div>
        <h2>伪元素::first-letter和::first-line</h2>
        <p class="select first-em">Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore.Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore.Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore.Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore.Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore.Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore.Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore.
        </p>

        <!-- 只有在块级元素例如div、p里才可以使用这2个伪元素 -->
        <span class="first-em">i am very favorite to learn CSS3</span>

        <p class="first-em">i am very favorite to learn CSS3</p>
    </div>
    
    <div>
        
    </div>
    
</body>
</html>
```
![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1657179684930-a571f594-7689-42e8-86fb-6cb211fa8500.png#averageHue=%23fdfaf5&clientId=u5f7b9d3e-e89c-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=115&id=u0533c8b9&margin=%5Bobject%20Object%5D&name=image.png&originHeight=115&originWidth=1347&originalType=binary&ratio=1&rotation=0&showTitle=false&size=22303&status=done&style=none&taskId=u2575d71d-1fe9-4254-9128-90e18604cce&title=&width=1347)
##### ::first-letter和::first-line

- ::first-letter会选中某 块级元素(display为block的元素）第一行的第一个字母，并且文字所处的行之前没有其他内容（如图片和内联的表格）
- 在某 [block-level element](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Visual_formatting_model#Block-level_elements_and_block_boxes) （块级元素）的第一行应用样式。第一行的长度取决于很多因素，包括元素宽度，文档宽度和文本的文字大小。
- first-line可以用来修改文章第一行文字的大小、粗细等样式，first-letter则可以让首字母大写
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>伪元素学习</title>
    <style>
        div{
            border:1px solid black
        }
        p::first-line{
            font-size: large;
            color: goldenrod;
        }
       
        .first-em::first-letter{
            text-transform: uppercase;
            color:greenyellow
        }
    </style>
</head>
<body>
    <div>
        <h2>伪元素::first-letter和::first-line</h2>
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore.Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore.Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore.Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore.Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore.Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore.Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore.
        </p>

        <!-- 只有在块级元素例如div、p里才可以使用这2个伪元素 -->
        <span class="first-em">i am very favorite to learn CSS3</span>

        <p class="first-em">i am very favorite to learn CSS3</p>
    </div>
    
    <div>
        
    </div>
    
</body>
</html>
```
![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1657179659092-6ad84884-3765-4e5b-91a9-725deb70f219.png#averageHue=%23f6eee5&clientId=u5f7b9d3e-e89c-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=89&id=u984d022b&margin=%5Bobject%20Object%5D&name=image.png&originHeight=89&originWidth=1348&originalType=binary&ratio=1&rotation=0&showTitle=false&size=18893&status=done&style=none&taskId=ud928c7c0-be43-4d73-a6ea-1c4c9426d9a&title=&width=1348)
### 元素（标签）关系选择器
| 名称 | 举例 | 意义 |
| --- | --- | --- |
| 子选择器 | div>p | div标签的子标签p，只能是子标签，不能是别的后代标签 |
| 相邻兄弟选择器 | img+p | 紧跟着img标签的p标签 |
| 通用兄弟选择器 | h3~p | h3标签之后所有同层级的p标签 |

#### 子选择器<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1657093630613-4ed9be88-a49d-42c6-a0ba-62a6166a8a8a.png#averageHue=%23fdfbfb&clientId=uab3bcd56-f6ff-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=265&id=udbd94ee0&margin=%5Bobject%20Object%5D&name=image.png&originHeight=265&originWidth=315&originalType=binary&ratio=1&rotation=0&showTitle=false&size=13131&status=done&style=none&taskId=u44f25d72-8374-4196-8794-910e327888f&title=&width=315)
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>子选择器学习</title>

    <style>
        /* 子关系选择器，只选中.div类的子标签p */
        .div1>p{
            color: red;
        }
        /* 可以使用多个子关系选择器符号来递进选择 */
        .div1>p>span{
            color: yellowgreen;
            font-size: 100px;
        }

    </style>
</head>
<body>
    <div class="div1"> 
        <p>我是一个段落</p>
        <p>我是一个<span>段落</span>段落</p>
        <div>
            <p>我是一个段落</p>
            <p>我是一个<span>段落</span></p>
            <p>我是一个段落</p>
        </div>
            
    </div>
</body>
</html>
```
#### 相邻兄弟选择器<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1657093645279-25b69236-b249-4da0-befc-7fd2f2740140.png#averageHue=%23b59251&clientId=uab3bcd56-f6ff-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=250&id=u347f2209&margin=%5Bobject%20Object%5D&name=image.png&originHeight=250&originWidth=695&originalType=binary&ratio=1&rotation=0&showTitle=false&size=69038&status=done&style=none&taskId=u1e7f0fd0-3e67-4055-9fa7-b85f8fd0d73&title=&width=695)
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>相邻兄弟选择器</title>
    <style>
        ul{
            list-style:none;
        }
        /* 紧跟在img后面的一个p标签 */
        img+p{
            color: red;
            background-color: aqua;
        }
    </style>
</head>
<body>
    <div>
        <ul>
            <li>
                <img src="images/广州塔.jpg" alt="广州塔">
                <p>广州塔是广州的地标，位于广州市海珠区</p>
                <p>广州塔是一个可以观光的地方，每层楼都有不同的游玩场所，顶层有摩天轮、跳楼机</p>
            </li>
        </ul>
    </div>
</body>
</html>
```
#### 通用兄弟选择器
![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1657093888814-6e341c5f-05d8-4afe-8aa3-01e1ba79be9f.png#averageHue=%23f9f8f7&clientId=uab3bcd56-f6ff-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=442&id=u7293cc1d&margin=%5Bobject%20Object%5D&name=image.png&originHeight=442&originWidth=670&originalType=binary&ratio=1&rotation=0&showTitle=false&size=30399&status=done&style=none&taskId=u5c1deb39-d8fa-4cfe-a77a-78968643c65&title=&width=670)
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>通用兄弟选择器学习</title>
    <style>
        /* 跟h3是同层级的才会应用样式，div里的p就不会应用 */
        h3~p{
            color: red;
        }

        /* 关系可以用各种选择器来定位 */
        .box~span{
            background-color: yellowgreen   ;
        }
        /* 通过2个类来选择有关系的标签 */
        .box~.spec{
            color: teal;
        }
    </style>
</head>
<body>
    <h1>通用兄弟选择器学习</h1>
    <p>我是一个段落</p>
    <p>我是一个段落</p>
    <p>我是一个段落</p>

    <h3>h3标题</h3>
    <p>h3后面的段落</p>
    <p>h3后面的段落</p>
    <p>h3后面的段落</p>
    <div class="box">
        <p>h3后面的div里的段落</p>
        <p>h3后面的div里的段落</p>
        <p>h3后面的div里的段落</p>
    </div>

    <span>我是box类的div标签后面的文字</span>
    <span class="spec">我是box类的div标签后面的文字</span>
    <span>我是box类的div标签后面的文字</span>
</body>
</html>
```
### 序号选择器
| 选择器 | 意义 |
| --- | --- |
| :first-child | 第一个子某元素 |
| :last-child | 最后一个子元素 |
| :nth-child(num) | 第num个子元素 |
| :nth-of-type(num) | 第num个某元素类型的子元素 |
| :nth-last-child(num) | 倒数第num个子元素 |
| :nth-last-of-type(num) | 倒数第num个某元素类型的子元素 |

![127.0.0.1_5500_practice_CSS%E5%AD%A6%E4%B9%A0%E5%92%8C%E7%BB%83%E4%B9%A0%E4%BB%A3%E7%A0%81_CSS%E9%80%89%E6%8B%A9%E5%99%A8_%E5%BA%8F%E5%8F%B7%E9%80%89%E6%8B%A9%E5%99%A8.html.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1657189547012-0369f426-6fd6-42bb-9b56-0b2f5f7ea346.png#averageHue=%23fcfcfb&clientId=uaf569d7e-705c-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=1765&id=u9142df21&margin=%5Bobject%20Object%5D&name=127.0.0.1_5500_practice_CSS%25E5%25AD%25A6%25E4%25B9%25A0%25E5%2592%258C%25E7%25BB%2583%25E4%25B9%25A0%25E4%25BB%25A3%25E7%25A0%2581_CSS%25E9%2580%2589%25E6%258B%25A9%25E5%2599%25A8_%25E5%25BA%258F%25E5%258F%25B7%25E9%2580%2589%25E6%258B%25A9%25E5%2599%25A8.html.png&originHeight=1765&originWidth=949&originalType=binary&ratio=1&rotation=0&showTitle=false&size=50261&status=done&style=none&taskId=u4bc3ee1b-5600-4ad8-b549-81673714cff&title=&width=949)
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>序号选择器</title>
    <style>
        /* 给div标签添加边框 */
        div{
            border: 1px solid black;
        }
        /* .box类的第一个子标签，如果不指定p的话如果前面的选择器可以选中多个元素，那么这些个元素的第一个子标签也会引用样式 */
        .box1 p:first-child{
            color: aqua;
        }

        /* 倒数第一个子标签 */
        .box1 p:last-child{
            color: chartreuse;
        }

        /* 指定正数第几个元素 */
        .box2 p:nth-child(3){
            font-size: 40px;
        }
        /* 指定倒数第几个元素 */
        .box2 p:nth-last-child(2){
            font-size: 30px;
        }

        /* 可以写成an+b的形式，2n+1是奇数，也可以写成odd，同理2n是偶数，等同于even */
        .box3 p:nth-child(odd){
            color: orchid;
            font-size: 26px;
        }

        /* .box4中演示的是可以正数指定类型的第几个子元素 */
        .box4 p:nth-of-type(2n+1){
            color: red;
            font-size: 28px;
        }

        /* 倒数指定类型的第几个子元素 */
        .box5 h3:nth-last-of-type(1){
            font-size: 31px;
            color: aqua;
        }
    </style>
</head>
<body>
    <div class="box1">
        <p>1</p>
        <p>2</p>
        <p>3</p>
        <p>4</p>
        <p>5</p>
        <p>6</p>
        <p>7</p>
        <p>8</p>
    </div>

    <div class="box2">
        <p>1</p>
        <p>2</p>
        <p>3</p>
        <p>4</p>
        <p>5</p>
        <p>6</p>
        <p>7</p>
        <p>8</p>
    </div>

    <div class="box3">
        <p>1</p>
        <p>2</p>
        <p>3</p>
        <p>4</p>
        <p>5</p>
        <p>6</p>
        <p>7</p>
        <p>8</p>
    </div>

    <div class="box4">
        <p>p1</p>
        <p>p2</p>
        <p>p3</p>
        <h3>h3-1</h3>
        <h3>h3-2</h3>
        <h3>h3-3</h3>
        <p>p4</p>
        <p>p5</p>
        <h3>h3-4</h3>
        <h3>h3-5</h3>
    </div>

    <div class="box5">
        <p>p1</p>
        <p>p2</p>
        <h3>h3-1</h3>
        <h3>h3-2</h3>
        <p>p3</p>
        <p>p4</p>
    </div>
    
</body>
</html>
```
## CSS层叠的含义
### 继承性

- 如果一个标签没有设置过一些样式，它的某个祖先级曾经设置过，在浏览器中该标签也会加载这些样式，这些样式都是从祖先级继承而来，这种现象就是继承性。
- 能够被继承的样式是所有的文字相关样式属性，其他的属性都不能被继承。
- 继承性的应用：可以把页面上出现较多的文字样式设置到较高层次的标签中，比如body，就可以减少在多个标签里面都写同样的样式了。<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667207245207-c564e2eb-8d5d-4014-afda-a18e9560aad6.png#averageHue=%23d5c7a5&clientId=u54c8bda8-3222-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=469&id=uf81965b1&margin=%5Bobject%20Object%5D&name=image.png&originHeight=469&originWidth=683&originalType=binary&ratio=1&rotation=0&showTitle=false&size=307108&status=done&style=none&taskId=u8ec479d5-ff5a-4666-a0ca-1c6bca89c6e&title=&width=683)

![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667207291182-f6523c9f-9325-42ae-979f-1bb96f0f9f7a.png#averageHue=%23bcb968&clientId=u54c8bda8-3222-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=460&id=u66dbad20&margin=%5Bobject%20Object%5D&name=image.png&originHeight=460&originWidth=452&originalType=binary&ratio=1&rotation=0&showTitle=false&size=12794&status=done&style=none&taskId=ubc7a1a91-0e5e-4eb3-81df-34d6e7f56c4&title=&width=452)
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    body {
      color: green;
      font-family: "宋体";
      font-size: 14px;
    }
    .box1 {
      width: 200px;
      height: 200px;
      background-color: pink;      
    }
    /* p {
      height: 50px;
    } */


  </style>
</head>
<body>
  <h2>这是一个二级标题</h2>
  <div class="box1">    
    <p>这是 box1 标签内部的段落</p>
    <p>这是 box1 标签内部的段落</p>
    <p>这是 box1 标签内部的段落</p>
    <p>这是 box1 标签内部的段落</p>
  </div>
  <div class="box2">    
    <p>这是 box1 标签内部的段落</p>
    <p>这是 box1 标签内部的段落</p>
    <p>这是 box1 标签内部的段落</p>
    <p>这是 box1 标签内部的段落</p>
  </div>

</body>
</html>
```
### 层叠性

- CSS的名字叫层叠式样式表，层叠的意思是多个不同的选择器可以同时应用在同一个元素，效果可以叠加或者根据选择器权重的不同覆盖
- 不同选择器之间的优先级是id选择器>类选择器>标签选择器
- 复杂选择器可以通过（id的个数, class的个数, 标签的个数）的形式，计算权重
- 如果我们需要将某个选择器的某条属性提升权重，可以在属性后面写!important
- 选择器的优先级有就近原则，里所选标签越近的权值越高![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667207585443-9466cfc3-c8f4-4a99-9153-16f0599b9bec.png#averageHue=%23eeeff4&clientId=u54c8bda8-3222-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=442&id=u35a4a676&margin=%5Bobject%20Object%5D&name=image.png&originHeight=442&originWidth=1101&originalType=binary&ratio=1&rotation=0&showTitle=false&size=283730&status=done&style=none&taskId=u5a090596-a4d7-4078-b209-bdc6ca3ee10&title=&width=1101)![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1657382176317-e928b548-3d6e-40d7-aa70-3c9c918b731c.png#averageHue=%23fff9f7&clientId=ua105f131-3034-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=95&id=u7cfd262a&margin=%5Bobject%20Object%5D&name=image.png&originHeight=105&originWidth=504&originalType=binary&ratio=1&rotation=0&showTitle=false&size=5283&status=done&style=none&taskId=uac9912c5-6309-4d3f-b0bc-cce4387438c&title=&width=458.18180825099495)
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>选择器权值</title>
    <style>
        p{
            color: blue
        }
        .green{
            color: green
        }
        #yellow{
            color: yellow
        }

        #pink{
            color: pink
        }
    </style>
</head>
<body>
    <p style="color:red" id="yellow" class="green">
        权值相同，就近原则；权值不同，哪个权值高，就用哪个
    </p>

    <p id="pink" class="green">
        权值相同，就近原则；权值不同，哪个权值高，就用哪个
    </p>
</body>
</html>
```
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    /* 选中目标，判断选择器权重 */
    /* #ps {
      color: blue;
    }
    .demo {
      color: yellow;
    }
    p {
      color: green;
    }
    * {
      color: red;
    } */
    /* body p {
      color: red;
    }
    .demo {
      color: green;
    }
    #ps.demo {
      color: blue;
    } */
    /* #box1 .box2 .demo,.box1 #box2 #ps {
      color: red !important;
    } */
    /* 选中目标，判断选择器权重，权重相同，判断css书写顺序 */
    .box1 #box2 .box3 .demo {
      color: blue;
    }
    .box1 .box2 #box3 .demo {
      color: yellow;
    }
    /* 选中的是目标的组先级，文字样式被继承，也会出现层叠 */
    /* 第一步：就近原则 */
    /* #box1 {
      color: red;
    }
    .box2 {
      color: green;
    } */
    
    /* 第二步：距离相同的组先级，判断选择器权重 */
    /* .box3 {
      color: blue;
    }
    #box3 {
      color: yellow;
    } */
    /* 第三步：距离相同的组先级，权重也相同，比较书写顺序 */
    
    /* .box2 #box3 {
      color: yellow;
    }
    #box2 .box3 {
      color: blue;
    } */
    
    /* 如果遇到 important ，在判断权重过程中 ，会将某条属性的权重提升到最大 */
    /* #box2 {
      color: yellow !important;
    }
    #box2 .box3 {
      color: blue;
    } */

    /* 行内样式的权重最高，但是低于 important */
  </style>
</head>
<body>  
  <div class="box1" id="box1">
    <div class="box2" id="box2">
      <div class="box3" id="box3">
        <p class="demo" id="ps" style="color: blue;">看一看文字颜色是什么？</p>
      </div>
    </div>
  </div>
</body>
</html>
```

- 可以在浏览器控制台中查看样式的继承和层叠情况
## 文本与字体属性
### 字体属性详解
#### font-size属性

- font-size属性用来设置字号，单位通常为px，也有em、rem单位，font-size: 30px;
- 网页文字正文字号通常是16px，浏览器最小支持12px字号，现在普遍使用14px+<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667205065923-c9813d85-3db1-43c8-93f6-0c56e2748b42.png#averageHue=%23f3f2f2&clientId=u54c8bda8-3222-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=506&id=ub7dcb608&margin=%5Bobject%20Object%5D&name=image.png&originHeight=506&originWidth=946&originalType=binary&ratio=1&rotation=0&showTitle=false&size=72714&status=done&style=none&taskId=ue912dde2-ae16-49ae-9a2c-531212da848&title=&width=946)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667205093977-9ad0701b-1700-4744-a295-9295ff208a57.png#averageHue=%23434852&clientId=u54c8bda8-3222-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=260&id=u45884c15&margin=%5Bobject%20Object%5D&name=image.png&originHeight=260&originWidth=1121&originalType=binary&ratio=1&rotation=0&showTitle=false&size=69430&status=done&style=none&taskId=ua20be3c0-7a77-472c-9ae5-50d434ac1b8&title=&width=1121)
#### font-weight属性

- font-weight属性设置字体的粗细程度，属性值可以是单词类型或者数字类型
- 单词类型的属性值有下图几个，通常就用normal和 bold两个值。<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667373580214-e95ff6e3-9774-459e-9084-12c71dac9647.png#averageHue=%23f6f5f5&clientId=u797b2182-d2c2-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=292&id=u37f8905a&margin=%5Bobject%20Object%5D&name=image.png&originHeight=292&originWidth=706&originalType=binary&ratio=1&rotation=0&showTitle=false&size=108232&status=done&style=none&taskId=u6615dea9-4167-4242-b60a-7c2366ce292&title=&width=706)
- 数字类型的属性值范围是100-900，数字越大，字体约粗。
- normal表示正常粗细，等价于400，可以让一些本来就加粗的变成正常粗细，例如标题标签。
- bold表示加粗，等价于700。
- lighter表示更细。
- bolder表示更粗，bolder和lighter大多数中文都不合适
```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>练习7 font-weight</title>
  <style>
    .normal {
      font-weight: normal;
    }

    .bold {
      font-weight: bold;
    }

    .w_400 {
      font-weight: 400;
    }

    .w_700 {
      font-weight: 700;
    }
  </style>
</head>

<body>
  <p class="normal">路漫漫其修远兮，吾将上下而求索normal</p>
  <p class="bold">路漫漫其修远兮，吾将上下而求索bold</p>
  <p class="w_400">路漫漫其修远兮，吾将上下而求索400</p>
  <p class="w_700">路漫漫其修远兮，吾将上下而求索700</p>
</body>

</html>
```
#### font-style属性

- font-style属性设置字体的倾斜
- normal：正常字体，也可以取消倾斜，比如可以把天生倾斜的i、 em等标签设置为不倾斜。
- italic：设置为倾斜字体（常用），主要针对英文等有倾斜体的字体
- oblique：也可以设置倾斜字体，不常用<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667375524052-d2ec62cc-e8c5-4905-a751-7b08b024e4c1.png#averageHue=%23f6f4f1&clientId=u797b2182-d2c2-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=138&id=u844b7af2&margin=%5Bobject%20Object%5D&name=image.png&originHeight=138&originWidth=376&originalType=binary&ratio=1&rotation=0&showTitle=false&size=10883&status=done&style=none&taskId=u50c52450-c843-4132-a75c-051aa54d509&title=&width=376)
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>练习8 font-style</title>
  <style>
    .normal {
      font-style: normal;
    }

    .italic {
      font-style: italic;
    }

    .oblique {
      font-style: oblique;
    }
  </style>
</head>
<body>
  <p class="normal">路漫漫其修远兮，吾将上下而求索normal</p>
  <p class="italic">路漫漫其修远兮，吾将上下而求索italic</p>
  <p class="oblique">路漫漫其修远兮，吾将上下而求索oblique</p>
</body>
</html>
```
#### font-family属性

- font-family属性用来设置文本的字体，可以是系统自带的字体，也可以是自定义字体。
- 属性值可以有多个，可以是中文名称或者英文名称，一般英文名称放到前面，后面的字体是前面的字体的“后备”字体。
- 中文字体也可以称呼它们的英语名字。[CSS font-family中文字体英文名称展示](https://www.zhangxinxu.com/study/201703/font-family-chinese-english.html)
- 常用的中文字体：
   - 宋体——SimSun
   - 微软雅黑——Microsoft Yahei
- 常用的英文字体：
   - Arial
   - consolas
- 不同浏览器会有不同的默认字体
- [中文字体网页开发指南——阮一峰](http://www.ruanyifeng.com/blog/2014/07/chinese_fonts.html)
- 字体通常必须是用户计算机中已经安装好的字体，所以一般来说设置为微软雅黑和宋体较多，设置成其他字体较少。
- 字体文件根据操作系统和浏览器不同，有eot、woff2、 woff、ttf、svg文件格式，自定义字体需要同时有这5种文件。
- 可以使用@font-face来自定义字体，进阶知识：[真正了解CSS3背景下的@font face规则](https://www.zhangxinxu.com/wordpress/2017/03/css3-font-face-src-local/)
- 阿里巴巴提供了一套免费商用授权的普惠字体，网址[https://www.iconfont.cn/webfont](https://www.iconfont.cn/webfont)![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1657523305008-e7591e5e-8132-4ae4-9c0d-9499e81349d2.png#averageHue=%23f5f3f1&clientId=u2397254b-cea1-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=566&id=u1af378a3&margin=%5Bobject%20Object%5D&name=image.png&originHeight=566&originWidth=794&originalType=binary&ratio=1&rotation=0&showTitle=false&size=83311&status=done&style=none&taskId=u9641f419-44ad-4fa8-91f8-60c87f13135&title=&width=794)
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>字体属性学习</title>
    <style>
        /* 设置中午字体，或者字体里有空格需要双引号包裹 */
        .para1{
            font-family: "宋体";
        }

        /* 中文字体有自己的英文名字 */
        .para2{
            font-family: 'simsun';
        }

        /* 网页默认字体是微软雅黑 */
        .para3{
            font-family: 'Microsoft YaHei';
        }

        /* 英文描述的字体要放在中文字体的前面 */
        .para4{
            font-family:"Times New Roman",serif,"正楷";
        }
        
        /* 自定义字体需要先把字体文件引入 */
        @font-face {
            font-family: "Mine Font";
            font-display: swap;
            src: url("webfont/webfont.eot");
            src: url("webfont/webfont.eot")format('embedded-opentype'),
                url("webfont/webfont.woff2")format('woff2'),
                url("webfont/webfont.woff")format('woff'),
                url("webfont/webfont.ttf")format('truetype'),
                url("webfont/webfont.svg")format('svg');

        }
        /* 只有生成的字体才可以应用样式 */
        .para5{
            font-family: 'Mine Font';
        }

    </style>
</head>
<body>
    <p class="para1">好好学习，天天向上 good good study,day day up1</p>
    <p class="para2">好好学习，天天向上 good good study,day day up2</p>
    <p class="para3">好好学习，天天向上 good good study,day day up3</p>
    <p class="para4">好好学习，天天向上 good good study,day day up4</p>
    <p class="para5">好好学习，天天向上 good good study,day day up5</p>
    <p class="para6">好好学习，天天向上 good good study,day day up6</p>
    <p class="para7">好好学习，天天向上 good good study,day day up7</p>
    <p class="para8">好好学习，天天向上 good good study,day day up8</p>
    <p class="para9">好好学习，天天向上 good good study,day day up9</p>
</body>
</html>
```
#### font合写属性
[CSS font关键字属性值的简单研究](https://www.zhangxinxu.com/wordpress/2016/01/css-font-keyword-value-caption-menu-message-box-small-caption-status-bar/)

- 字体、字号、行高、加粗、斜体都是font综合属性的单一属性。
- font属性可以用来作为font-style, font-weight, font-size, line-height和font-family属性的合写，属性值可以有2个到多个，彼此之间空格隔开。
- 必须包含<font-size>，<font-family>属性值，字号在前，字体在后
- font属性经常对字体、字号、行高进行合写，书写顺序必须是字号、行高、字体，字号和行高之间必须用/进行分隔。
- font-style, font-variant 和 font-weight 必须在 font-size 之前，但是这几个属性值可以互换位置
- line-height 必须跟在 font-size 后面，由 "/" 分隔，例如 "16px/3"
- font-family 必须最后指定![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1657533868389-2259e63f-fb26-4bcf-a5e2-e8dbd0e49b7c.png#averageHue=%23f5f3f2&clientId=u2397254b-cea1-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=249&id=UBOIB&margin=%5Bobject%20Object%5D&name=image.png&originHeight=249&originWidth=1357&originalType=binary&ratio=1&rotation=0&showTitle=false&size=23461&status=done&style=none&taskId=u6acac16d-4fc6-49e7-bb1c-f7a6e49cc7f&title=&width=1357)
- 可以看到效果是一样的。
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>font合写属性</title>
    <style>
        /* font可以把font-style, font-weight, font-size, line-height和font-family属性合写，
            但是要遵循顺序
         */

         /* 分开设置 */
         .para1{
            font-style: italic;
            font-weight: bold;
            font-size: 30px;
            line-height: 2;
            font-family: 'KaiTi';
         }
					/*字号大小/行高 字体*/
         .para2{
            font: italic bold 30px/2 "KaiTi";
         }
    </style>
</head>
<body>
    <p class="para1">
        好好学习，天天向上,
        好好学习，天天向上,
        好好学习，天天向上,
        好好学习，天天向上,
        好好学习，天天向上,
        好好学习，天天向上,
        好好学习，天天向上,
        好好学习，天天向上,
    </p>

    <p class="para2">
        好好学习，天天向上,
        好好学习，天天向上,
        好好学习，天天向上,
        好好学习，天天向上,
        好好学习，天天向上,
        好好学习，天天向上,
        好好学习，天天向上,
        好好学习，天天向上,
    </p>
</body>
</html>
```
### 文本属性
#### color属性

- color属性用来设置文本内容的颜色
- 设置颜色的方法有以下几种：
         1. **英语单词**：比如color:red表示设置红色，这种比较不准确，学习时可用，工作中一般不用
         2. **十六进制表示法：**所有设计软件中都通用的颜色表示法，由设计师提供。比如color:#ff0000表示红色
            1. 十六进制ff就是十进制的255，每种颜色分量都是0~255
            2. 如果颜色值是#aabbcc的形式，可以简写为#abc
            3. 黑色是#000，白色是#fff，常见的灰色有#ccc、#333、 #2f2f2f等
         3. **rgb()  表示法：**color: rgb(255, 0, 0);rgb表示法里面只能填数字
         4. **rgba()表示法：**color: rgba(255, 0, 0, .65);最后一个参数表示透明度，介于0到1之间，0表示纯透明，1表示纯实心的数字
#### text-decoration属性

- text-decoration属性用于设置文本的修饰线外观的（下划线、删除线）
- none：没有修饰线，可以用来取消超链接标签的下划线
- underline：下划线
- line-through：删除线<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667380746150-aaf532cf-e6aa-4eea-a30b-a1e802207630.png#averageHue=%23f6f6f5&clientId=u797b2182-d2c2-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=246&id=uf6a20877&margin=%5Bobject%20Object%5D&name=image.png&originHeight=246&originWidth=696&originalType=binary&ratio=1&rotation=0&showTitle=false&size=92079&status=done&style=none&taskId=u71b10bb4-14f1-451b-aef9-e6653eaff2f&title=&width=696)

![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1657509553521-d0283f32-1ea7-47f7-9fe9-b776110c2d0a.png#averageHue=%23f8f5f4&clientId=ub33716a1-ad2a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=607&id=YQ0Id&margin=%5Bobject%20Object%5D&name=image.png&originHeight=607&originWidth=489&originalType=binary&ratio=1&rotation=0&showTitle=false&size=55647&status=done&style=none&taskId=ud4905974-e655-483a-aaf5-5d59327bc67&title=&width=489)	
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>常用文本样式属性学习</title>
    <style>
        /* 用英语单词设置颜色 */
        .para1{
            color: red;
        }
        /* 用十六进制设置颜色 */
        .para2{
            color: #ff6666;
        }
        /* aabbcc可以简写成abc */
        .para3{
            color: #f66;
        }
        /* 用rgb()设置颜色 */
        .para4{
            color: rgb(111, 21, 67);
        }
        /* 用rgba()设置颜色,后面的颜色透明度可以省略0 */
        .para5{
            color: rgba(111,21,67,.2);
        }
        /* font-size属性设置字号，一定要带单位 */
        .para6{
            font-size: 30px;
        }
        /* font-weight属性设置字体粗细,bold加粗 */
        .para7{
            font-weight: bold;
        }
        .h3-1{
            font-weight: normal;
        }
        /* normal跟400等价，可以不写单位 */
        .h3-2{
            font-weight: 400;
        }
        /* bold和700等价 */
        .para8{
            font-weight: 700;
        }
        /* bolder和lighter大多数中文都不合适 */
        .para9{
            font-weight: lighter;
        }
        .para10{
            font-weight: bolder;
        }
        /* font-style设置字体倾斜 */
        .para11{
            font-style: italic;
        }
        .para12{
            font-style:oblique;
        }
        /* 将原本倾斜的i标签变成正常 */
        i{
            font-style: initial;
        }

        /* text-decotation用来设置下划线和删除线 */
        .para12{
            text-decoration: underline;
        }
        .para13{
            text-decoration: line-through;
        }
        /* 取消超链接的下划线 */
        a{
            text-decoration: none;
        }
    </style>
</head>
<body>
    <p class="para1">路漫漫其修远兮，吾将上下而求索1</p>
    <p class="para2">路漫漫其修远兮，吾将上下而求索2</p>
    <p class="para3">路漫漫其修远兮，吾将上下而求索3</p>
    <p class="para4">路漫漫其修远兮，吾将上下而求索4</p>
    <p class="para5">路漫漫其修远兮，吾将上下而求索5</p>
    <p class="para6">路漫漫其修远兮，吾将上下而求索6</p>
    <p class="para7">路漫漫其修远兮，吾将上下而求索7</p>
    <h3 class="h3-1">路漫漫其修远兮，吾将上下而求索h3-1</h3>
    <h3 class="h3-2">路漫漫其修远兮，吾将上下而求索h3-2</h3>
    <p class="para8">路漫漫其修远兮，吾将上下而求索8</p>
    <p class="para9">路漫漫其修远兮，吾将上下而求索9</p>
    <p class="para10">路漫漫其修远兮，吾将上下而求索10</p>
    <p class="para11">路漫漫其修远兮，吾将上下而求索11</p>
    <p class="para12">路漫漫其修远兮，吾将上下而求索</p>
    <p class="para13">路漫漫其修远兮，吾将上下而求索</p>
    <i>路漫漫其修远兮，吾将上下而求索iii</i><br>

    <a href="">路漫漫其修远兮，吾将上下而求索</a>


</body>
</html>
```
#### text-indent属性

- text-indent属性定义首行文本内容之前的缩进量，单位是em（em表示字符宽度）。<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667380852535-b907646a-5bbc-4d34-b21d-5e3d874e5b67.png#averageHue=%23f5f4f3&clientId=u797b2182-d2c2-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=237&id=u96ebdb0a&margin=%5Bobject%20Object%5D&name=image.png&originHeight=237&originWidth=837&originalType=binary&ratio=1&rotation=0&showTitle=false&size=129022&status=done&style=none&taskId=u89e99a1b-42a0-41e9-9845-4f40634b490&title=&width=837)
- 实际工作中，最常使用 em 为单位的属性值。
- 属性值区分正负，正数表示向右缩进，负数表示向左缩进。
#### line-height属性

- line-height属性用于定义行高，进阶知识：[css行高line-height的一些深入理解及应用](https://www.zhangxinxu.com/wordpress/2009/11/css%E8%A1%8C%E9%AB%98line-height%E7%9A%84%E4%B8%80%E4%BA%9B%E6%B7%B1%E5%85%A5%E7%90%86%E8%A7%A3%E5%8F%8A%E5%BA%94%E7%94%A8/)
- 属性的值可以是以px为单位的数值：line-height:30px;
- 可以是无单位的数字，表示的是行高为字体大小的多少倍，这个是最推荐的方式，不会在继承时产生不确定的结果，line-height:1.5;
- 也可以是百分数，表示字号的倍数，line-height:150%;
- 设置text-align: center，即可实现文本水平居中，要垂直居中则要行高等于盒子的高度![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1657533160795-d9cb0ae2-6fd0-4bd7-a3aa-ff355efec844.png#averageHue=%23f9f3de&clientId=u2397254b-cea1-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=592&id=u05708c6d&margin=%5Bobject%20Object%5D&name=image.png&originHeight=592&originWidth=1366&originalType=binary&ratio=1&rotation=0&showTitle=false&size=93516&status=done&style=none&taskId=u4ba7f84c-a30a-4d2c-8975-0ade5d5d659&title=&width=1366)
```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>段落和行</title>
    <style>
        .para1{
            /* 首行缩进量 */
            text-indent: 2em;
            /* 以px为单位设置行高 */
            line-height: 30px;
        }

        .para2{
            text-indent: 2em;
            /* 无单位数字，最推荐的方式，表示行高为字体大小的多少倍 */
            line-height: 2.5;
            /*  */
        }

        .box{
            /* 把div变成一个盒子 */
            width: 300px;
            height: 300px;
            border: 1px solid;
            background-color: gold;
            font-size: 30px;
            color: #fff;

            /* 设置文本水平居中 */
            text-align: center;

            /* 把行高设置成与盒子的高度一致就可以垂直居中了 */
            line-height: 300px;
        }
    </style>
</head>

<body>
    <p class="para1">
        噫吁嚱，危乎高哉！
        蜀道之难，难于上青天！
        蚕丛及鱼凫，开国何茫然！
        尔来四万八千岁，不与秦塞通人烟。
        西当太白有鸟道，可以横绝峨眉巅。
        地崩山摧壮士死，然后天梯石栈相钩连。
        上有六龙回日之高标，下有冲波逆折之回川。
        黄鹤之飞尚不得过，猿猱欲度愁攀援。
        青泥何盘盘，百步九折萦岩峦。
        扪参历井仰胁息，以手抚膺坐长叹。

        问君西游何时还？畏途巉岩不可攀。
        但见悲鸟号古木，雄飞雌从绕林间。
        又闻子规啼夜月，愁空山。
        蜀道之难，难于上青天，使人听此凋朱颜！
        连峰去天不盈尺，枯松倒挂倚绝壁。
        飞湍瀑流争喧豗，砯崖转石万壑雷。
        其险也如此，嗟尔远道之人胡为乎来哉！(也如此 一作：也若此)

        剑阁峥嵘而崔嵬，一夫当关，万夫莫开。
        所守或匪亲，化为狼与豺。
        朝避猛虎，夕避长蛇，磨牙吮血，杀人如麻。
        锦城虽云乐，不如早还家。
        蜀道之难，难于上青天，侧身西望长咨嗟！
        
    </p>

    <p class="para2">
        噫吁嚱，危乎高哉！
        蜀道之难，难于上青天！
        蚕丛及鱼凫，开国何茫然！
        尔来四万八千岁，不与秦塞通人烟。
        西当太白有鸟道，可以横绝峨眉巅。
        地崩山摧壮士死，然后天梯石栈相钩连。
        上有六龙回日之高标，下有冲波逆折之回川。
        黄鹤之飞尚不得过，猿猱欲度愁攀援。
        青泥何盘盘，百步九折萦岩峦。
        扪参历井仰胁息，以手抚膺坐长叹。

        问君西游何时还？畏途巉岩不可攀。
        但见悲鸟号古木，雄飞雌从绕林间。
        又闻子规啼夜月，愁空山。
        蜀道之难，难于上青天，使人听此凋朱颜！
        连峰去天不盈尺，枯松倒挂倚绝壁。
        飞湍瀑流争喧豗，砯崖转石万壑雷。
        其险也如此，嗟尔远道之人胡为乎来哉！(也如此 一作：也若此)

        剑阁峥嵘而崔嵬，一夫当关，万夫莫开。
        所守或匪亲，化为狼与豺。
        朝避猛虎，夕避长蛇，磨牙吮血，杀人如麻。
        锦城虽云乐，不如早还家。
        蜀道之难，难于上青天，侧身西望长咨嗟！
    </p>

    <div class="box">
        好好学习，天天向上
    </div>
</body>

</html>
```
#### 水平对齐text-align属性

- 作用：设置文本水平方向的对齐。
- 在盒子标签中，不论文本是单行还是多行，都会对应方向对齐，text-align属性就是设置文本水平方向上的对齐方向
- 属性值：三个方向的单词<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667380597450-1258c66e-54e2-4603-bb9d-d4f10e1dbe87.png#averageHue=%23f8f7f7&clientId=u797b2182-d2c2-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=229&id=u1ea3af51&margin=%5Bobject%20Object%5D&name=image.png&originHeight=229&originWidth=761&originalType=binary&ratio=1&rotation=0&showTitle=false&size=65172&status=done&style=none&taskId=u94213684-28c7-46e5-b347-d254dde89b4&title=&width=761)
### 继承

- 文本与字体属性可以继承父标签的属性。
- 因为文字相关属性有继承性，所以通常会设置body标签的字号、颜色、行高等，这样就能当做整个网页的默认样式了。
## 盒模型
### 什么是盒模型

- 所有HTML标签都可以看成矩形盒子，由width宽度、height高度、padding内边距、border边框和margin外边距构成，称为“盒模型”<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667381268713-da0f6111-904f-4e27-9483-31fd8023e323.png#averageHue=%23cdc0ab&clientId=u797b2182-d2c2-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=538&id=u16b1d385&margin=%5Bobject%20Object%5D&name=image.png&originHeight=538&originWidth=880&originalType=binary&ratio=1&rotation=0&showTitle=false&size=337913&status=done&style=none&taskId=ucbeef59d-774b-4d2e-af67-8db87045466&title=&width=880)
- 理解这些“盒子”的基本原理，是我们使用 CSS 实现准确布局、处理元素排列的关键。
- width和height是标签内容的宽高，单位通常是px，移动端开发也会涉及百分数、rem等单位
- padding是内边距，就是内容到盒子之间的距离，分上下左右。
- border是外边距，也是边框，就是盒子的边框长度，也分上下左右。
- margin是外边距，是元素与元素之间的距离。
- 盒子可以实体化的区域：width+height+padding+border
- 盒子实际占位的位置：width+height+padding+border+margin
#### 盒模型图

- 可以在浏览器控制台中查看元素的盒模型图<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667464891380-44518e0c-6a4f-46de-8d8e-369d87440701.png#averageHue=%23f8f3e8&clientId=u441aed12-67cf-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=320&id=u3d1166b2&margin=%5Bobject%20Object%5D&name=image.png&originHeight=320&originWidth=547&originalType=binary&ratio=1&rotation=0&showTitle=false&size=17706&status=done&style=none&taskId=ud8fc66b0-1d71-4a89-a7ac-59b01352a89&title=&width=547)
### 盒模型属性
#### 宽度width

- 作用：设置可以添加元素内容的区域的宽度。
- 属性值：<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667464967159-cfdce8c5-2471-4302-9c46-85aefd82c86c.png#averageHue=%23f6f6f5&clientId=u441aed12-67cf-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=243&id=ua121fb51&margin=%5Bobject%20Object%5D&name=image.png&originHeight=243&originWidth=816&originalType=binary&ratio=1&rotation=0&showTitle=false&size=104027&status=done&style=none&taskId=u5a52e350-39c0-4d27-94f0-4f07455ca61&title=&width=816)

- 特殊应用：
   - width属性的值为auto的时候，浏览器会根据不同的元素的特点自动计算出实际宽度，例如div需要独占一行的，width的值就会撑满父元素的width，span不占一行的width属性就是元素内部内容的实际宽度。
   - <body> 元素比较特殊，不需要设置 width 属性，宽度会自动适应浏览器窗口的宽度。
#### 高度height

- 作用：设置可以添加元素内容的区域的高度。
- 属性值：<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667465163610-1133b6e4-8910-49a4-a716-241a42e256a6.png#averageHue=%23f6f6f6&clientId=u441aed12-67cf-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=209&id=u57b50112&margin=%5Bobject%20Object%5D&name=image.png&originHeight=209&originWidth=691&originalType=binary&ratio=1&rotation=0&showTitle=false&size=79765&status=done&style=none&taskId=u5e9cf6d4-c60b-47c8-b242-69ebc197d8d&title=&width=691)
- 特殊应用：
   - 属性值为auto时，高度为内容的实际高度，会自动撑开，自适应内容的高度
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>width宽度和height高度</title>

  <style>
    .box {
      width: 500px;
      /* 根据内容自动增加 */
      height: auto;
      background-color: red;
    }
    /* div 这种需要独占一行的，width属性为auto的时候会自动撑满父元素的width，高度则根据内容调整 */
    .inbox {
      width: auto;
      height: auto;
      background-color: blue;
    }

    /* 固定的宽高 */
    .box>p {
      width: 100px;
      height: 100px;
      background-color: green;
    }

    /* width属性为auto的时候，width的值就会撑满父元素的width，height为父元素高度的百分比 */
    div>.pbox {
      width: auto;
      height: 50%;
    }

    /* span不占一行的width属性就是元素内部内容的实际宽度。 */
    .span_box {
      background-color: yellow;
    }
  </style>
</head>
<body>
  <div class="box">
    <p>没有class的段落</p>
    <p class="pbox">在div里面的段落</p>
    <div class="inbox">
      <span class="span_box">这是一行span文字</span>
    </div>
    
  </div>
</body>
</html>
```
#### 内边距 padding

- 作用：设置的是元素的边框内部到宽高区域之间的距离。
- 特点：可以去加载背景，不能书写嵌套的内容。
- 属性值：常用px为单位的数值。
- padding 是一个复合属性，可以根据内边距的方向不同划分为四个方向的单一属性。
##### 单一属性

- 书写四个方向单一属性时，一般是按照顺时针规律书写：上、右、下、左。<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667465330502-b177ed07-88a2-4c08-946c-f69c19b9498b.png#averageHue=%233d434c&clientId=u441aed12-67cf-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=278&id=u296b80d7&margin=%5Bobject%20Object%5D&name=image.png&originHeight=278&originWidth=901&originalType=binary&ratio=1&rotation=0&showTitle=false&size=119643&status=done&style=none&taskId=u89a0bbec-7907-43b5-b66d-2f5f5ba1656&title=&width=901)
##### 简写

- 为了简化书写，一般习惯将四个方向的单一属性进行合写成 padding 属性。
- padding 属性值：可以有 1-4 个值，值之间用空格进行分隔。
- 根据 padding 的属性值的个数不同，区分了四种表示法：
   - 四值法：设置四个属性值，分配方向上、右、下、左，从上面开始顺时针赋值。<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667790378574-b5670d22-3fdf-4542-b986-954958b7baa1.png#averageHue=%23e9cd94&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=324&id=u6b59f800&margin=%5Bobject%20Object%5D&name=image.png&originHeight=324&originWidth=381&originalType=binary&ratio=1&rotation=0&showTitle=false&size=16511&status=done&style=none&taskId=u4f6b3679-3661-443e-b0c3-ff22615ef61&title=&width=381)![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667790464243-344a5bcc-277e-43ff-9329-74be9c0ccc25.png#averageHue=%23fa2727&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=88&id=ub2d542b9&margin=%5Bobject%20Object%5D&name=image.png&originHeight=88&originWidth=267&originalType=binary&ratio=1&rotation=0&showTitle=false&size=1658&status=done&style=none&taskId=u02b092ad-9a61-4599-b5c1-eebf5604477&title=&width=267)
   - 三值法：设置三个值分配给上、左右、下。<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667800856598-62bf95ac-ac57-497b-b823-ce8c053fa65e.png#averageHue=%23f5ebda&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=337&id=u0204b2fd&margin=%5Bobject%20Object%5D&name=image.png&originHeight=337&originWidth=330&originalType=binary&ratio=1&rotation=0&showTitle=false&size=17428&status=done&style=none&taskId=u6c92e0f4-5506-47b2-b440-faa0d5a8159&title=&width=330)![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667800870755-10e6223a-2594-4918-91d4-86fe0ef8c809.png#averageHue=%2300fd3d&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=88&id=u7df2ac78&margin=%5Bobject%20Object%5D&name=image.png&originHeight=88&originWidth=315&originalType=binary&ratio=1&rotation=0&showTitle=false&size=2301&status=done&style=none&taskId=uf281ec3f-b4be-4be2-8de1-24362167d3d&title=&width=315)
   - 二值法：设置两个值，分配给上下、左右。<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667790492793-b23cd86d-bac5-499d-8d24-66891091ec7e.png#averageHue=%23ebcd94&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=327&id=u05e574d4&margin=%5Bobject%20Object%5D&name=image.png&originHeight=327&originWidth=342&originalType=binary&ratio=1&rotation=0&showTitle=false&size=15598&status=done&style=none&taskId=ua16dc78e-533b-4f37-bb48-9f991f845f4&title=&width=342)![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667790501421-265c7260-0e6d-400d-ad13-62b6c0464288.png#averageHue=%230003fb&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=85&id=ud73f7b4a&margin=%5Bobject%20Object%5D&name=image.png&originHeight=85&originWidth=326&originalType=binary&ratio=1&rotation=0&showTitle=false&size=2152&status=done&style=none&taskId=u635e03de-3fac-4965-83b7-b7420edb5ce&title=&width=326)
   - 单值法：设置属性值只有一个，分配方向上右下左，四边的值相同。<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667790523566-bb94bd85-c18a-429d-a105-26d408b19f8b.png#averageHue=%23ebcd94&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=336&id=ucbf55486&margin=%5Bobject%20Object%5D&name=image.png&originHeight=336&originWidth=339&originalType=binary&ratio=1&rotation=0&showTitle=false&size=15763&status=done&style=none&taskId=u6087e009-8f75-4341-96ab-9775dd8f7d4&title=&width=339)![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667790531209-9f110ec1-e2a6-49d0-b6f4-4c9fb1144921.png#averageHue=%23fbb83b&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=121&id=u49876486&margin=%5Bobject%20Object%5D&name=image.png&originHeight=121&originWidth=305&originalType=binary&ratio=1&rotation=0&showTitle=false&size=2459&status=done&style=none&taskId=u9b183719-ffb6-4f04-9bec-9cbfabe3fb4&title=&width=305)
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>02_内边距padding</title>
  <style>
    p {
      width: 200px;
    }

    /* 单一属性设置 */
    .box2>p {
      padding-top: 10px;
      padding-right: 20px;
      padding-bottom: 30px;
      padding-left: 40px;
      background-color: #aef;
    }
    /* 四值法，从头部开始按照顺时针的顺序书写 */
    .p1 {
      padding:40px 30px 20px 10px;
      background-color: #f00;
    }
    /* 三值法，设置3个值，一个是上内边距的值，一个是左右内边距的值，最后一个应用于下内边距 */
    .p2 {
      /* 上下一个值 */
      padding: 30px 50px 20px;
      background-color: #0f0;
    }
    /* 二值法，左右一个值上下一个值 */
    .p3 {
      padding: 30px 50px;
      background-color: #00f;
    }
    /* 单值法，所有边都使用同一个值 */
    .p4 {
      padding: 40px;
      background-color: #ffaa00;
    }
  </style>
</head>
<body>
  <div class="box1">
    <p class="p1">这是一段文字p1</p>
    <p class="p2">这是第2段文字p2</p>
    <p class="p3">这是第3段文字p3</p>
    <p class="p4">这是第4段文字p4</p>
  </div>

  <div class="box2">
    <p>这是box2里的文字</p>
  </div>
</body>
</html>
```
##### 案例

- 制作三边内边距相同，一边不同。
   - 方法1：使用四值法、三值法进行属性设置。
   - 方法2：利用层叠属性，先用padding设置另外3边，再用单一属性层叠掉另一边。
#### 边框border

- 作用：设置的是内边距外面的边界区域，作为盒子的实体化的最外层。
- 属性值：由三个值组成，分为线的宽度、线的形状、线的颜色 。
- border 属性是一个复合属性，根据划分依据不同可以有两种单一属性的划分方式。
```css
.box1,.box2,.box3 {
      float: left;
      width: auto;
      background-color: red;
      border: 10px solid dodgerblue;
      margin: 10px;
    }
```
##### 按照属性值的类型划分

- 线宽：border-width
   - 作用：设置边框线的宽度。
   - 属性值：常用px形式的数值，跟padding类似也有4个方向的设置，也有4种写法，是复合属性
- 线型：border-style
   - 作用：设置边框的线条形状
   - 属性值：形状的单词，总体也是类似 padding 的综合属性写法，可以分别设置4个方向的边框<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667466764870-4332eb20-9359-4e3d-a3ef-23a1011408db.png#averageHue=%23f5f4f4&clientId=u441aed12-67cf-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=484&id=u3867f9fd&margin=%5Bobject%20Object%5D&name=image.png&originHeight=484&originWidth=689&originalType=binary&ratio=1&rotation=0&showTitle=false&size=255696&status=done&style=none&taskId=ubeaf6900-ce3a-4d59-b685-3f828bdea9b&title=&width=689)
- 线的颜色：border-color
   - 作用：设置边框的颜色。
   - 属性值：颜色名或颜色值，整体类似 padding 综合属性写法。
- ![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667803008286-89271e74-3445-49eb-a91a-1d6891f49a7e.png#averageHue=%23adf131&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=567&id=u0b71a11d&margin=%5Bobject%20Object%5D&name=image.png&originHeight=567&originWidth=273&originalType=binary&ratio=1&rotation=0&showTitle=false&size=12893&status=done&style=none&taskId=u013c40f4-c1da-40f2-9565-12d0af48bb2&title=&width=273)![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667803109985-bf2f3ddc-2168-4cea-adbb-9169984b7823.png#averageHue=%23faeee0&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=518&id=uf43a7a6b&margin=%5Bobject%20Object%5D&name=image.png&originHeight=518&originWidth=285&originalType=binary&ratio=1&rotation=0&showTitle=false&size=24531&status=done&style=none&taskId=u8c24f5d7-7219-43d6-a86e-3ddc494246b&title=&width=285)
```css
 /* 四值法设置border-width和border-style还有border-color */
    .box1p1 {
      border-width: 10px 11px 12px 13px;
      border-style: none solid dashed dotted;
      border-color: azure yellow blue green;
    }
    /* 三值法设置border-width和border-style还有border-color */
    .box1p2 {      
      border-width: 10px 21px 14px;
      border-style: solid dashed dotted;
      border-color: yellow blue green;
    }
    /* 双值法 */
    .box1p3 {      
      border-width: 22px 11px;
      border-style: solid dashed;
      border-color: yellow green;
    }
    /* 单值法 */
    .box1p4 {      
      border-width: 30px;
      border-style: dashed;
      border-color: greenyellow;
    }
```
##### 根据边框的方向划分

- 上边框：border-top
- 右边框：border-right
- 下边框：border-bottom
- 左边框：border-left
- 每个单一属性都必须与复合属性 border 一致，设置三个属性值（线条、颜色、宽度）

![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667803167027-cdce8a5b-3d4d-4419-b431-643e70f0a443.png#averageHue=%23f0f61d&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=431&id=u06c11299&margin=%5Bobject%20Object%5D&name=image.png&originHeight=467&originWidth=262&originalType=binary&ratio=1&rotation=0&showTitle=false&size=8946&status=done&style=none&taskId=u6cdb31b6-a27e-4aa6-a578-7741fa585b8&title=&width=242)![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667803192497-18f52589-7143-44b8-8a74-2c545d8ca354.png#averageHue=%23faefe3&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=387&id=u371d1a44&margin=%5Bobject%20Object%5D&name=image.png&originHeight=454&originWidth=266&originalType=binary&ratio=1&rotation=0&showTitle=false&size=19714&status=done&style=none&taskId=u3bcc5656-0be8-4a2a-8fe6-3b857656b27&title=&width=227)![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667803207529-10fc921b-2c62-4edc-a017-e146fc097692.png#averageHue=%23faefe2&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=519&id=u9c157866&margin=%5Bobject%20Object%5D&name=image.png&originHeight=519&originWidth=269&originalType=binary&ratio=1&rotation=0&showTitle=false&size=22741&status=done&style=none&taskId=u6e63f323-1aad-418f-9426-234befa15ef&title=&width=269)
```css
/* 只设置一条边的边框 */
    .top {
      border-top: 10px solid yellow;
    }

    .right {
      border-right: 11px dashed orange;
    }

    .bottom {
      border-bottom: 12px dotted pink;
    }

    .left {
      border-left: 13px groove indianred;
    }
```
##### 根据方向和类型，进一步细分

- 可以根据方向和类型设置单一属性，单一属性写法：border-方向-类型。
- 细分时必须先写方向划分再写类型划分，否则属性名错误。

![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667803304597-520b44ff-5265-493e-a1e5-44e42c90fdfe.png#averageHue=%2371bd33&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=435&id=ua2231109&margin=%5Bobject%20Object%5D&name=image.png&originHeight=475&originWidth=286&originalType=binary&ratio=1&rotation=0&showTitle=false&size=13077&status=done&style=none&taskId=udb1793e1-8c3d-4ca0-ac2a-ca9bd9645f0&title=&width=262)![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667803316899-bda171f1-5471-4301-b8d0-8929fd51997d.png#averageHue=%23faf0e6&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=420&id=u52a86c82&margin=%5Bobject%20Object%5D&name=image.png&originHeight=523&originWidth=260&originalType=binary&ratio=1&rotation=0&showTitle=false&size=20741&status=done&style=none&taskId=uf4eb157a-fe86-4cce-bd5d-dd04fe68594&title=&width=209)![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667803327920-f8d80453-b581-4b8e-92d1-6e3eea1aeeae.png#averageHue=%23faeee2&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=496&id=u46689679&margin=%5Bobject%20Object%5D&name=image.png&originHeight=496&originWidth=247&originalType=binary&ratio=1&rotation=0&showTitle=false&size=20940&status=done&style=none&taskId=u5ed6a039-2bc9-4363-abf2-1d6a3ee4b9d&title=&width=247)
```css
 .box3p1 {
      border-top-color: gray;
      border-top-width: 10px;
      border-top-style: solid;
    }
    .box3p2 {
      border-right-color: yellowgreen;
      border-right-width: 20px;
      border-right-style: dashed;
    }
    .box3p3 {
      border-bottom-color: rgb(90, 110, 227);
      border-bottom-width: 30px;
      border-bottom-style: dotted;
    }
    .box3p4 {
      border-left-color: deeppink;
      border-left-width: 22px;
      border-left-style: double;
    }
```
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>03-边框border</title>
  <style>
    .box1,.box2,.box3 {
      float: left;
      width: auto;
      background-color: red;
      border: 10px solid dodgerblue;
      margin: 10px;
    }

    p {
      width: 200px;
      height: 200px;
      background-color: aqua;
    }
    /* 四值法设置border-width和border-style还有border-color */
    .box1p1 {
      border-width: 10px 11px 12px 13px;
      border-style: none solid dashed dotted;
      border-color: azure yellow blue green;
    }
    /* 三值法设置border-width和border-style还有border-color */
    .box1p2 {      
      border-width: 10px 21px 14px;
      border-style: solid dashed dotted;
      border-color: yellow blue green;
    }
    /* 双值法 */
    .box1p3 {      
      border-width: 22px 11px;
      border-style: solid dashed;
      border-color: yellow green;
    }
    /* 单值法 */
    .box1p4 {      
      border-width: 30px;
      border-style: dashed;
      border-color: greenyellow;
    }
    /* 只设置一条边的边框 */
    .top {
      border-top: 10px solid yellow;
    }

    .right {
      border-right: 11px dashed orange;
    }

    .bottom {
      border-bottom: 12px dotted pink;
    }

    .left {
      border-left: 13px groove indianred;
    }

    .box3p1 {
      border-top-color: gray;
      border-top-width: 10px;
      border-top-style: solid;
    }
    .box3p2 {
      border-right-color: yellowgreen;
      border-right-width: 20px;
      border-right-style: dashed;
    }
    .box3p3 {
      border-bottom-color: rgb(90, 110, 227);
      border-bottom-width: 30px;
      border-bottom-style: dotted;
    }
    .box3p4 {
      border-left-color: deeppink;
      border-left-width: 22px;
      border-left-style: double;
    }
  </style>
</head>
<body>
  <div class="box1">
    <h2>按照属性值的类型划分</h2>
    <p class="box1p1">border-width四值法</p>
    <p class="box1p2">border-width三值法</p>
    <p class="box1p3">border-width双值法</p>
    <p class="box1p4">border-width单值法</p>
  </div>

  <div class="box2">
    <!-- 类似于border -->
    <h2>根据边框的方向划分</h2>
    <p class="top">上边框设置</p>
    <p class="right">右边框设置</p>
    <p class="bottom">下边框设置</p>
    <p class="left">左边框设置</p>
  </div>

  <div class="box3">
    <h2>根据方向和类型，进一步细分</h2>
    <p class="box3p1">上边框的颜色、宽度和风格</p>
    <p class="box3p2">右边框的颜色、宽度和风格</p>
    <p class="box3p3">下边框的颜色、宽度和风格</p>
    <p class="box3p4">左边框的颜色、宽度和风格</p>

  </div>
  
</body>
</html>
```

#### 外边距margin

- 作用：设置的是盒子与盒子之间的距离。
- 特点：不能渲染背景
- 属性值：常用px为单位的数值。
- 外边距的设置方式与内边距 padding 一模一样的。	
   - 四值法<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667803966095-9e1ed4a9-0461-47d3-9899-f1bf9b42e8ae.png#averageHue=%23fed398&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=451&id=b4f2E&margin=%5Bobject%20Object%5D&name=image.png&originHeight=451&originWidth=251&originalType=binary&ratio=1&rotation=0&showTitle=false&size=16795&status=done&style=none&taskId=u788e5197-799f-48dd-9e45-29520c90690&title=&width=251)![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667803910030-d6b20e52-c58b-42f0-8421-ed3e4ca69ae3.png#averageHue=%23f9eddf&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=422&id=NHzGr&margin=%5Bobject%20Object%5D&name=image.png&originHeight=422&originWidth=273&originalType=binary&ratio=1&rotation=0&showTitle=false&size=18410&status=done&style=none&taskId=u21779c43-ae3e-4f86-9044-33714c769b7&title=&width=273)
   - 三值法<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667804001328-8c77aa99-aada-4664-9ab6-7657ba3b809f.png#averageHue=%23fed091&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=424&id=vdnwg&margin=%5Bobject%20Object%5D&name=image.png&originHeight=424&originWidth=262&originalType=binary&ratio=1&rotation=0&showTitle=false&size=15544&status=done&style=none&taskId=u540075a3-527b-4c02-947d-9895c240809&title=&width=262)![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667804021577-d4575f54-854b-4788-8515-3d089bc145ab.png#averageHue=%23f9ecde&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=438&id=ip89L&margin=%5Bobject%20Object%5D&name=image.png&originHeight=438&originWidth=260&originalType=binary&ratio=1&rotation=0&showTitle=false&size=20493&status=done&style=none&taskId=ua4e8c560-1042-486b-915d-0a168d3dda4&title=&width=260)
   - 双值法<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667804122691-1dda072a-df36-423c-865e-3a22702128aa.png#averageHue=%23faeee1&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=413&id=u29482950&margin=%5Bobject%20Object%5D&name=image.png&originHeight=413&originWidth=307&originalType=binary&ratio=1&rotation=0&showTitle=false&size=20240&status=done&style=none&taskId=u47b2bbeb-8915-4a91-b36c-4c6c979ceab&title=&width=307)![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667804140137-c286c747-155b-4631-b25b-863585e44b8d.png#averageHue=%23e0bc5e&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=117&id=u2b187c70&margin=%5Bobject%20Object%5D&name=image.png&originHeight=117&originWidth=235&originalType=binary&ratio=1&rotation=0&showTitle=false&size=3234&status=done&style=none&taskId=u520e6dc0-9155-48b8-9e98-2399a9b9ef4&title=&width=235)
   - 单值法<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667804159069-a1b89ba1-47ab-4aff-8ec0-bf7d53cb8611.png#averageHue=%23faeddf&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=436&id=u4a472baa&margin=%5Bobject%20Object%5D&name=image.png&originHeight=436&originWidth=275&originalType=binary&ratio=1&rotation=0&showTitle=false&size=18858&status=done&style=none&taskId=u415f2927-ab34-486b-abbc-5563e098b86&title=&width=275)![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667804181495-a2de2a13-63b0-4553-850f-555f6cd9aff1.png#averageHue=%230004fd&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=181&id=u67d67b1d&margin=%5Bobject%20Object%5D&name=image.png&originHeight=181&originWidth=179&originalType=binary&ratio=1&rotation=0&showTitle=false&size=1474&status=done&style=none&taskId=u518d3130-c305-4c4a-8b31-6afe32ab71d&title=&width=179)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>04-外边距margin</title>
  <style>
    /* 清楚默认样式 */
    body {
      border: 0;
      margin: 0;
    }

    .box,.box2 {
      float: left;
      width: 200px;
      height: 200px;
      border: 10px solid yellow;
      background-color: blue;
      /* 四值法设置margin */
      margin: 20px 30px 40px 50px;
    }

    .box2 {
      margin: 10px 50px 30px;
    }

    .box>p {
      margin: 20px 20px;
      background-color: red;
      border: 10px solid green;
    }

    .box2>p {
      margin: 50px;
      background-color: red;
      border: 10px solid green;
    }

  </style>
</head>
<body>
  <div class="box">
    <p>这是一段文字</p>
  </div>

  <div class="box2">
    <p>这是另一个文字</p>
  </div>
</body>
</html>
```
### 盒模型拓展应用
#### 清除默认样式

- 大部分标签都会有默认样式，在对页面进行布局的时候会有影响，为了避免这些影响需要清楚默认样式。
- 带有默认样式的标签：
   - 盒模型属性中内外边距，大部分容器级标签都有默认边距，可以通过标签选择器并集的方式或者通配符清除。<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667804515915-be52a4f4-abe6-4d45-b17e-9095a84c0308.png#averageHue=%23f9f8f6&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=289&id=u06d60172&margin=%5Bobject%20Object%5D&name=image.png&originHeight=289&originWidth=303&originalType=binary&ratio=1&rotation=0&showTitle=false&size=10737&status=done&style=none&taskId=u6beeddff-d188-4cc7-806b-6858ab64a12&title=&width=303)![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667804538108-6d0eb748-a2a3-431d-bd2f-ec1c14a25c52.png#averageHue=%23f7f6f4&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=209&id=u8779160f&margin=%5Bobject%20Object%5D&name=image.png&originHeight=209&originWidth=282&originalType=binary&ratio=1&rotation=0&showTitle=false&size=10012&status=done&style=none&taskId=u0e96b528-baca-4e87-abd4-626a1757ca2&title=&width=282)
   - ul和ol两种列表默认的列表前缀可以用list-style清除。<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667804629068-90d03583-08ce-4423-bbb7-2386b916d785.png#averageHue=%23faf9f7&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=205&id=u56db6914&margin=%5Bobject%20Object%5D&name=image.png&originHeight=205&originWidth=251&originalType=binary&ratio=1&rotation=0&showTitle=false&size=6023&status=done&style=none&taskId=u08070a7a-df2d-4f5d-8e1c-95f942af585&title=&width=251)
   - a标签的默认下划线和字体颜色可以用text-decoratio和color清除。<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667804689284-e6c3d9d0-0b54-49ee-a532-98fcb1adea90.png#averageHue=%23fefefd&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=35&id=u7b78d0cf&margin=%5Bobject%20Object%5D&name=image.png&originHeight=35&originWidth=210&originalType=binary&ratio=1&rotation=0&showTitle=false&size=1536&status=done&style=none&taskId=u8031ea60-9e93-492b-bb9c-3b5433e7151&title=&width=210)![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667804727322-fbb7beb2-eeca-4d9a-9127-37eb39d0071e.png#averageHue=%23eeeae6&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=25&id=u6ea89a60&margin=%5Bobject%20Object%5D&name=image.png&originHeight=25&originWidth=127&originalType=binary&ratio=1&rotation=0&showTitle=false&size=1167&status=done&style=none&taskId=u9c009da1-9f0b-4606-875f-39638c467fd&title=&width=127)
   - 清除标题标签的默认加粗效果可以使用font-weight。<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667804589939-83b246f8-8ad8-44eb-922c-f016ae49bce4.png#averageHue=%23f9f8f7&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=196&id=u6494439d&margin=%5Bobject%20Object%5D&name=image.png&originHeight=196&originWidth=233&originalType=binary&ratio=1&rotation=0&showTitle=false&size=6145&status=done&style=none&taskId=u60fcace9-5017-4c0b-8166-17e4400c21e&title=&width=233)
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>05-清除默认样式</title>
  <style>
    /* 清楚容器的默认样式 */
     .box,h2,ul,li,ol,a {
      border: 0;
      margin: 0;
    }

    h2{
      font-weight: normal;
    }

    ul,ol {
      list-style: none;
    }

    a {
      text-decoration: none;
      color: black;
    }
  </style>
</head>
<body>
  <div class="box">
    <h2>这是一个无序序列</h2>
    <ul>
      <li>1</li>
      <li>2</li>
      <li>3</li>
    </ul>

    <h2>这是一个有序序列</h2>
    <ol>
      <li>1</li>
      <li>2</li>
      <li>3</li>
    </ol>

    <a href="#">这是一个超链接</a>

  </div>
</body>
</html>
```
#### 高度height应用

- 根据不同的需求，高度属性可以设置也可以不设置。
- 如果设置了高度：盒子占有的高度位置就确定死了，后面的同级元素会紧挨着加载。
- 如果不设置高度：会根据标签内部内容高度自动撑开
- 以 <div> 标签为例，根据情况不同选择是否设置高度：
   - 如果设计图中盒子高度占位是固定的，后面同级元素在高度下面加载。自身盒子内部内容过多时会溢出盒子区域。<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667805203350-e7f2f1ec-f1a9-48fa-a81d-4b38585cdcf9.png#averageHue=%23ebcd83&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=163&id=uee49af4b&margin=%5Bobject%20Object%5D&name=image.png&originHeight=163&originWidth=327&originalType=binary&ratio=1&rotation=0&showTitle=false&size=9979&status=done&style=none&taskId=u427f6d7c-7070-4cd5-9132-b3b76d69a4d&title=&width=327)<br />可以通过一个溢出的属性 overflow，进行溢出部分内容的显示效果设置<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667615502685-8939a130-16a6-4d34-9bbe-0b7b5112d654.png#averageHue=%23f4f4f3&clientId=u1f2822ac-d613-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=280&id=ua9546572&margin=%5Bobject%20Object%5D&name=image.png&originHeight=308&originWidth=991&originalType=binary&ratio=1&rotation=0&showTitle=false&size=231631&status=done&style=none&taskId=u97d9c195-1ecf-452d-8035-eee7a3e20bc&title=&width=900.9090713824127)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667805246300-3cee1836-aaa8-4335-aba7-bb78ab9bdff6.png#averageHue=%23f4daad&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=176&id=uc25e0102&margin=%5Bobject%20Object%5D&name=image.png&originHeight=176&originWidth=339&originalType=binary&ratio=1&rotation=0&showTitle=false&size=5890&status=done&style=none&taskId=ue96a7a51-0a4e-4a4d-983d-3132d9c7661&title=&width=339)![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667805255417-63673d4e-78fd-44a6-9499-3d4ccd62fe80.png#averageHue=%23fbf5e1&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=200&id=u87190282&margin=%5Bobject%20Object%5D&name=image.png&originHeight=248&originWidth=423&originalType=binary&ratio=1&rotation=0&showTitle=false&size=19128&status=done&style=none&taskId=u8c0fa6fb-1f33-4feb-b0de-d4deec1821a&title=&width=341)
   - 必须不设置高度：要求盒子高度必须自适应内部内容的高度，或者设置height的属性值是自动的，这样不会随着内容的变多导致内容溢出盒子。<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667805374871-6062f187-216f-4447-9acf-45b6eeb30224.png#averageHue=%23f3f426&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=284&id=u8a7cc1b5&margin=%5Bobject%20Object%5D&name=image.png&originHeight=284&originWidth=318&originalType=binary&ratio=1&rotation=0&showTitle=false&size=14491&status=done&style=none&taskId=u02a71052-c9e6-4f05-8e6f-1778dec9f60&title=&width=318)
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>06-高度height应用</title>
  <style>
    div,p {
      border: 0;
      margin: 0;
    }

    .box {
      width: 300px;
      height: 100px;
      border: 10px solid red;
      background-color: yellow;
      overflow: scroll;
    }

    .box2{
      width: 300px;
      height: auto;
      background-color: #0ff;
    }
  </style>
</head>
<body>
  <div class="box">
    <p>这是一大段话这是一大段话这是一大段话这是一大段话这是一大段话
      这是一大段话这是一大段话这是一大段话这是一大段话这是一大段话这是一大段话
      这是一大段话这是一大段话这是一大段话这是一大段话这是一大段话这是一大段话
      这是一大段话这是一大段话这是一大段话这是一大段话
    </p>
  </div>
  <div class="box2">
    <p>这是另一大段话这是另一大段话这是另一大段话这是另一大段话这是另一大段话这是另一大段话这是另大段话
      这是另一大段话这是另一大段话这是另一大段话这是另一大段话这是另一大段话这是另一大段话这是另一大段话这是另一大段话这是另一大段话这是另一大段话这是另一大段话这是另一大段话这是另一大段话这是另一大段话
    </p>
  </div>
</body>
</html>
```
#### 居中
##### 文本水平居中

- 水平居中使用text-align属性，不论单行还是多行都可以设置，属性值设为center。<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667805691639-9d2cad31-d66c-4778-9532-381c7e5144f7.png#averageHue=%2300fefe&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=178&id=uc748038b&margin=%5Bobject%20Object%5D&name=image.png&originHeight=178&originWidth=407&originalType=binary&ratio=1&rotation=0&showTitle=false&size=1619&status=done&style=none&taskId=u6b8b2f91-9ffb-4c9d-aae2-d54ba48351c&title=&width=407)![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667805888262-13240dd8-85cd-46a7-8067-7eab5761ab6c.png#averageHue=%23fefbf9&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=140&id=u148a1df6&margin=%5Bobject%20Object%5D&name=image.png&originHeight=140&originWidth=241&originalType=binary&ratio=1&rotation=0&showTitle=false&size=6001&status=done&style=none&taskId=uf135b560-9ccd-4c87-af06-599632402bc&title=&width=241)
##### 文本垂直居中

- 单行文本垂直居中：让文字行高 line-height 等于盒子高度 height。<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667805836259-f2b4de01-549a-4f65-a892-db54e046bda7.png#averageHue=%2301fefe&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=170&id=u1bba7c12&margin=%5Bobject%20Object%5D&name=image.png&originHeight=170&originWidth=266&originalType=binary&ratio=1&rotation=0&showTitle=false&size=2036&status=done&style=none&taskId=u2ca14083-3f2f-4cc8-8755-b329a278a45&title=&width=266)![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667805869001-e934a6c0-0d72-4014-8594-ce8c1da7171e.png#averageHue=%23fefcfa&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=66&id=u61e80ab2&margin=%5Bobject%20Object%5D&name=image.png&originHeight=66&originWidth=253&originalType=binary&ratio=1&rotation=0&showTitle=false&size=2601&status=done&style=none&taskId=u13fe3e53-b49a-4269-953b-7d957e33f16&title=&width=253)
- 多行文本垂直居中：让元素高度自适应正好等于多行文字的高度，设置元素内边距上下值相同，这样上下的内边距会把文本挤到中间。<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667807385012-4ea814c9-72ba-44a6-bc04-73f0bdcd0851.png#averageHue=%23008d29&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=143&id=u0cab4028&margin=%5Bobject%20Object%5D&name=image.png&originHeight=143&originWidth=283&originalType=binary&ratio=1&rotation=0&showTitle=false&size=4117&status=done&style=none&taskId=u9ec82816-93cf-4605-beaf-55061a1b6d9&title=&width=283)![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667807399636-c61079bf-7698-4676-97e0-b932a2b5e313.png#averageHue=%23faf0e4&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=409&id=u7a7da60e&margin=%5Bobject%20Object%5D&name=image.png&originHeight=409&originWidth=262&originalType=binary&ratio=1&rotation=0&showTitle=false&size=17190&status=done&style=none&taskId=uc55c392f-ea3b-457e-9123-8886e076e80&title=&width=262)
##### 元素垂直居中
一个元素内部嵌套的子元素，在父元素中垂直居中

- 与多行文字类似，让父元素高度自适应，子元素高度自动撑开父级的高度，再给父元素设置相同的上下边距<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667808080935-3f1861b6-d9a9-483e-939c-7bbf74317481.png#averageHue=%23fea919&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=193&id=uc680d905&margin=%5Bobject%20Object%5D&name=image.png&originHeight=193&originWidth=364&originalType=binary&ratio=1&rotation=0&showTitle=false&size=2190&status=done&style=none&taskId=u1ea5957d-1bcc-45d0-a3eb-5bfc8da1868&title=&width=364)![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667808092729-26d63d26-96e9-4dcb-ad16-4dcb76844f1f.png#averageHue=%23fbf1e7&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=566&id=ub6f01402&margin=%5Bobject%20Object%5D&name=image.png&originHeight=566&originWidth=259&originalType=binary&ratio=1&rotation=0&showTitle=false&size=23772&status=done&style=none&taskId=ue87d1c76-afbe-42f3-a562-363a7f6d2c3&title=&width=259)
##### 元素水平居中

-  类似于div这种需要占据一行的盒子，如果子盒子的宽度低于父盒子的宽度，可以通过设置2个水平方向的外边距margin的值为auto实现水平居中。

原因：正常情况下，div占据一行是因为右边的margin会自动占满剩余的位置，当我们把左右2边的margin都设为auto后，就会自动平均分配左右的margin值。<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667808111306-3dd79c36-6ad8-4617-9bf0-5b6d0a136c41.png#averageHue=%2301e7d4&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=112&id=ueca40f84&margin=%5Bobject%20Object%5D&name=image.png&originHeight=159&originWidth=271&originalType=binary&ratio=1&rotation=0&showTitle=false&size=1024&status=done&style=none&taskId=u91251b7d-4007-4f27-86d8-1bb6654974c&title=&width=191)![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667808142798-93670e07-882c-43ed-a3a9-7546c5e012c0.png#averageHue=%23faf0e5&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=493&id=uca6b7f78&margin=%5Bobject%20Object%5D&name=image.png&originHeight=485&originWidth=252&originalType=binary&ratio=1&rotation=0&showTitle=false&size=19083&status=done&style=none&taskId=uf8cb61b5-60ad-4db7-8a61-880052f4ed8&title=&width=256)![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667808176374-48f57490-a86b-4cf7-b737-ae855a76abef.png#averageHue=%23fbf1e7&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=475&id=ue49728aa&margin=%5Bobject%20Object%5D&name=image.png&originHeight=546&originWidth=283&originalType=binary&ratio=1&rotation=0&showTitle=false&size=21800&status=done&style=none&taskId=u593ecae9-5538-4dbd-82ca-243dc6d6c52&title=&width=246)
#### 父子盒模

- 在父元素里放一个或多个子元素，而且多个子元素还要排一行显示的时候，必须保证父元素的宽度要足够（子元素的所有宽度加在一起不能大于父元素的宽度，即父元素的width>=所有子元素width+padding+border+margin），如果不满足则会溢出父元素，或者掉落到下一行。<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667810210826-15b62ce8-5c27-409a-bc16-d0306a9f0b16.png#averageHue=%238ecf46&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=121&id=u8db9a010&margin=%5Bobject%20Object%5D&name=image.png&originHeight=121&originWidth=867&originalType=binary&ratio=1&rotation=0&showTitle=false&size=1978&status=done&style=none&taskId=uf55e3b87-a3a2-4a5b-8cdc-2ba50ad9c93&title=&width=867)![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667810259004-0168c0d3-5900-4dfd-9657-aaeb489389e3.png#averageHue=%23fef9f7&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=102&id=u4e520a0b&margin=%5Bobject%20Object%5D&name=image.png&originHeight=102&originWidth=262&originalType=binary&ratio=1&rotation=0&showTitle=false&size=5547&status=done&style=none&taskId=u2891c128-d215-4edf-a4f9-630c52fc375&title=&width=262)<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667810235159-166b3d1e-cb40-442c-bbef-8c867a2ef06d.png#averageHue=%238ace40&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=180&id=uc6f429f7&margin=%5Bobject%20Object%5D&name=image.png&originHeight=180&originWidth=845&originalType=binary&ratio=1&rotation=0&showTitle=false&size=2408&status=done&style=none&taskId=u6fa3fd1b-e81a-44ca-ae9a-ee8200775a8&title=&width=845)![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667810244794-2f66f35f-4d0c-427a-ba21-c59d5e506efc.png#averageHue=%23fefaf8&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=131&id=udf9e6d02&margin=%5Bobject%20Object%5D&name=image.png&originHeight=131&originWidth=325&originalType=binary&ratio=1&rotation=0&showTitle=false&size=7665&status=done&style=none&taskId=u07f28405-2970-428c-8e7f-2b705ce6c95&title=&width=325)
   - 一个元素的溢出情况<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667811205802-94907d88-d108-41c6-a911-dfaf68b111d3.png#averageHue=%23e5f33d&clientId=u006fdd94-e84a-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=122&id=u977af93e&margin=%5Bobject%20Object%5D&name=image.png&originHeight=122&originWidth=327&originalType=binary&ratio=1&rotation=0&showTitle=false&size=1273&status=done&style=none&taskId=uf7c4f6f0-5bac-40af-84fa-18483910030&title=&width=327)
- 解决办法：
   - 针对多行的，计算或量取尺寸时一定要计算准确，一像素都不能偏差。
   - 父子盒模型中，只有一个子元素，且子元素是类似 <div>，p 标签必须占一行的，可以不设置子元素的宽度（子元素的宽度会自动撑满父元素），当我们去修改padding、bording和margin的时候，会自动修改width的长度，从而实现总的宽度等于父元素的宽度。
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>08-父子盒模型</title>
  <style>
    div,p {
      border: 0;
      margin: 0;
    }

    .box {
      height: 100px;
      width: 1000px;
      background-color: aquamarine;

    }
    /* 如果要在一行显示，最终宽度不能超过父盒子 */
    .demo1 {
      margin-right: 50px ;
      float: left;
      background-color: yellowgreen;
      width: 200px;
      height: 100px;
    }

    .box2 {
      background-color: aquamarine;
      width: 300px;
      height: 100px;
      border: 10px solid red;
    }

    /* 不设置宽度，添加水平方向的padding和margin或者border时盒模型会自动对宽度修改 */
    .box2 p {
      /*  width: 300px; */
      height: 100px; 
      border: 10px dashed yellow;
      padding: 0 20px;
      margin: 0 20px;
      background-color: pink;
    }
  </style>
</head>
<body>
  <div class="box">
    <div class="demo1">1</div>
    <div class="demo1">2</div>
    <div class="demo1">3</div>
    <div class="demo1">4</div>
  </div>

  <div class="box2">
    <p>5</p>
  </div>
</body>
</html>
```
#### margin塌陷现象

- 上面的元素有下边距，下面的元素有上边距，两个边距相遇，真正的盒子间距离是较大的那个值，小的那个会塌陷在大的里面。<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667828812205-ca14e9b8-16d9-4a7d-a66a-cc17d53c0548.png#averageHue=%23e7d9ab&clientId=ucfe23c97-168d-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=336&id=u66d0aa9f&margin=%5Bobject%20Object%5D&name=image.png&originHeight=370&originWidth=259&originalType=binary&ratio=1&rotation=0&showTitle=false&size=2865&status=done&style=none&taskId=u1165fa71-aaae-4b2b-af85-3206852ce20&title=&width=235.45454035120574)![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667828827919-278e9859-ebdf-40b1-8d7d-2fb8fa407196.png#averageHue=%23fdf8e6&clientId=ucfe23c97-168d-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=346&id=uf7466376&margin=%5Bobject%20Object%5D&name=image.png&originHeight=381&originWidth=238&originalType=binary&ratio=1&rotation=0&showTitle=false&size=2766&status=done&style=none&taskId=u9d93e291-2dd7-4256-b7cc-022aa672e11&title=&width=216.36363167408095)![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1667828875068-8ea90063-4239-4bad-8a8b-11109fce24ab.png#averageHue=%23fefaf6&clientId=ucfe23c97-168d-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=399&id=u6c064ff9&margin=%5Bobject%20Object%5D&name=image.png&originHeight=439&originWidth=1662&originalType=binary&ratio=1&rotation=0&showTitle=false&size=59331&status=done&style=none&taskId=u09985285-80a0-4d87-a3e5-f1f876b5969&title=&width=1510.909058161019)
- 父子元素塌陷，父元素和子元素都设置了同方向的margin-top 值，两个属性之间没有其他的内容进行隔离，导致两个属性相遇，发生margin 塌陷
- 本身父元素与上一个元素的距离是0，子元素如果设置了垂直方向的上边距，会带着父级一起掉下来，间隔为子元素的margin。
- 解决 margin 塌陷问题的方法：
   - 同级元素：如果两个元素垂直方向有间距，只需要设置给一个元素，不要进行拆分。
   - 父子元素：让两个边距不要相遇，中间可以使用父元素 border 或 padding 将边距分隔开；<br />更加常用方法，父子盒模型之间的距离就不要用儿子的 margin 去踹出来，而是父级的 padding 挤出来
- 水平方向的 margin 没有塌陷现象。
## 标准文档流
### 标准文档流定义

- 标准文档流，指的是元素排版布局过程中，元素会默认自动从左往右，从上往下的流式排列方式。前面内容发生了变化，后面的内容位置也会随着发生变化。
- HTML就是一种标准文档流文件。
- HTML中的标准文档流特点通过两种方式体现：微观现象和元素等级。
### 微观现象

1. 空白折叠现象
2. 文字类的元素如果排在一行会出现一种高低不齐、底边对齐效果。
3. 自动换行，元素内一行内容写满元素的 width 时会自动进行换行。
### 元素等级

- 在标准流中，大部分元素是区分等级的，习惯将元素划分为几种常见的加载级别：块级元素、行内元素、行内块元素等。
- 块级元素：大部分容器级标签（标签内部可以包含不仅仅是文字元素的标签）包括p标签都是块级元素，比如<div>、<h1>。
- 行内元素：大部分的文本级标签，比如 <span>、<a>、<b> 等。
- 行内块元素：行内元素具有块级特性比如 <img>、<input> 等。
- 各种等级的元素有自己的加载特点。
#### 块级元素

- 块级元素可以设置宽高，在浏览器中正常加载。
- 块级元素必须独占一行，不能与其他任何标签并排一行。
- 块级元素如果不设置宽度，会自动撑满父级的 width 区域；高度不设置，会被内容自动撑开高度。
#### 行内元素

- 行内元素不能正常加载宽度和高度属性，其他的盒模型属性虽然能设置，但是容易出现加载问题。
- 行内元素可以与其他的行内或行内块元素并排一行显示。
- 行内元素不论是否设置宽高，宽度和高度都只能被内容自动撑开。内容得是文字内容，不可以是子标签元素。
#### 行内块元素

- 行内块元素可以设置宽度和高度，如图片标签img。
- 行内块元素可以与其他的行内或行内块并排一行显示。
- 行内块元素如果不设置宽高，要么以原始尺寸加载要么被内容自动撑开。
- 行内块依旧具有标准流的微观性质，例如空白折叠现象。<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1668532039792-e504852c-9d16-44a2-8211-9009ed6bec57.png#averageHue=%23c3c3b8&clientId=uc0a9d1e6-3324-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=238&id=u9631e07c&margin=%5Bobject%20Object%5D&name=image.png&originHeight=262&originWidth=659&originalType=binary&ratio=1&rotation=0&showTitle=false&size=87229&status=done&style=none&taskId=u2e8aa6f6-9bbd-41e2-9e37-53ceb68f582&title=&width=599.0908961059636)
### CSS显示模式样式

- 显示模式的样式为display，可以通过更改display属性来更改标签的加载模式。
- 属性值：元素根据属性值不同，可以加载对应元素等级的显示模式的特点。<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1668561597087-4f5c3317-4a2c-4b72-8f43-c81ffb7674c2.png#averageHue=%23efefee&clientId=u1868518c-38d2-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=429&id=ubcf3b4a3&margin=%5Bobject%20Object%5D&name=image.png&originHeight=429&originWidth=994&originalType=binary&ratio=1&rotation=0&showTitle=false&size=80719&status=done&style=none&taskId=u68165577-704f-4739-acf8-9bcb3753a03&title=&width=994)
   - 改变前：<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1668669404306-9810e707-1078-4531-887b-bea935465f5f.png#averageHue=%23fdd5d4&clientId=u8d0fea58-d09c-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=119&id=u42dc6a78&margin=%5Bobject%20Object%5D&name=image.png&originHeight=119&originWidth=678&originalType=binary&ratio=1&rotation=0&showTitle=false&size=4802&status=done&style=none&taskId=u72d49298-a22c-47a0-be93-67b1a5703d8&title=&width=678)
   - 改变后：<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1668669693635-401cf031-e180-467a-9bb3-660bf500d754.png#averageHue=%23a3c72c&clientId=u263e574c-0e8e-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=62&id=u245d4cc5&margin=%5Bobject%20Object%5D&name=image.png&originHeight=62&originWidth=673&originalType=binary&ratio=1&rotation=0&showTitle=false&size=2232&status=done&style=none&taskId=uc3d4429f-f39b-430d-b1c7-31bd0c2eebb&title=&width=673)
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>display样式</title>
  <style>
    div,p,span{
      margin: 0;
      padding: 0;
    }
    p {
      background-color: aqua;

    }

    .box {
      background-color: red;
      border: 1px solid blue;
    }

		/*给span标签的display样式值为block*/
    ._span {
      background-color: yellowgreen;
      border: 1px solid orange;
      display: block;
    }
  </style>
</head>
<body>
  <div class="box">
    <p>这是一段话</p>
    <span class="_span">这是span</span>
  </div>
</body>
</html>
```
### 脱离标准流

- display 属性更改的显示模式并没有改变标准流本质性质，页面还是只能从上往下加载，存在空白折叠现象等微观性质。要想实现更多的界面布局效果需要脱离标准流的限制。
- 标签元素脱离标准流的方法包括：浮动、绝对定位、固定定位。
## CSS浮动
### 浮动定义

- 浮动是一种非常重要的布局属性。
- 属性名：float，漂流、浮动的意思。
- 属性值：
   - left：左浮动
   - right：右浮动
- 作用：让元素脱离标准流，同一级的浮动的元素可以并排在一排显示。
### 浮动的性质
#### 浮动的元素脱离标准流

- 设置了浮动属性的元素脱离了标准流的限制，具有行块二象性，可以设置宽高并且可以并排一行。
- 不会有空白折叠现象。
- 如果元素不设置宽高，可以被元素内容自动撑开。
#### 浮动的元素依次贴边

- 根据设置的浮动值不同，进行布局的时候加载位置的方向不同。
- 以left为例，父子元素都设置了浮动属性，如果父元素宽度足够，所有子元素会按照HTML书写顺序，依次向左进行贴边，父元素左边←子元素1←子元素2← 子元素3←子元素4。
   - 浮动前：<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1668670504182-e135ffca-b86c-4160-a0b4-8cbd734d0815.png#averageHue=%23f5debf&clientId=u263e574c-0e8e-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=350&id=u3f793409&margin=%5Bobject%20Object%5D&name=image.png&originHeight=350&originWidth=827&originalType=binary&ratio=1&rotation=0&showTitle=false&size=2619&status=done&style=none&taskId=u5bdd4ffb-2855-4255-9a8f-86402db7de9&title=&width=827)
   - 浮动后：<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1668670930214-6f567100-d817-4d6b-a79c-c1a93f374e92.png#averageHue=%23e7ccac&clientId=u263e574c-0e8e-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=153&id=u0cb267e9&margin=%5Bobject%20Object%5D&name=image.png&originHeight=153&originWidth=1042&originalType=binary&ratio=1&rotation=0&showTitle=false&size=2050&status=done&style=none&taskId=u4e58adc6-1fea-40b6-8e16-c335fa59243&title=&width=1042)
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>浮动贴边</title>
  <style>
    div {
      margin: 0;
      padding: 0;
    }
		/*父元素和子元素一样都得添加浮动，子元素才能在父元素里贴边*/
    .fbox {
      background-color: blanchedalmond;
      border: 5px solid ;
      width: 1000px;
      float: left;
    }

    .box1 {
      float: left;
      width: 100px;
      height: 100px;
      background-color: red;
      border: 1px solid ;
    }
    .box2 {
      float: left;
      width: 100px;
      height: 100px;
      background-color: yellow;
      border: 1px solid ;
    }
    .box3 {
      float: left;
      width: 100px;
      height: 100px;
      background-color: blue;
      border: 1px solid ;
    }
    .box4 {
      float: left;
      width: 100px;
      height: 100px;
      background-color: green;
      border: 1px solid ;
    }
  </style>
</head>
<body>
  <div class="fbox">
    <div class="box1">1</div>
    <div class="box2">2</div>
    <div class="box3">3</div>
    <div class="box4">4</div>
  </div>
</body>
</html>
```

   - 父元素宽度如果不够，例如不能放下一个子元素4，那么子元素4在贴边时，会跳过上一个子元素3，向更上一个子元素2进行贴边，如果子元素2后面位置不够，继续跳过子元素2向前面的子元素1进行贴边。
      - 位置不够：<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1668671317524-57b1a3c7-5eed-46ba-ba9e-7ff8b0bd1167.png#averageHue=%23f1c4a5&clientId=u263e574c-0e8e-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=364&id=u3db086ae&margin=%5Bobject%20Object%5D&name=image.png&originHeight=364&originWidth=596&originalType=binary&ratio=1&rotation=0&showTitle=false&size=3152&status=done&style=none&taskId=u8fc1ca92-ba05-4229-8ba0-c412c63c53f&title=&width=596)
```css
 div {
      margin: 0;
      padding: 0;
    }
		/*修改父元素宽度  */
    .fbox {
      background-color: blanchedalmond;
      border: 5px solid ;
      width: 405px;
      float: left;
    }
		/*增高第一个子元素给第4个子元素贴边*/
    .box1 {
      float: left;
      width: 100px;
      height: 300px;
      background-color: red;
      border: 1px solid ;
    }
		/*增高第二个子元素*/
    .box2 {
      float: left;
      width: 100px;
      height: 180px;
      background-color: yellow;
      border: 1px solid ;
    }
    .box3 {
      float: left;
      width: 100px;
      height: 100px;
      background-color: blue;
      border: 1px solid ;
    }

		/*
			第四个子元素宽度增加，贴在第二个子元素时超过父元素宽度
      第四个子元素就会贴第一个子元素的边
		*/
    .box4 {
      float: left;
      width: 200px;
      height: 100px;
      background-color: green;
      border: 1px solid ;
    }
```

      - 位置够：<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1668671688400-821c369b-4b51-4e12-9508-25772281c568.png#averageHue=%23fef188&clientId=u263e574c-0e8e-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=334&id=ue4c9af3e&margin=%5Bobject%20Object%5D&name=image.png&originHeight=334&originWidth=456&originalType=binary&ratio=1&rotation=0&showTitle=false&size=2715&status=done&style=none&taskId=u002880c2-05f5-4cb8-9256-b0033ab69fe&title=&width=456)
```css
/*第二个元素后面的宽度足够放下第四个元素的时候，第四个元素就会跟第二个元素贴边  */
.box4 {
      float: left;
      width: 199px;
      height: 100px;
      background-color: green;
      border: 1px solid ;
    }
```

   - 如果子元素4在跳过子元素3向更前面的子元素2贴边时，子元素2的高度不高于子元素3，子元素2没有延伸出一个高度的边让子元素4贴边，那么子元素4就会跳过子元素2向子元素1进行贴边。
```css
/*box2的高度为100跟box3和4一样，box4无法贴边，于是就贴到box1那里了*/
.box2 {
  float: left;
  width: 100px;
  height: 100px;
  background-color: yellow;
  border: 1px solid ;
}
```

   - 如果贴边的这个子元素4宽度小于子元素2，子元素2的高度低于子元素1和子元素3，形成一个凹陷，子元素4会受前面子元素3高度影响，不会出现钻空现象。<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1668672014930-cbbdd786-3267-4b6d-a9b7-4c6b6c836d85.png#averageHue=%23eeb798&clientId=u263e574c-0e8e-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=353&id=ue6e7ad44&margin=%5Bobject%20Object%5D&name=image.png&originHeight=353&originWidth=558&originalType=binary&ratio=1&rotation=0&showTitle=false&size=3100&status=done&style=none&taskId=u85415ec8-c71d-48a0-ab97-a415b134402&title=&width=558)
```css
/*先把父元素的宽度调大，给元素2的宽度调整流出空间  */
.fbox {
      background-color: blanchedalmond;
      border: 5px solid ;
      width: 500px;
      float: left;
    }

    .box1 {
      float: left;
      width: 100px;
      height: 300px;
      background-color: red;
      border: 1px solid ;
    }
/*把元素2的宽度调整为比元素4大  */
    .box2 {
      float: left;
      width: 220px;
      height: 50px;
      background-color: yellow;
      border: 1px solid ;
    }
    .box3 {
      float: left;
      width: 100px;
      height: 100px;
      background-color: blue;
      border: 1px solid ;
    }
    .box4 {
      float: left;
      width: 199px;
      height: 100px;
      background-color: green;
      border: 1px solid ;
    }
```

   - 如果子元素1后面的距离也放不下子元素4，子元素4最终会贴到父元素左边，如果子元素4的宽度超过了父元素，只会出现溢出现象。<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1668672379035-b0c33e04-3be8-4808-bfd1-bb571922a9af.png#averageHue=%23feefa1&clientId=ufa26ec83-85b7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=439&id=u07d3cade&margin=%5Bobject%20Object%5D&name=image.png&originHeight=439&originWidth=545&originalType=binary&ratio=1&rotation=0&showTitle=false&size=2630&status=done&style=none&taskId=u1b388a77-76b4-4f35-90d0-01765789a9e&title=&width=545)![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1668672453644-8d38d648-06af-4ad4-b2d4-c0f42dbf5ebf.png#averageHue=%23feef9f&clientId=ufa26ec83-85b7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=440&id=u92a57494&margin=%5Bobject%20Object%5D&name=image.png&originHeight=440&originWidth=618&originalType=binary&ratio=1&rotation=0&showTitle=false&size=2810&status=done&style=none&taskId=uabd68a2d-7340-497f-be78-fa044763ad6&title=&width=618)
```css
.box1 {
  float: left;
  width: 100px;
  height: 300px;
  background-color: red;
  border: 1px solid ;
}
.box2 {
  float: left;
  width: 120px;
  height: 200px;
  background-color: yellow;
  border: 1px solid ;
}
/*没超父元素*/
.box4 {
  float: left;
  width: 459px;
  height: 100px;
  background-color: green;
  border: 1px solid ;
}

/*超过父元素，就会溢出  */
.box4 {
  float: left;
  width: 559px;
  height: 100px;
  background-color: green;
  border: 1px solid ;
}
```

- 右浮动与左浮动贴边效果是一致的，只是贴边方向不同。按照 HTML 书写顺序依次向右向上一个元素贴边，第一个元素贴父元素的右边。<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1668672634874-32f822e7-8e62-449a-902b-1c02c3b97aab.png#averageHue=%23eeddc9&clientId=ufa26ec83-85b7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=143&id=u2784dcc3&margin=%5Bobject%20Object%5D&name=image.png&originHeight=143&originWidth=1695&originalType=binary&ratio=1&rotation=0&showTitle=false&size=2750&status=done&style=none&taskId=uc571954f-e025-4bb4-867a-9b5ac787774&title=&width=1695)
- 案例：利用浮动依次贴边的性质，用列表结构模拟平均分布的表格布局结构。![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1668674747208-7a73be1d-0882-4c21-b185-96887d782725.png#averageHue=%2386bfa3&clientId=ufa26ec83-85b7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=150&id=ua1d93062&margin=%5Bobject%20Object%5D&name=image.png&originHeight=150&originWidth=445&originalType=binary&ratio=1&rotation=0&showTitle=false&size=2788&status=done&style=none&taskId=ud6d392d1-f307-4814-98bf-aacf803cb7a&title=&width=445)
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>浮动表格布局结构练习</title>
  <style>
    div,ul,li {
      margin: 0;
      padding: 0;
    }

    ul {
      list-style: none;
      width: 408px;
      height: 126px;
      background-color: red;
      padding-top: 2px;
      padding-left: 2px;
    }

    li {
      float: left;
      text-align: center;
      width: 100px;
      height: 40px;
      background-color: skyblue;
      margin: 0 2px 2px 0;
    }

  </style>
</head>
<body>
  <div class="box">
    <ul>
      <li>1</li>
      <li>2</li>
      <li>3</li>
      <li>4</li>
      <li>5</li>
      <li>6</li>
      <li>7</li>
      <li>8</li>
      <li>9</li>
      <li>10</li>
      <li>11</li>
      <li>12</li>
    </ul>
  </div>
</body>
</html>
```

- 同一个盒子中，可以有左浮动和右浮动的子盒子并存，子盒子会根据浮动方向，向上一个同方向的子盒子进行贴边，如果空间不够，也会发生之前依次贴边的各种情况。<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1668674916580-6985d114-ae98-43fb-bbf9-29c8e1f93416.png#averageHue=%237f9666&clientId=ufa26ec83-85b7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=143&id=uf68f0b4a&margin=%5Bobject%20Object%5D&name=image.png&originHeight=143&originWidth=616&originalType=binary&ratio=1&rotation=0&showTitle=false&size=3302&status=done&style=none&taskId=u6dc7d42e-fa90-485f-ac2b-00a11ff8f28&title=&width=616)
```css
ul {
  list-style: none;
  width: 608px;
  height: 126px;
  background-color: red;
  padding-top: 2px;
  padding-left: 2px;
}

li {
  float: left;
  text-align: center;
  width: 100px;
  height: 40px;
  background-color: skyblue;
  margin: 0 2px 2px 0;
}

.fr {
  float: right;
}
```
#### 贴边性质应用

- 利用浮动的这个依次贴边性质，可以完成多种网页布局效果。例如：
   - 上述平均分布表格效果。
   - 导航栏效果。
   - 常见的电商或企业网站布局。

练习：绘制出如图效果<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1668606567632-c31e3998-8902-4ec5-ae0f-6acacd54d7a5.png#averageHue=%237295b5&clientId=u567a56dc-b07c-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=455&id=u21d7cb64&margin=%5Bobject%20Object%5D&name=image.png&originHeight=500&originWidth=1042&originalType=binary&ratio=1&rotation=0&showTitle=false&size=76224&status=done&style=none&taskId=udc7944c2-c4ce-4ab2-a0fe-228a457e47a&title=&width=947.2727067411442)![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1668676740234-d94e5918-cba6-494c-ab8b-67c50b9420d6.png#averageHue=%2387ceeb&clientId=ufa26ec83-85b7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=507&id=u4bda4c6a&margin=%5Bobject%20Object%5D&name=image.png&originHeight=507&originWidth=1002&originalType=binary&ratio=1&rotation=0&showTitle=false&size=3956&status=done&style=none&taskId=ucbe473e3-4e0b-42d6-86fa-844bded3b9c&title=&width=1002)
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>04-浮动贴边练习4</title>
  <style>
    div {
      margin: 0;
      padding: 0;
    }

    .box {
      padding: 10px;
      width: 960px;
      height: 460px;
      border: 1px solid;
    }

    .box1 {
      width: 300px;
      height: 260px;
      background-color: rgb(255, 131, 203);
      float: left;
    }

    .box2 {
      width: 240px;
      height: 260px;
      background-color: skyblue;
      float: left;
    }

    .box3 {
      float: left;
      background-color: yellow;
      width: 200px;
      height: 130px;
    }

    .box4 {
      float: left;
      background-color: rgb(150, 226, 109);
      width: 200px;
      height: 130px;
    }
    .box5 {
      float: left;
      background-color: rgb(150, 226, 109);
      width: 200px;
      height: 130px;
    }
    .box6 {
      float: left;
      background-color: yellow;
      width: 200px;
      height: 130px;
    }

    .box7 {
      float: left;
      width: 300px;
      height: 180px;
      background-color: rgb(158, 199, 249);
    }

    .box8 {
      background-color: rgb(242, 39, 242);
      float: left;
      width: 160px;
      height: 180px;
    }
    .box9 {
      background-color: rgb(182, 241, 63);
      float: left;
      width: 160px;
      height: 180px;
    }
    .box10 {
      background-color: rgb(242, 39, 242);
      float: left;
      width: 160px;
      height: 180px;
    }
    .box11 {
      background-color: rgb(182, 241, 63);
      float: left;
      width: 160px;
      height: 180px;
    }

    

  </style>
</head>
<body>
  <div class="box">
    <div class="box1"></div>
    <div class="box2"></div>
    <div class="box3"></div>
    <div class="box4"></div>
    <div class="box5"></div>
    <div class="box6"></div>
    <div class="box7"></div>
    <div class="box8"></div>
    <div class="box9"></div>
    <div class="box10"></div>
    <div class="box11"></div>
  </div>
</body>
</html>
```

#### 浮动的元素没有margin塌陷

- margin 塌陷现象出现在标准流中的，浮动元素已经脱离标准流，不再具有 margin塌陷现象。
#### 浮动的元素让出标准流位置

- 元素浮动之后，脱离了标准流，会将原来占有的标准流位置让给后面的一个同级元素。
#### 字围现象

- 同级元素中前面的元素浮动，后面的元素不浮动，不浮动的元素内部还有一些文字，浮动的蓝盒子会压盖住粉盒子的一部分，但是文字内容不会被盖住，粉盒子中的文字会让开蓝盒子位置，围绕它进行加载。
- 可以利用字围现象制作一些特殊的图文混排布局效果![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1668762571793-d7ddad01-7ffe-4cbc-ab29-9fe6cc168b23.png#averageHue=%23c9c4bc&clientId=u5d3d4b67-dcf3-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=436&id=u3d8a3a5f&margin=%5Bobject%20Object%5D&name=image.png&originHeight=436&originWidth=530&originalType=binary&ratio=1&rotation=0&showTitle=false&size=174359&status=done&style=none&taskId=u2f24e963-85f2-4c5c-a44b-a4c2517cea8&title=&width=530)
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>05-字围现象</title>
  <style>
    div {
      margin: 0;
      padding: 0;
    }

    .content {
      border: 1px solid;
      width: 500px;
      /* float: left;   */
    }

    .para {
      width: 500px;
    }


    .image {
      float: left;
    }


  </style>
</head>
<body>
  <div class="content">
    <!-- 图片要在文字的上面，这样图片浮动后，下面的文字才能围上去 -->
    <img class="image" src="../images/围龙屋.jpg" alt="围龙屋">
    <p class="para">
      围龙屋是一种客家人独有的围楼形态建筑，其分布范围非常广泛，只要在客家人聚居之处，都能够见到围龙屋的踪迹，包括在中国大陆南方的广东省、福建省、江西省南部，台湾中南部的屏东、云林、台中市东势，以至马来西亚和新加坡都有踪影。客家人为了适应当地环境和气候、满足其生活需要，形成了集合了卧房、大院、厨房、练功房、武器库、庭院、牌位室、神龛等多种功能的客家民居，是客家文化中的特色建筑，也是福建围楼这一建筑概念中数量最多的样式。围龙屋始见于宋元、成熟于明末和清朝、鼎盛于中华民国大陆时期。狭义的围龙屋特指的是围龙式的围屋，而广义的围龙屋可以指各式的客家围楼或围屋。广义上的围龙屋的外形基本分同心圆形、半圆形和方形三种，此外也有椭圆形状的。围龙屋在中国大陆被称作“中国五大民居特色建筑之一”。
    </p>
  </div>
</body>
</html>
```
### 浮动的问题
#### 浮动的问题1

- 内部浮动的子元素不可以自动撑高标准流父亲的宽高。![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1668790038917-ffbfe785-eeb7-4a4f-a8ea-4228c6520429.png#averageHue=%23b3c1a2&clientId=u7c5cfa18-af1f-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=218&id=ud6a20268&margin=%5Bobject%20Object%5D&name=image.png&originHeight=240&originWidth=542&originalType=binary&ratio=1&rotation=0&showTitle=false&size=1777&status=done&style=none&taskId=u875fcd88-d8db-4c7d-a4e4-3e9e9f1ce7d&title=&width=492.7272620476969)![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1668791871926-8a89ce96-3911-46c8-93a6-39bc3bb5b018.png#averageHue=%23faedae&clientId=u7c5cfa18-af1f-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=144&id=u8124403c&margin=%5Bobject%20Object%5D&name=image.png&originHeight=158&originWidth=647&originalType=binary&ratio=1&rotation=0&showTitle=false&size=1348&status=done&style=none&taskId=u7a9c8a16-ac26-4d6e-bf7e-f8d400bf8b0&title=&width=588.1818054333208)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>06-浮动的问题</title>
  <style>
    div {
      margin: 0;
      padding: 0;
    }

    .box {
      width: 500px;
      background-color: skyblue;
      border: 10px solid red;
    }

    .para {
      background-color: bisque;
      width: 300px;
      float: left;
    }


  </style>
</head>
<body>
  <div class="box">
    <p class="para">
      我是一段话，我是一段话，我是一段话，我是一段话，我是一段话，我是一段话，我是一段话，我是一段话，我是一段话，我是一段话，我是一段话，我是一段话，我是一段话，我是一段话，我是一段话，我是一段话，我是一段话，我是一段话，我是一段话，我是一段话，我是一段话，我是一段话，我是一段话，我是一段话，我是一段话，我是一段话，我是一段话，我是一段话
    </p>
  </div>
</body>
</html>
```
#### 浮动的问题2

- 父元素没有高度，会影响后面元素的标准流位置（后面的标准流会贴着父元素标准流，子元素浮动会影响到），如果浮动的子元素足够高时，有可能影响到后面浮动元素的贴边<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1668791857122-d2c1ba66-11dc-434d-9607-1e6acd0006b4.png#averageHue=%23fddfdf&clientId=u7c5cfa18-af1f-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=257&id=u6201ab6c&margin=%5Bobject%20Object%5D&name=image.png&originHeight=283&originWidth=2226&originalType=binary&ratio=1&rotation=0&showTitle=false&size=4231&status=done&style=none&taskId=ucef65bdf-a587-489c-8eb9-eb377b5323c&title=&width=2023.6363197752275)
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>06-浮动的问题</title>
  <style>
    div {
      margin: 0;
      padding: 0;
    }

    .box {
      /* width: 508px; */
      background-color: skyblue;
      border: 10px solid red;
    }

    .box1 {
      width: 125px;
      height: 50px;
      background-color: yellow;
      border: 1px solid;
      float: left;
    }


  </style>
</head>
<body>
  <div class="box">
    <div class="box1"></div>
    <div class="box1"></div>
    <div class="box1"></div>
    <div class="box1"></div>
  </div>

  <!-- 父元素后面的另一个标准流元素 -->
   <div class="box">
    <div class="box1"></div>
    <div class="box1"></div>
    <div class="box1"></div>
    <div class="box1"></div>
   </div>
</body>
</html>
```

### 清除浮动影响的方法

- 如果父元素高度是固定的，建议使用 height 属性解决，如果父元素有固定的高度，紧靠父元素的下一个标准流就不会被子元素浮动影响，因为子元素完全被父元素包裹。。
```css
.box {
  /* width: 508px; */
﻿
  background-color: skyblue;
  border: 10px solid red;
/*   给父元素一个高度，让子元素都在你父元素之中 */
  height: 50px;
}
```

- 如果父元素高度需要自适应，建议使用 overflow 属性解决浮动问题。![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1668792121177-18fa48a2-6b0b-44e2-9a31-818e26cdf3a1.png#averageHue=%23c9db6a&clientId=u7c5cfa18-af1f-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=970&id=u4eb2ac5b&margin=%5Bobject%20Object%5D&name=image.png&originHeight=1067&originWidth=951&originalType=binary&ratio=1&rotation=0&showTitle=false&size=9345&status=done&style=none&taskId=u2d74ccc6-2303-4e35-9668-d4ecca7ca4b&title=&width=864.5454358069369)
```css
.box {
      /* width: 508px; */
      background-color: skyblue;
      border: 10px solid red;
			/*设置overflow属性为hidden，可以*/
      overflow: hidden;
    }

    .box1 {
      width: 125px;
      /* 高度改为500也能自适应 */
      height: 500px;
      background-color: yellow;
      border: 1px solid;
      float: left;
    }
```

## 背景属性

- CSS属性除了布局属性外，还需要添加一些背景类的内容来让网页变的更加美观。
- CSS中通过background属性来设置背景，background属性是一个综合属性，可以拆分成多个单一属性。
### 设置背景颜色

- 属性名：background-color
- 作用：在盒子区域添加背景颜色的修饰。
- 加载区域：在border及以内加载背景颜色，包括padding。
- 属性值：颜色名、颜色值（rgb、rgba）。
### 背景图片

- 属性名：background-image
- 作用：给盒子添加图片作为背景。
- 加载范围：默认的加载到边框及以内部分。如果图片不重复加载，加载从border 以内开始。
- 属性值：url(图片路径)
- 背景图可以和背景颜色同时设置，背景图片会压盖背景的颜色，没有背景图的区域会显示背景颜色。
- 一个盒子上可以添加多个背景图片，以逗号分隔多背景的 URL路径地址。
- 背景加载时，先写的背景压盖后写的背景图片
### 背景重复

- 属性名background-repeat
- 作用：设置添加的背景图是否要在盒子中重复进行加载。
- 属性值：根据属性值不同，有四种加载方式<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1669387197771-7ff4d925-aa27-42d8-82ad-2397e39945de.png#averageHue=%23efeeee&clientId=u05ba6b6b-e85b-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=405&id=u4a86fedb&margin=%5Bobject%20Object%5D&name=image.png&originHeight=445&originWidth=1203&originalType=binary&ratio=1&rotation=0&showTitle=false&size=117008&status=done&style=none&taskId=u47b80651-6128-447d-8e96-fce54e71290&title=&width=1093.6363399324343)
### 背景定位

- 属性名：background-position
- 作用：主要用于设置不重复的图片在背景区域加载的开始位置。
- 属性值：有三种写法，分别是单词表示法、像素表示法、百分比表示法。
- 不论哪种写法，属性值都有2个，值之间用空格分隔。
- 第一个属性值表示背景图片在水平方向的位置，第二个属性值表示背景图片在垂直方向的位置。
#### 单词表示法

- 属性值都是使用代表方向的单词进行书写。
- 水平方向可选单词：left、center、right。
- 垂直方向可选单词：top、center、bottom。
- 单词表示图片与盒子背景区域进行对应方向的对齐。
#### 像素表示法

- 使用像素值（px）作为背景定位的属性值。
- 第一个属性值，表示背景图片的左上角从border 以内的左上顶点水平方向位移的距离（像素值）
- 第二个属性值，表示背景图片的左上角从border 以内的左上顶点垂直方向位移的距离（像素值）<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1669428905391-475555d8-8db9-4efb-9522-a46f7933ba87.png#averageHue=%23ced8b2&clientId=ucc5f8257-b054-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=388&id=uff9dbcfa&margin=%5Bobject%20Object%5D&name=image.png&originHeight=427&originWidth=575&originalType=binary&ratio=1&rotation=0&showTitle=false&size=163795&status=done&style=none&taskId=ud9f40aad-5d12-4a9a-8ba5-86211b36f88&title=&width=522.7272613974644)
- 像素值正负代表位移的方向不同
   - 正数：表示图片针对盒子的原点向右、向下移动。
   - 负数：表示图片针对盒子的原点向左、向上移动。
- 可以利用属性值为负数，制作在小盒子中显示大的背景图的一部分。制作方法，需要使用 FW 软件量取尺寸，读取数据。
   - 第一步：在设计图中，使用切片工具制作一个想要显示区域大小的切片，让切片左上顶点位于想要加载的背景部分。
   - 第二步：读取属性栏的切片数据，其中宽、高就是要加载的盒子的宽高，x 和 y 的数值表示移动的距离的绝对值，直接将数值加负号赋值给背景定位属性。
#### 百分比表示法

- 百分比表示法使用百分比数字作为属性值。
- 100%代表的数值：
   - 水平方向，等价于盒子的border以内的背景区域宽度减去图片的宽度。
   - 垂直方向，等价于盒子的border以内的背景区域高度减去图片的高度。
### 背景附着

- 属性名：background-attachment。
- 作用：设置的是背景图片是否要随着页面或者盒子的滚动而滚动。
- 属性值：<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1669430873246-4af9e87d-8211-473d-bb08-7a175e2c454f.png#averageHue=%23edecea&clientId=udfb59beb-f4ab-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=153&id=u9b6af1fd&margin=%5Bobject%20Object%5D&name=image.png&originHeight=168&originWidth=631&originalType=binary&ratio=1&rotation=0&showTitle=false&size=42187&status=done&style=none&taskId=u786bbbd1-e50c-47e8-92de-deea8e13372&title=&width=573.6363512031305)
#### 背景缩放

- 属性名：background-size
- 作用：设置背景图片的尺寸，就像我们设置 <img> 的尺寸一样，在移动 Web 开发中做屏幕适配应用非常广泛。
- 属性值：cover会完全覆盖，而contain只要有一个方向（垂直或水平）扩展至最大尺寸就会停止扩展了。<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1669436990235-b24ebb87-70ef-4812-91f9-796f8785ac6c.png#averageHue=%23f4f3f2&clientId=udfb59beb-f4ab-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=309&id=ube0647a7&margin=%5Bobject%20Object%5D&name=image.png&originHeight=340&originWidth=1000&originalType=binary&ratio=1&rotation=0&showTitle=false&size=106402&status=done&style=none&taskId=ud570fa80-4576-4974-a5ed-6ee2a78a0f9&title=&width=909.0908893868947)
### 综合写法

- 综合写法就是用background属性把五个单一属性的值进行合写。
- 属性值：可以有 1-5 个属性值，值之间用空格进行分隔，背景定位的两个属性值算一个属性值，不能被分开也不能颠倒顺序。五个属性值之间可以互换位置。
- 如果属性值没有设置完全，其他没有设置的单一属性会按照默认值加载。
- 还可以使用单一属性来层叠综合属性中设置的的某个单一属性的样式 。
### 背景应用
#### 替换插入图

- 场景：想对logo图片提高搜索排名，用h1标签设置logo图片（插入图）的时候就不能够使用文字会，而h1标签中的文字可以提高SEO 搜索排名。
- 解决办法：
   - 1. 使用背景图片来代替插入图作为logo。
   - 2. 可以将文字的字号设置为0来隐藏文字。
   - 或者可以设置给包含文本的标签一个 text-indent属性，属性值为负的很大的值，文字会走到盒子外部，直接再设置溢出隐藏属性，将溢出文字隐藏。<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/2760917/1669451624152-28bf61a7-fb8f-48c8-bb27-012b2776e00c.png#averageHue=%23fcd6c8&clientId=udfb59beb-f4ab-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=85&id=u1670a811&margin=%5Bobject%20Object%5D&name=image.png&originHeight=93&originWidth=174&originalType=binary&ratio=1&rotation=0&showTitle=false&size=7408&status=done&style=none&taskId=u1b37b8da-3a78-48f3-a1ff-edc3faeadd7&title=&width=158.18181475331968)
#### padding区域背景图

- 使用背景图在padding区域设置无序列表的列表样式
#### 精灵图技术

- 场景：一个页面有多个背景图的时候，用户访问页面的时候每张图片都要通过发起请求才能展示给用户，频繁发起请求会大大降低页面的加载速度。为了有效地减少服务器接受和发送请求的次数，提高页面的加载速度，出现了 CSS精灵图技术
- 解决办法：
         1. 将一个页面涉及到的所有零星背景图像都集中到一张大图（一张背景透明的 png 图片）中去，然后将大图应用于网页。
         2. 利用背景定位技术，将精灵图的每个小图片加载到对应的标签上。
- 注意事项：
   - 精灵图上放的都是小的装饰性质的背景图片，插入图片不能往上放。
   - 精灵图的宽度取决于最宽的那个背景图片的标签宽度。
   - 精灵图可以横向摆放也可以纵向摆放，但是每个图片之间必须留够足够的空白，保证背景图片加载到一个标签内部时，不能出现多余内容。
   - 在精灵图的最底端，尽量留一点空白，方便以后添加其他精灵图。
   - 可以使用一些在线工具，快速生成精灵图。
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>背景应用</title>
  <style>
    * {
      margin: 0;
      padding: 0;
    }

    h1 {
      width: 146px;
      height: 58px;
      margin: 0 auto;
    }

    h1 a {
      display: block;
      width:146px;
      height:58px;
      background-image: url("images/logo.png");
      font-size: 0;
    }

    .list {
      width: 350px;
      border: 1px solid #333;
      margin: 20px;
      list-style: none;
      font: 16px/32px "微软雅黑";
      
    }

    .list li {
      background: url("images/s.png") no-repeat left center ;
      padding-left: 20px;
      
    }
  </style>
</head>
<body>
  <!-- 用背景图代替插入图 -->
  <h1>
    <!-- <a href="#"><img src="images/logo.png" alt="logo"></a> -->
    <a href="#">淘宝网|购物|衣服|直播</a>
  </h1>

  <!-- padding区域的背景图 -->
  <ul class="list">
    <li>新闻标题新闻标题新闻标题新闻标题</li>
    <li>新闻标题新闻标题</li>
    <li>新闻标题新闻标题新闻标题新闻标题新闻123</li>
    <li>新闻标题新闻标题新闻标题新闻</li>
    <li>新闻标题新闻标题新闻标题新闻标题新闻</li>
  </ul>
  
</body>
</html>
```
## 处理不同方向的文本

- 页面有时候会有需要垂直走向的文本，比如古诗词或者日本台湾一些文学作品是从上到下显示的，所以需要使用一个属性**writing-mode**来实现
- 属性值：
  - `horizontal-tb`: 文本是水平方向的，元素是垂直从上到下的。
  - `vertical-rl`: 元素流向从右向左，文本是垂直方向的
  - `vertical-lr`: 元素流向从左向右，文本是垂直方向的
    ![image-20230103233150417](https://image-1303053174.cos.ap-guangzhou.myqcloud.com/typora-images/image-20230103233150417.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    .verticle-mode {
      writing-mode: vertical-rl;
    }

    .verticle-mode-lr {
      writing-mode:vertical-lr;
    }
  </style>
</head>
<body>
  <h4>咏柳</h4>
<p>碧玉妆成一树高，<br>万条垂下绿丝绦。<br>不知细叶谁裁出，<br>二月春风似剪刀。</p>

<div class="verticle-mode">
    <h4>咏柳</h4>
    <p>碧玉妆成一树高，<br>万条垂下绿丝绦。<br>不知细叶谁裁出，<br>二月春风似剪刀。</p>
</div>

<div class="verticle-mode-lr">
  <h4>咏柳</h4>
  <p>碧玉妆成一树高，<br>万条垂下绿丝绦。<br>不知细叶谁裁出，<br>二月春风似剪刀。</p>
</div>
</body>
</html>
```

### 逻辑属性和逻辑值

+ 有2个盒子，一个是水平方向的书写模式，一个是垂直方向的书写模式，同时给这2个盒子设置了一个固定的宽度，可以发现垂直方向的盒子的宽度也发生了变化，导致出现了溢出。
  ![image-20230103235806768](https://image-1303053174.cos.ap-guangzhou.myqcloud.com/typora-images/image-20230103235806768.png)

  ```css
  .box {
    width: 110px;
  }
  
  .horizontal {
    writing-mode: horizontal-tb;
  }
  
  .vertical {
    writing-mode: vertical-rl;
  }
  
  
  ```

  ```html
  <div class="wrapper">
    <div class="box horizontal">
      <h2>Heading</h2>
      <p>A paragraph. Demonstrating Writing Modes in CSS.</p>
      <p>These boxes have a width.</p>
    </div>
    <div class="box vertical">
      <h2>Heading</h2>
      <p>A paragraph. Demonstrating Writing Modes in CSS.</p>
      <p>These boxes have a width.</p>
    </div>
  </div>
  ```

+ 这时候就需要用到一个新的属性——映射属性来替换掉width和height，它们分别是内联尺寸（inline-size）以及块级尺寸（block-size），这是块级维度的尺寸。
  ![image-20230104000219800](https://image-1303053174.cos.ap-guangzhou.myqcloud.com/typora-images/image-20230104000219800.png)

  ```css
  .box {
    inline-size: 150px;
  }
  
  .horizontal {
    writing-mode: horizontal-tb;
  }
  
  .vertical {
    writing-mode: vertical-rl;
  }
  ```

  ```html
  <div class="wrapper">
    <div class="box horizontal">
      <h2>Heading</h2>
      <p>A paragraph. Demonstrating Writing Modes in CSS.</p>
      <p>These boxes have inline-size.</p>
    </div>
    <div class="box vertical">
      <h2>Heading</h2>
      <p>A paragraph. Demonstrating Writing Modes in CSS.</p>
      <p>These boxes have inline-size.</p>
    </div>
  </div>
      
  ```

#### 逻辑外边距、边框和内边距属性

+ margin-top属性的映射是margin-block-start——总是指向块级维度开始处的边距,垂直方向如果是rl则是最右边，反之亦然。

+ padding-left属性映射到 padding-inline-start，这是应用到内联开始方向（这是该书写模式文本开始的地方）上的内边距。

+ border-bottom属性映射到的是border-block-end，也就是块级维度结尾处的边框。
  ![image-20230104002129634](https://image-1303053174.cos.ap-guangzhou.myqcloud.com/typora-images/image-20230104002129634.png)

  ```html
  <!DOCTYPE html>
  <html lang="en">
  
  <head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
      .box {
        inline-size: 200px;
        writing-mode: vertical-rl;
      }
  
      .logical {
        margin-block-start: 60px;
        padding-inline-end: 4em;
        padding-block-start: 2px;
        border-block-start: 5px solid pink;
        border-inline-end: 10px dotted rebeccapurple;
        border-block-end: 1em double orange;
        border-inline-start: 10px solid black;
      }
  
      .physical {
        margin-top: 20px;
        padding-right: 2em;
        padding-top: 2px;
        border-top: 5px solid pink;
        border-right: 10px dotted rebeccapurple;
        border-bottom: 1em double orange;
        border-left: 1px solid black;
      }
  
      h2 {
        border-bottom: 5px solid black;
      }
    </style>
  </head>
  
  <body>
    <div class="wrapper">
      <div class="box physical">
        <h2>Physical Properties</h2>
        <p>A paragraph. Demonstrating Logical Properties in CSS.</p>
      </div>
      <div class="box logical" style="display: inline;">
        <h2>Logical Properties</h2>
        <p>A paragraph. Demonstrating Logical Properties in CSS.</p>
        
      </div>
      <div class="box logical" style="display: inline;">
        <h2>Logical Properties</h2>
        <p>A paragraph. Demonstrating Logical Properties in CSS.</p>
        
      </div>
  
  </body>
  
  </html>
  ```

  #### 逻辑值

  + 一些属性的取值是一些物理值（如top、right、bottom和left），这些值同样拥有逻辑值映射（block-start、inline-end、block-end和inline-start）。

### 何时使用逻辑属性呢？

+ 在你并没有应用多种书写模式时，更倾向于使用物理属性，因为这些在你使用弹性布局和网格布局时非常有用。
+ 如果有多种书写模式，那么使用逻辑属性可以避免出现一些像溢出这种问题。

## 定位属性

### 定位类型

- 属性名：position
- 属性值：
   - relative：相对定位
   - absolute：绝对定位
   - fixed：固定定位
- 作用：根据属性值的不同，在页面上以不同参考元素为根据发生不同的位置偏移
### 偏移量属性

- 设置了定位属性的元素，如果要发生位置的移动必须要搭配偏移量属性进行设置。
- 水平方向：left、right
- 垂直方向：top、bottom
- 属性值：常用px为单位的数值，或者百分比
### 相对定位

- 相对定位的属性值为relative，中文为相对。
- 相对定位参考的元素为标签加载的原始位置，也就是说相对定位的偏移是以原来原始位置为参考点进行偏移的。
#### 相对定位的性质

- 设置了相对定位的元素不会脱离标签的原始状态（浮动、标准流），并且不会让出原来占有的位置。
- 元素显示效果就是原位留坑，偏移位置出显示元素。
- 相对定位是以元素整个盒子为单位进行偏移，参考的元素为整个盒子。
#### 注意事项

1. 偏移量属性的值是区分正负的
   1. 正数：表示偏移的方向与属性名方向相反。
   2. 负数：表示偏移的方向与属性名方向相同。
2. 同一个方向，不能设置两个偏移量属性，如果水平方向同时设置了 left 和right 属性，只会加载 left 属性，垂直方向只加载 top 属性，所以一般建议书写时从水平方向和垂直方向各挑一个属性进行组合。
3. 由于相对定位的参考元素是自身，left 的正值等价于 right 的负值，top 的正值等价于 bottom 的负值。为了方便记忆，可以选择只使用 left、top 组合。
#### 实际应用

1. 由于相对定位元素比较稳定，不会随意让出位置，可以将相对定位的元素作为绝对定位的参考元素，就是父元素为相对定位，子元素以父元素为参考设置绝对定位，父相子绝。
2. 相对定位比较稳定，可以在占有原始位置的情况下，对加载效果区域进行位置调整，进行微调设置。或者对文字进行微调。
### 绝对定位

- 属性值：absolute，中文为绝对。
- 绝对定位的参考是距离最近的有定位的祖先元素，如果祖先都没有定位，参考<body>。
#### 绝对定位的性质

1. 绝对定位的元素脱离标准流，会让出标准流位置。
2. 可以设置宽高，也可以随时定义位置，如果不设置宽高，则只能被内容撑开。
3. 绝对定位的参考元素是不固定的，不同的参考元素以及不同的偏移量组合，会导致绝对定位元素的参考点不同，具体位移效果不同。
4. 在绝对定位中，由于参考点不同，left 正值不再等价于 right 的负值。
5. 绝对定位以点为参考。
#### 绝对定位的应用

- <body> 为参考元素的参考点
   - 如果有 top 参与的定位，参考点就是 <body> 页面的左上顶点和右上顶点。自身的对比点是盒子的所有盒模型属性最外面的左上角或右上角。
   - 如果有 bottom 参与的绝对定位，参考点是 <body> 页面首屏的左下顶点或右下顶点。对比点是盒子的所有盒模型属性最外面的左下角或右下角。
   - 实际应用中，如果以 <body> 为参考元素，不同分辨率的浏览器中，绝对定位的元素位置是不同的，所以较少使用 <body> 作为参考元素。
- 祖先级为参考元素
   - 如果祖先级中有定位的元素，就不会去参考 <body> 。
   - 参考的是祖先元素中有任意定位的，在 HTML 结构中距离目标最近的祖先。
### 固定定位
### 定位应用
### 压盖顺序
### 综合案例
