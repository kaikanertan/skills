
# 微信公众号文章转 Markdown

将微信公众号文章转换为 Markdown 格式，保存到用户当前工作目录。

当用户提供微信公众号文章链接（mp.weixin.qq.com）并希望转换、下载、保存为 Markdown 时使用。

**触发词**包括：转成 Markdown、转为 md、下载文章、保存为 Markdown、导出 Markdown、公众号转 Markdown、文章转换等。
如果用户要求下载图片、保存图片、包含图片、图片本地化，则需要加 --save-images 参数。

## 安装项目和依赖

```bash
uv sync
uv tool install --editable ./ # 这里用的相对路径，最好用绝对路径
```

## 使用方法

提供两种模式:

- 默认模式（保留原图链接）
- 下载图片模式

### 示例

用户输入（默认模式）：

- "把这个公众号文章转成 Markdown：<https://mp.weixin.qq.com/s/xxx>"
- "下载这篇文章为 md 格式 <https://mp.weixin.qq.com/s/xxx>"
- "<https://mp.weixin.qq.com/s/xxx> 保存为 Markdown"

用户输入（下载图片模式）：

- "把这个文章转成 Markdown，图片也下载下来：<https://mp.weixin.qq.com/s/xxx>"
- "<https://mp.weixin.qq.com/s/xxx> 转 md，保存图片"
- "导出这篇文章，包含图片 <https://mp.weixin.qq.com/s/xxx>"

### 输出

- 默认模式

  - 输出：`{当前目录}/{文章标题}.md`
  - 图片：保留微信原链接

- 下载图片模式

  - 输出目录：`{当前目录}/{文章标题}/`
  - 文件结构：
  
  ```
  {文章标题}/
  ├── {文章标题}.md
  └── images/
      ├── image_01.png
      ├── image_02.png
      └── ...
  ```

## 鸣谢

感谢原项目：[https://github.com/huangyunbin/resource](https://github.com/huangyunbin/resource)

作者公众号：[AgentFlow](https://mp.weixin.qq.com/s/dB8rW5U9eV8yKGuba1T5-g)