# Stream

### Why

> 为什么我们要使用 Stream
>
> 参考：
> [[译] 关于 Node.js Stream 你需要知道的一切](https://segmentfault.com/a/1190000009793488)
> [[原文] 关于 Node.js Stream 你需要知道的一切](https://medium.freecodecamp.com/node-js-streams-everything-you-need-to-know-c9141306be93)
> [NodeJS Stream 二：什么是 Stream](https://www.cnblogs.com/dolphinX/p/6285240.html)

- 流不需要像 `fs.readFile` 那些接口，需要把文件完全读入（内存）才能进行下一步操作，内存占用非常小
- 流是一种标准的输入输出抽象，比如在 Unix 或类 Unix 系统（Linux、Mac OS 等）中有管道符号 `|`，类似 Stream 中的 `pipe()`

