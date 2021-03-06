目的

在这篇教程中，你将会学到：

* 使用OpenCV中的copyMakeBorder()函数来设置边框（额外的图像边距）

理论

> 注意
> 
> 本文例子来源于Bradski和Kaehler所著的Learning OpenCV一书。

1.在之前的教程中，我们学会了如何使用卷积的方式处理图片。但是，很自然地我们还有其他问题，如何处理图像的边框？如果我们需要处理的图像像素位于图像的边界上，我们应该如何处理？

2.OpenCV的大部分函数是将输入的图片放置到一张更大的图片当中，然后增加边框（下面代码提及任何一种的情况）。这样，卷积函数便可以在任何一个需要的像素上进行处理，并没有什么问题（额外的边框在操作结束后将他去除掉）。

3.在这篇教程中，我们将简单地使用两种生成图像边框的方法：

    * BORDER_CONSTANT: 在图像边界使用常量值进行操作（例如黑色或0）
    * BORDER_REPLICATE: 原始图像的行或列通过复制原来边界上的像素来增加额外的边框。
    
这些概念在代码部分可以更加直观的感受到。

* 这些代码能做什么？

    * 加载一张图片
    * 允许用户使用各种各样的值来对图像的边界进行边框处理。这里有两个选项：
        
        1.固定值的边框：对整个边框增加固定宽度。每五秒钟更新固定边框的值。
        
        2.复制图像边框：边框将通过原始图片的边界值进行复制后得到。
    
    用户通过输入“c”(constant)和“r”(replicate)来切换选项。

    * 当用户按下“ESC”键后，程序停止运行。
