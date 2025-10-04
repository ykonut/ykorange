---
{"dg-publish":true,"permalink":"/CS/文字处理/Word制表符与制表位及其应用/","title":"Word制表符与制表位及其应用","tags":["word"],"created":"2025-04-03T19:19:11.569+08:00","updated":"2025-09-02T11:07:11.369+08:00"}
---

## 使用软件：Microsoft office 365中的word

[制表符](https://so.csdn.net/so/search?q=%E5%88%B6%E8%A1%A8%E7%AC%A6&spm=1001.2101.3001.7020) ：用tab键添加的符号

制表位：水平标尺上的特定位置，用于指定文字缩进的距离或一栏文字开始的位置

制表位三要素：制表位位置、 [对齐方式](https://so.csdn.net/so/search?q=%E5%AF%B9%E9%BD%90%E6%96%B9%E5%BC%8F&spm=1001.2101.3001.7020) 、制表位的引导符（对应制表符下面的显示符号，如虚线，连点线）

![](https://i-blog.csdnimg.cn/blog_migrate/83fbee81cf8bdc26088338b42ae5d0b8.png)

切换制表位种类方法：

方法1:

![](https://i-blog.csdnimg.cn/blog_migrate/15501331f78e783ab45fcce7309bf571.png)

方法2:

![](https://i-blog.csdnimg.cn/blog_migrate/4eec3ac60a5d711c5b2672440553047b.png)

作用位置：制表位是属于段落的属性，因此它是对整个段落起作用的。

- 如果未选择段落时设置制表位，它将对光标所在的那一整段落起作用。
- 如果只需要多个段落有同样的制表位设置，可同时选中多个段落，再进行制表位 [属性设置](https://so.csdn.net/so/search?q=%E5%B1%9E%E6%80%A7%E8%AE%BE%E7%BD%AE&spm=1001.2101.3001.7020) 。

继承性：在一个设置有制表位的段落中按回车产生出下一个段落，新段落也会与上一段落具有同样的制表位设置。

制表位设置方法：

方法1：标尺左侧切换好制表符种类后，直接用鼠标在水平标尺上的相应位置点击添加

![](https://i-blog.csdnimg.cn/blog_migrate/47d21e45c5f457edb35ab670b5c37add.gif)

方法2：【段落设置对话框】→【制表位】设置

![](https://i-blog.csdnimg.cn/blog_migrate/85c8ce527fa6f67a67f439608eb715fc.gif)

#### 应用1：手动设置论文目录：

要求：章节题目居左且逐级增加缩进，页码位于页面最右侧且右对齐

![](https://i-blog.csdnimg.cn/blog_migrate/87c56483daa43cb116edacb7ff2f73c6.gif)

最终效果图：

![](https://i-blog.csdnimg.cn/blog_migrate/ae977c2f4c11a5705130b2603d5196e4.png)

#### 应用2：公式制表位设置，使之公式居中，编号右对齐

(1) 查看纸张大小（如A4：21cm×29.7cm）

(2) 查看页边距（左、右边距）：

![](https://i-blog.csdnimg.cn/blog_migrate/c6846592b74881804e929eb56eaf5d08.png)

(3) 根据左、右页边距与纸张大小设置制表位：

![](https://i-blog.csdnimg.cn/blog_migrate/73ad2433780de9573195952f177a77ed.png)

![](https://i-blog.csdnimg.cn/blog_migrate/b8403989162901921b216ff96372c840.png)

设置结果如下：

![](https://i-blog.csdnimg.cn/blog_migrate/52897a6bd1f69eaa2f7a9e6977af2281.png)

#### 应用3： 一定字数范围内，文字下划线不随文字长度而变化（适用于论文封面个人信息填写）

![](https://i-blog.csdnimg.cn/blog_migrate/106050d6fbbfcdfc88f5e9c5d13868ba.gif)

最终效果图：

![](https://i-blog.csdnimg.cn/blog_migrate/c5db30a81f08e32137f191eabbd32491.png)

设置三个制表位

- 第一个：下划线左边界位置，设为 。左对齐型制表位
- 第二个：中间书写文字的起始位置，设为 。居中对齐型制表位
- 第三个：下划线右边界位置，设为 。左对齐型制表位

位置关系为：

##### 扩展：让上面文字+下划线，整体居中对齐(重要！！！)

1. 做出上面的左对齐格式文本
2. 全选这三个段落
3. 【段落对话框】→【对齐方式】为【居中】

（注意：必须在段落对话框里面设置居中，在外面设置无效！！！！）

![](https://i-blog.csdnimg.cn/blog_migrate/633d79338c418e7d314cec230c7e7ca2.png)

##### 最终效果图：（制表位不变的同时，段落整体居中）

![](https://i-blog.csdnimg.cn/blog_migrate/b308bed29a11458e7940d288db72e6cf.png)

#### 应用4： 上下两行的数字小数点对齐

要求：上下两行的数字设置同样的小数点型制表位

最终效果图：

![](https://i-blog.csdnimg.cn/blog_migrate/8b98172c993a1ecb3f03f14a59d2f1c0.png)

![](https://i-blog.csdnimg.cn/blog_migrate/a03bb12838606d2aac80817f42854083.png)