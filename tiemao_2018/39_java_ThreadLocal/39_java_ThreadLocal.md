# ThreadLocal简介

JavaWeb容器中, 当一个请求(request)到达时, 一般会单独分配一个线程(thread)来进行处理; 如果是多个请求, 则对应多个线程。

这种模型带来的好处是, 编程可以很简化，一对一不需要考虑很多复杂的情况; 毕竟对于大部分系统来说，人力开发成本是最大的成本。

Java的最大竞争优势和适用领域就在这里, 所以在企业应用开发领域基本上没有对手。 当然, 在其他领域不一定就是最适合的了, 所以 goLang, Python 等语言纷纷在各自的领域称王称霸。

一般来说, request, response 这一类对象, 是不能传递到service和biz层的。

考虑这样一种场景: 系统和业务代码很早之前就已经开发了， 接口、API和实现代码已经确定、并且有很多地方在使用。 比如 Controller（属于上层） 和 Service (属于底层), Filter(属于外层); 假设业务需求有一些改变, 各个层次之间需要传递/共享/依赖一些新的数据, 我们怎么办?


ThreadLocal

