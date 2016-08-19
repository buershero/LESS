# LESS

标签（空格分隔）： less mixins 

---

##mixins

>请注意,当你叫mixin,**括号是可选的**。

####用法一

```less
.a, #b{
    color:red;
}
```
```less
.a,
.a();
```
####选择器MIXINS

> mixin不仅仅可以包含属性,它们可以包含选择器。

```LESS
.my-hover-mixin() {
  &:hover {
    border: 1px solid red;
  }
}
button {
  .my-hover-mixin();
}
```
编译后
```css
button:hover{border:1px solid red;}
```

####命名空间

```less
#my-library {
  .my-mixin() {
    color: black;
  }
}
// 可以这样用
.class {
  #my-library > .my-mixin();
}
```
####重要的关键字
```less
.foo (@bg: #f5f5f5, @color: #900) {
  background: @bg;
  color: @color;
}
.unimportant {
  .foo(1);
}
.important {
  .foo(2) !important;
}
```
编译后
```css
.unimportant {
  background: #f5f5f5;
  color: #900;
}
.important {
  background: #f5f5f5 !important;
  color: #900 !important;
}
```








