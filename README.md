# Example AI Docs

基于 [Mintlify](https://mintlify.com) 的对话模型网关文档（chat-only，OpenAI / Anthropic 双协议）。

## 部署（Mintlify Hobby 免费档）

1. 用 GitHub 登录 [app.mintlify.com](https://app.mintlify.com)，选 **免费 Hobby** 档。
2. 连接本仓库（首次会让你安装 Mintlify 的 GitHub App，授权本仓库即可）。
3. Mintlify 自动构建并给一个 `<子域>.mintlify.app` 预览地址；之后每次 `git push` 自动重新部署。
4. （可选）在 dashboard **Settings → Custom Domain** 绑定你的域名，如 `docs.你的站.com`（免费档支持）。

## 本地预览

```bash
bunx mint dev    # 或 npx mint dev
```

## 改成你的品牌（部署前）

全仓库把占位符替换成真实值：

| 占位符 | 换成 |
| --- | --- |
| `Example AI` | 你的品牌名 |
| `https://api.example.com` | 你的 API 域名 |
| `https://example.com` | 你的控制台 / 主站 |

一条命令（macOS）：

```bash
LC_ALL=C find . -name '*.mdx' -o -name 'docs.json' | xargs sed -i '' \
  -e 's#https://api\.example\.com#https://api.你的域名#g' \
  -e 's#https://example\.com#https://你的主站#g' \
  -e 's#Example AI#你的品牌名#g'
```

## 内容范围

只含**对话模型**：介绍 / 快速开始 / 鉴权 / 对话补全 / 模型与定价 / 提示词缓存 / 供应商路由 / 计费 / 速率限制 / 错误处理 + 客户端接入（Cursor / Claude Code / Cline·Roo / Codex / 官方 SDK）。不含视频、图像、嵌入模型。导航在 `docs.json`。
