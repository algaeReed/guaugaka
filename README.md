# 刮刮卡（Canvas 练手 Demo）

2020 年写的前端练手项目：在图片上覆盖一层灰色 Canvas 涂层，按住鼠标拖动即可「刮开」，刮开面积超过 60% 时自动显示整张图片。核心是 Canvas 2D 的 `globalCompositeOperation = "destination-out"`，再用 `getImageData` 统计透明像素占比。

## 运行

纯静态页面，**无需安装依赖、无需构建、无需服务器**：

- 直接双击 `index.html` 用浏览器打开；或
- 在本目录执行 `python3 -m http.server 8000`，然后访问 `http://localhost:8000`

> 刮开交互只绑定了鼠标事件，请用桌面浏览器体验。

## 文件

| 路径 | 说明 |
|---|---|
| `index.html` | 页面 + 内联 CSS/JS，包含全部刮刮逻辑 |
| `images/bg.png` | 页面背景图（1470 × 899 PNG） |
| `images/pic.png` | 被涂层覆盖的图片（文件实际是 JPEG 数据，扩展名为 `.png`） |

## 已知问题（保留 2020 年原样，未修复）

- `#txt` 输入框在 HTML 中被注释掉了，但 `check()` 仍在写 `txt.value`，鼠标松开时会触发空指针错误。
- 只绑定了 `onmousedown` / `onmousemove` / `onmouseup`，移动端触摸不可用。
- 容器宽高写死 `1253 × 890`，与背景图 `1470 × 899` 不一致，窗口缩放会错位。
- 页面 `<title>` 仍是 `Document`，meta 关键词与描述仍是占位文本。

## 状态

练手代码，仅作归档展示，不再维护。原仓库唯一提交为 `11952f9 "cnavas"`（2020-05-26）。
