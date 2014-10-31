# 前端开发代码规范

这里记载下我的前端开发代码规范:

## 规范

* [HTML 编码规范](./html.md)
* [CSS 编码规范](./css.md)
* [Javascript 编码规范](./javascript.md)
* [Markdown 编写规范](./markdown.md)
<!-- * [开源项目目录规范](./project.md) -->





todo:

在 FEX 文档基础上根据其他文档以及一些其他知识点添加。

## HTML 编码规范
- [] 添加 [fex](https://github.com/fex-team/styleguide) HTML 规范
- [] review [fex](https://github.com/fex-team/styleguide) HTML 规范
- [] review [lzx-coding-standards](/lzx-coding-standards.md) HTML 部分
- [] review [编码规范 by @mdo](http://codeguide.bootcss.com/) HTML 部分
- [] review [Isobar前端代码规范 及 最佳实践](http://coderlmn.github.io/code-standards/) HTML 部分
- [] review [前端开发指南](http://coderlmn.github.io/Front-End-Development-Guidelines/) HTML 部分

+ CSS 编码规范
 - - [] 添加 [fex](https://github.com/fex-team/styleguide) CSS 规范
 - [] review [fex](https://github.com/fex-team/styleguide) CSS 规范
 - [] review [lzx-coding-standards](/lzx-coding-standards.md) CSS 部分
 - [] review [编码规范 by @mdo](http://codeguide.bootcss.com/) CSS 部分
 - [] 根据各个 CSS reset 以及 [zxx.lib.css](zxx.lib.css)以及sofish & lepture 等 CSS 库进行总结出一份属于自己的 CSS 库，参考 paddingme 的 gists。
 - [] review [Isobar前端代码规范 及 最佳实践](http://coderlmn.github.io/code-standards/) CSS 部分
 - [] review [前端开发指南](http://coderlmn.github.io/Front-End-Development-Guidelines/) CSS 部分
 - review [http://semantic-ui.com/guide/cssguide.html](http://semantic-ui.com/guide/cssguide.html)

+ Markdown 编码规范
 - [] 添加 [fex](https://github.com/fex-team/styleguide) MD 规范
 - [] review [Markdown 语法说明](http://wowubuntu.com/markdown/) MD 规范
 - [] review [GitHub Flavored Markdown](https://help.github.com/articles/github-flavored-markdown/) MD 规范

+ Javascript 编码规范
 - [] 添加 [fex](https://github.com/fex-team/styleguide) Javascript 规范
 - [] review [fex](https://github.com/fex-team/styleguide) Javascript 规范
 - [] review [lzx-coding-standards](/lzx-coding-standards.md) Javascript 部分
 - [] review [编码规范 by @mdo](http://codeguide.bootcss.com/) Javascript 部分
 - [] review [Isobar前端代码规范 及 最佳实践](http://coderlmn.github.io/code-standards/) Javascript 部分
 - [] review [前端开发指南](http://coderlmn.github.io/Front-End-Development-Guidelines/) Javascript 部分

+ security.md
 - [] 添加 [fex](https://github.com/fex-team/styleguide) security.md
 - [] review [fex](https://github.com/fex-team/styleguide) security.md

+ editorconfig.md
 - [] 添加 [fex](https://github.com/fex-team/styleguide) security.md

+ sublime 插件以及配置
 - [] 参考[emmet-plus](https://github.com/yisibl/emmet-plus)
 - [] 参考[Sublime Text 全程指南](http://zh.lucida.me/blog/sublime-text-complete-guide/)
 - [] sublime 插件以及配置


主要参考以下代码规范以及最佳实践，再结合自身习惯总结：
- [文档与源码编写风格](https://github.com/fex-team/styleguide)
- [Isobar前端代码规范 及 最佳实践](http://coderlmn.github.io/code-standards/)
- [前端开发指南](http://coderlmn.github.io/Front-End-Development-Guidelines/)
- [编码规范 by @mdo](http://codeguide.bootcss.com/)
- [00xx](https://github.com/paddingme/Coding-Standards/blob/master/lzx-coding-standards.md)
- [http://semantic-ui.com/guide/cssguide.html](http://semantic-ui.com/guide/cssguide.html)












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
