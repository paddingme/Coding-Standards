# 前端开发代码规范

这里记载下我的前端开发代码规范，主要参考以下代码规范以及最佳实践，再结合自身习惯总结：

- [文档与源码编写风格](https://github.com/fex-team/styleguide)
- [Isobar前端代码规范 及 最佳实践](http://coderlmn.github.io/code-standards/)
- [前端开发指南](http://coderlmn.github.io/Front-End-Development-Guidelines/)
- [编码规范 by @mdo](http://codeguide.bootcss.com/)
- [00xx](https://github.com/paddingme/Coding-Standards/blob/master/lzx-coding-standards.md)

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