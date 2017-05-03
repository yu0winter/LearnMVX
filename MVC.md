#MVC

##1.起始-架构（Architecture）
如何设计一个程序的结构，这是一门专门的学问，叫做"架构模式"（architectural pattern），属于编程的方法论。

而MVC模式就是一种最常见的架构模式，即Model-View-Controller。


对于Model层，首先来看一个错误的认知：
> 把 Model Object 混同于 Value Object。[来自于知乎问题](https://www.zhihu.com/question/22886622/answer/48378638)

在项目中，对象几乎遍布程序的每一个角落。在MVC中不仅Controller需要对象作为数据源，View有时也会通过特定对象来展示界面（如 setViewWithInfo:）。显而易见，此时数据模型既出现在C层、又出现在View层，如果将Model理解成数据模型，那么就违反了MVC的设计，即Moddel和View层是相互隔离的。

那么该如何理解Model层的含义呢，下面首先明确一个定义：ValueObject数据对象。而Model层，应该理解为数据层，也就是程序需要操作的数据或信息。比如UserModel对象，具有获取当前用户信息的方法currentUserInfo，那么需要展示用户信息时Controller层调用currentUserInfo获取信息，之后传递给View层显示。保存用户信息时，用户点击“保存”按钮，将事件传递给Controller，由Controller将修改后的数据传递给UserModel，并让其保存（UserModel.saveAsCurrentUserInfo）。

面向对象设计的核心，就是将复杂的逻辑，拆分成不同的对象来封装。比如要买火车票，那么我们就可以联想到一个具有售票、查询、打印票据等功能的售票机。
 





资料

[谈谈MVC模式](http://www.ruanyifeng.com/blog/2007/11/mvc.html)