# 优势识别器静态测评网站

这是5.5T生成的静态网站版本。生成的静态网站版本。

## 功能

- 180 题，一页一题
- 自动保存进度到浏览器 localStorage
- 完成后生成：
  - 前 5 优势
  - 前 5 优势描述
  - 34 项完整排名
  - 四大才干主题排序：执行力、影响力、关系建立、战略思维
- 支持导出图片和 PDF 报告
- 移动端优先响应式 UI
- 无需后端、无需数据库，可直接部署到 GitHub Pages

## 文件结构

```text
.
├── index.html
├── assets
│   ├── css
│   │   └── style.css
│   └── js
│       ├── data.js
│       └── app.js
└── README.md
```

## 本地预览

直接双击 `index.html` 即可打开。

更推荐用本地静态服务预览：

```bash
python -m http.server 8000
```

然后访问：

```text
http://localhost:8000
```

## GitHub Pages 部署步骤

1. 在 GitHub 新建仓库，例如 `gallup-static-site`
2. 把本文件夹里的全部文件上传到仓库根目录
3. 进入仓库 `Settings` → `Pages`
4. `Build and deployment` 选择：
   - Source: `Deploy from a branch`
   - Branch: `main`
   - Folder: `/root`
5. 点击 Save
6. 等待 GitHub Pages 生成访问地址，例如：

```text
https://你的用户名.github.io/gallup-static-site/
```

## 重要说明

- 测评数据只保存在用户当前浏览器 localStorage 中，不会上传服务器。
- 图片 / PDF 导出依赖 CDN 加载 `html2canvas` 和 `jsPDF`。如果用户网络无法访问 CDN，核心测评功能仍可正常使用，但导出按钮会提示稍后重试。
- 计分矩阵来源于 Excel 的 `sheet1` 工作表公式；优势描述来源于 `Sheet2`。
