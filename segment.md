## 碎片

### DOCTYPE 

```
<!DOCTYPE html>
```

`<!DOCTYPE html>` 简介易记，并可向前向后兼容。位于 HTML 文档 第一句，除掉空格外不可以添加任何字符，若有其他字符，IE 会启动怪异模式，进行渲染。

### CSS RESET

不进行刻意的 CSS reset， 不使用任何 CSS reset 文件。最大限度的冗余，只对有必要的标签，属性进行重置，更何况很多标签是一定会重置的，例如 `a`。 下面是根据各大 CSS reset 文件进行总结的一份完整的 CSS reset 文件，请遵循随取随用的原则，进行取舍，切忌进行复制粘贴。

kitty reset。normal.css，等，查询后再总结。


### CSS 命名空间

常见的 CSS 使用命名空间，更加可见易用。

常见的有:

```
.fl {float:left;}

.fr {float:right;}

```


## 一些细节

```
.foo {
 -webkit-tap-highlight-color: transparent; /* 部分浏览器只支持这个 */
 -webkit-tap-highlight-color: rgba(0, 0, 0, 0); 
}
```

参考链接：
 - https://github.com/yisibl/blog/issues/6
 - http://stackoverflow.com/questions/5210481/disable-orange-outline-highlight-on-focus


`absolute` 与 `display` 并存，`display` 属性自动计算为 `block`。

```
.foo {
  position: absolute;
  display: inline-blcok; /* 多余属性 */
}
```


减少`<a href="#" onclick="">` 或者 `<a href="javascript:...">` 应考虑在
noscript 下 该如何平稳退化。至少不影响功能使用。

应该把 href 指向正确的真实存在的地址。


