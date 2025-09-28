# 例子
## 文档编写例子
本文档主站采用sphinx+recommenmark搭建, 支持markdown语法和reStructuredText, 推荐使用markdown, 以下为几个视例(你可以在右上角查看本页面代码)


表格(原生markdown的表格被屏蔽, 需要通过reStructuredText)
```eval_rst
+------------+------------+-----------+
| Header 1   | Header 2   | Header 3  |
+============+============+===========+
| body row 1 | column 2   | column 3  |
+------------+------------+-----------+
| body row 2 | Cells may span columns.|
+------------+------------+-----------+
```

公式
```math
E = m c^2
```

代码
```c++
int main(){
    printf("HelloWorld!");
}
```

图片
![RUNOOB 图标](_static/basic_screenshot.png)

块引用
> xxxxxxxxx
>> xxxxxxxxx
>>> xxxxxxxxx


## 文档更新例子
+ 按照编写约定,在与Makefile同级别目录下编写<your_doc_name>.md
+ 然后在index.rst里
```
... ...

.. toctree::
    :maxdepth: 2
    :caption: Contents:

    此处添加<your_doc_name>,注意上面的空行

... ...
```
+ 最后执行make html即可,无需重新上线web服务
