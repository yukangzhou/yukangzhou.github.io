+++
title = '{{ replace .File.ContentBaseName "-" " " | title }}'
date = '{{ .Date }}'
draft = true
# 文章摘要：留空则自动取正文开头
summary = ''
# 分类：一个分类一个页面，自动汇总到 /categories/xxx/
categories = ['技术笔记']
# 标签：可多个，自动汇总到 /tags/xxx/
tags = []
# 封面图：列表页大图 + 文章页顶部图 + 分享卡片图
# image 只写文件名也能工作：会先在本文章目录找，再找 static/ 全局资源
# [params.cover]
#   image = 'images/xxx.png'
#   alt = '封面图说明（列表页鼠标悬停/读屏用）'
#   caption = '图注，只在文章页显示'
#   hidden = false            # true = 页面上不显示，但分享卡片仍用它
#   responsiveImages = true   # 自动生成 360/480/720/1080/1500 多尺寸（仅生产构建生效）
+++
