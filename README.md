# AI Hub Kit · 产品导航

精致的产品导航静态页，专为少量产品场景优化。玻璃态大卡片 + 渐变背景 + 深浅色主题。

## ✨ 设计亮点

- **渐变光晕背景** — 三色径向渐变营造层次感，深浅色各有专属配色
- **玻璃态大卡片** — `backdrop-filter: blur(24px)` 毛玻璃效果，顶部带产品主题色光晕
- **极简顶栏** — 仅保留主题切换按钮，不抢视觉焦点
- **Hero 区域** — 徽章（带呼吸动画）+ 大标题 + 副标题，信息饱满不空洞
- **真实 Logo** — 卡片展示产品真实 logo 图片，非 emoji 占位
- **角标系统** — 支持 API / NEW / HOT 等自定义角标
- **悬停交互** — 卡片上浮缩放、Logo 旋转微动、箭头变色滑出
- **进入动画** — Hero 下落淡入 → 卡片依次弹入 → 页脚渐显

## 📁 文件结构

```
nav/
├── index.html        # 页面（单文件：HTML + CSS + JS）
├── products.json     # 产品数据（唯一维护入口）
├── logo-model.png    # ZMode 产品 Logo
├── logo-magic.png    # Magic Chat 产品 Logo
└── README.md
```

## 🚀 运行方式

```bash
# 在项目目录启动本地服务
python3 -m http.server 8080

# 浏览器访问
open http://localhost:8080
```

> ⚠️ 不能直接双击打开 HTML（`file://` 协议下浏览器会拦截 `fetch` 读取 JSON）。

## ✏️ 维护产品数据

编辑 `products.json`：

```json
{
  "site": { "title": "站点名", "subtitle": "副标题", "logo": "徽章文字" },
  "products": [
    {
      "id": "唯一标识",
      "name": "产品名称",
      "description": "描述文字",
      "url": "https://链接",
      "icon": "logo-xxx.png",       // 图片路径或 emoji
      "category": "分类",
      "tags": ["标签1", "标签2"],
      "color": "#4f6ef7",           // 主题色（角标/CTA文字）
      "glow": "#4f6ef7",            // 卡片顶部光晕颜色
      "badge": "API"                // 角标文字（可选）
    }
  ]
}
```

| 字段 | 说明 |
|------|------|
| `icon` | 支持 `.png/.jpg/.svg` 路径或纯文本 emoji |
| `color` | 影响角标背景色、CTA 链接色 |
| `glow` | 卡片顶部模糊光晕的颜色，可与 color 不同以增加对比 |
| `badge` | 右上角小标签，如 `API` / `NEW` / `HOT` |

## 🎨 自适应说明

页面针对 **1–4 个产品**做了专门优化：
- 卡片居中排列，不会撑满整行显得空旷
- Hero 区域提供足够的信息密度填充上半屏
- 产品增多时自动换行，仍保持美观

部署到 GitHub Pages / Vercel / Netlify 等平台即可直接使用。
