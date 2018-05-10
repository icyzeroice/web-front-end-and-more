# BFC

Block Formatting Contexts（块级格式化上下文），隔离了内外布局的相互影响。

### BFC 的触发条件

1. body 根元素本身是一个有 BFC 特性的元素

2. float: right / left;

3. position: absolute / fixed;

4. display: inline-block / table-cells / flex;

5. overflow: hidden / auto / scroll;
