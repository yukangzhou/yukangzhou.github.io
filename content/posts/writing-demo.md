+++
title = '写作示例：图片、代码与目录'
date = '2026-01-05T10:00:00+08:00'
draft = true
summary = '一篇纯示例文章，用来测试图片、代码块、目录、分类和标签是否都正常。确认没问题后可以直接删掉。'
categories = ['教程']
tags = ['Markdown', '写作', '示例']

[params.cover]
  image = 'images/demo-cover.png'
  alt = '示例封面图'
  caption = '这是文章页封面下方的图注（caption 只在文章页显示）'
+++

> **这一篇是示例，不是给你发布的。**
> 本地用 `hugo server -D` 预览确认后，把整个文件删掉即可。

## 一、正文与标题

PaperMod 会根据二级以上标题自动生成右侧目录（`ShowToc = true`）。
所以文章结构尽量用 `##` 和 `###`，不要用加粗假装标题。

## 二、图片的两种放法

### 方法 A：全局图片库（简单，推荐日常使用）

图片丢进 `static/images/`，正文里用**从站点根开始**的路径：

![全局图片库里的示例封面](/images/demo-cover.png)

```markdown
![全局图片库里的示例封面](/images/demo-cover.png)
```

### 方法 B：随文章的页包（一篇文的图跟着这篇文走）

新建 `content/posts/我的文章/index.md` + `content/posts/我的文章/图1.png`，
正文里用相对路径 `![说明](图1.png)`。适合配图很多的长文。

### 高级用法：图片缩放

用 Hugo 的图片处理，可以把大图自动缩到指定宽度：

```markdown
{{</* figure src="/images/demo-cover.png" width="600" caption="自动缩放到 600px" */>}}
```

{{< figure src="/images/demo-cover.png" width="600" caption="自动缩放到 600px 宽" >}}

## 三、代码块

行内代码：`hugo server -D`

```python
def greet(name: str) -> str:
    """中文文档字符串也不会乱码"""
    return f"你好，{name}"

print(greet("wholosewin"))
```

```bash
# 代码块右上角有「复制」按钮（ShowCodeCopyButtons = true）
git add content/posts/
git commit -m "post: 新增一篇文章"
```

## 四、表格与引用

| 项目 | 说明 |
| --- | --- |
| 分类 | 一篇文章建议只放 1 个分类 |
| 标签 | 可以放多个，用来做横向检索 |

> 引用块用来放结论或提示。

## 五、其他常用语法

- 有序 / 无序列表
- **加粗**、*斜体*、~~删除线~~
- 链接：[Hugo 官方文档](https://gohugo.io/)
- 折叠块（PaperMod 自带 shortcode，参数名是 `summary` 不是 `title`）：

```markdown
{{</* collapse summary="点我展开" */>}}
被折叠的内容
{{</* /collapse */>}}
```

{{< collapse summary="点我展开：一个隐藏的彩蛋" >}}
恭喜你找到了彩蛋 🎉
{{< /collapse >}}
