## 定位 position
- position:absolute; 绝对定位（定位于最上层、以浏览器的左上角为基准）
- position:relative; 相对定位（相对于当前位置，跟它父级没关系。）
>总结：（position一旦设置会让标签脱离默认文档流，成为一个单独的层。）
>1.一个标签如果设置了position属性，就会解封另外四个属性（top、left、right、bottom）离左上角的距离。
>2.通过absolute定位之后，原位置会被其他元素占用（释放了当前空间）。
>3.通过relative定位之后，原位置不会被其他元素占用。（俗称占着茅坑不拉屎）
>4.如果父级标签没有写position,子标签写了absolute，那么子标签相对浏览器左上角原点定位。
>5.子标签写了relative,不管父级是否有position属性,都是相对自己原来的位置去定位。
>6.父级标签写了position,子标签写了absolute,相对于父级标签左上角定位，同时支持margin.
>7.子标签为absolute,多重父级标签中,以最近的那层写了position属性的标签的左上角为原点定位。（从内往外找，如果都没有，最终以浏览器的左上角为基准。）

##### 总结写position的方法:
1.如果标签原始位置不能被占用，使用relative.相对于自己原来位置去定位。
2.如果标签原始位置需要被占用，使用absolute.但是需要在父级标签中添加position:relative;告诉子元素以我定位。

##### 关于层数(楼层位置)：
- 必须并列关系的元素才能设置楼层。嵌套内的元素永远不会因为楼层低被父级标签元素覆盖。
- 后写定位的层数高。
- 定位层数： z-index: n;n代表正整数。


- position:fixed; 相对窗口定位