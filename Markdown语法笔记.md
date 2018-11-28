<script type="text/javascript" src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=default">/* 引入MathJax，显示公式 */</script>

# markdown语法总结
<font size='3' color="grey">`BoxunWang`  `Markdown语法`</font>
---
文件的保存类型为xxx.md

## 1.强调
*斜体*    **加粗**  
_斜体_    __加粗__  

## 2.分级标题
一级标题
======
二级标题
------  
<br />
# 一级标题
## 二级标题
### 三级标题
<br />
# 一级标题 #
## 二级标题 ##
### 三级标题 ###

## 3.列表
* 无序列表1
* 无序列表2
* 无序列表3
<br />
+ 无序列表1
+ 无序列表2
+ 无序列表3
<br />
- 无序列表1
- 无序列表2
- 无序列表3
<br />
1.有序列表一  
3.有序列表二  
9.有序列表三  
> p.s.序号只以第一个数字为准

## 4.文字引用
> 一级引用
>> 二级引用
>>> 三级引用

## 5.分割线
---
* * *
- - -

## 6.删除线
~~删除的文字~~  

## 7.链接
[链接文字](http://www.baidu.com)  

## 8.图片
![一张图片](http://www.xxx.com/image/logo.gif)  

## 9.代码
```代码类型
    //一段代码...
```

    Tab开头表示代码块

## 10.Todo列表
- [ ] 项目1
    - [ ] 事务1
    - [ ] 事务2
    - [x] 事务3
    - [x] 事务4

## 11.公式
```html
<!-- 引入MathJax，用以显示公式 -->
<script type="text/javascript" src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=default"></script>
```
$$E=mc^2$$  
$$\sum_{i=1}^n a_i=0$$  
$$f(x_1,x_x,\ldots,x_n) = x_1^2 + x_2^2 + \cdots + x_n^2 $$  
$$\sum^{j-1}_{k=0}{\widehat{\gamma}_{kj} z_k}$$  

## 12.表格
| name | age | sex |
|:----:|:----|----:|
| Tony | 20  | female |
| Lucy | 16  | male |

表头1 | 表头2
------- | -------
content | content 
content | content 

## 13.图
### 流程图
```flow
st=>start: Start
op=>operation: Your Operation
cond=>condition: Yes or No?
e=>end

st->op->cond
cond(yes)->e
cond(no)->op
```
### Mermaid 流程图
```graphLR
    A[Hard edge] -->|Link text| B(Round edge)
    B --> C{Decision}
    C -->|One| D[Result one]
    C -->|Two| E[Result two]
```

### 序列图
```seq
Alice->Bob: Hello Bob, how are you?
Note right of Bob: Bob thinks
Bob-->Alice: I am good thanks!
```
```seq
Title: Here is a title
A->B: Normal line
B-->C: Dashed line
C->>D: Open arrow
D-->>A: Dashed open arrow
```
### Mermaid 序列图
```sequence
    Alice->John: Hello John, how are you?
    loop every minute
        John-->Alice: Great!
    end
```

### 甘特图
```gantt
    title 项目开发流程
    section 项目确定
        需求分析       :a1, 2016-06-22, 3d
        可行性报告     :after a1, 5d
        概念验证       : 5d
    section 项目实施
        概要设计      :2016-07-05  , 5d
        详细设计      :2016-07-08, 10d
        编码          :2016-07-15, 10d
        测试          :2016-07-22, 5d
    section 发布验收
        发布: 2d
        验收: 3d
```

## 14.内容目录
显示全文内容的目录结构  
[TOC]

## 15.标签分类
Tags: Sublime Markdown Emmet
标签： Sublime Markdown Emmet

## 16.注脚
注脚一[^footnote]
注脚二[^footnote2]

[^footnote]: 注脚永远在最后一行显示。  
[^footnote2]: 注脚永远在最后一行显示。

## 17.换行 & 首行缩进
### 使用html的br标签
一段文字<br />
二段文字
### 敲击两个以上空格，然后回车
一段文字  
二段文字
### 首行缩进
&ensp;//半角  
&emsp;//全角  
&nbsp;//other  

## 18.高亮字体
高亮` markdown `效果