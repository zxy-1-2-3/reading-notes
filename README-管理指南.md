# 读书心得网站管理指南

## 网站结构

```
读书心得/
├── index.html              # 主页 - 书籍列表展示
├── 教学理论读书心得.html    # 示例文章页面
├── articles.json           # 文章元数据配置文件
├── article-template.html   # 新文章模板
└── README-管理指南.md      # 本文档
```

## 添加新的读书心得文章

### 方法一：直接修改 index.html 中的数据

1. 打开 `index.html` 文件
2. 找到 `booksData` 对象中的 `books` 数组
3. 按照现有格式添加新的书籍对象：

```javascript
{
    "id": "unique-book-id-2024",
    "title": "《书名》",
    "subtitle": "副标题或读书心得主题",
    "author": "作者姓名",
    "publisher": "出版社",
    "publishYear": "出版年份",
    "pages": "页数",
    "readingDate": "2024-01-01",
    "fileName": "文章文件名.html",
    "summary": "书籍简介和读书心得摘要...",
    "readingTime": "约XX分钟",
    "difficulty": "容易/中等/较难",
    "featured": true/false
}
```

### 方法二：使用 articles.json 配置文件（推荐）

1. 编辑 `articles.json` 文件，在 `articles` 数组中添加新条目
2. 修改 `index.html` 中的 JavaScript 代码，从 `articles.json` 加载数据

## 创建新的文章页面

### 使用模板创建

1. 复制 `article-template.html` 文件
2. 重命名为您的文章文件名（如：`新书读书心得.html`）
3. 替换模板中的占位符：
   - `{{ARTICLE_TITLE}}` → 文章标题
   - `{{ARTICLE_SUBTITLE}}` → 文章副标题
   - `{{BOOK_TITLE}}` → 书名
   - `{{BOOK_AUTHOR}}` → 作者
   - `{{BOOK_PUBLISHER}}` → 出版社
   - `{{BOOK_YEAR}}` → 出版年份
   - `{{BOOK_PAGES}}` → 页数
   - `{{ARTICLE_CONTENT}}` → 文章正文内容

### 基于现有文章创建

1. 复制 `教学理论读书心得.html` 文件
2. 修改文章标题、书籍信息和正文内容
3. 确保保留导航栏和阅读辅助功能

## 网站特性

### 当前功能
- ✅ 响应式设计，支持各种设备
- ✅ 简约的书籍卡片展示
- ✅ 搜索功能（书名、作者、内容）
- ✅ 阅读辅助功能（字体调节、夜间模式、行间距调节）
- ✅ 智能目录导航
- ✅ 一页展示8+本书的紧凑布局
- ✅ 精选标识和阅读统计

### 设计原则
- **简约优先**：去除复杂的分类和导航
- **内容为王**：突出书籍标题和核心信息
- **高密度展示**：一页显示更多书籍
- **优秀体验**：保持现有的阅读辅助功能

## 样式自定义

### 主要CSS变量
```css
:root {
    --primary-color: #1a365d;      /* 主色调 */
    --secondary-color: #2d5a87;    /* 次要色调 */
    --accent-color: #4a90a4;       /* 强调色 */
    --text-primary: #2d3748;       /* 主要文字颜色 */
    --bg-card: #ffffff;            /* 卡片背景色 */
    --gradient-primary: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
}
```

### 卡片尺寸调整
- 修改 `.books-grid` 的 `grid-template-columns: repeat(auto-fit, minmax(280px, 1fr))`
- 调整 `.book-card` 的 `height: 320px`

## 部署建议

### 静态网站托管
- GitHub Pages
- Netlify
- Vercel
- 腾讯云静态网站托管

### 本地预览
在项目目录下运行简单的HTTP服务器：
```bash
# Python 3
python -m http.server 8000

# Node.js
npx serve .

# PHP
php -S localhost:8000
```

## 维护建议

1. **定期备份**：保存好所有HTML文件和配置
2. **版本控制**：使用Git管理代码变更
3. **内容更新**：及时添加新的读书心得
4. **性能优化**：当书籍数量增多时考虑分页或懒加载
5. **SEO优化**：为每篇文章添加合适的meta标签

## 技术栈

- **前端**：纯HTML + CSS + JavaScript
- **字体**：Google Fonts (Noto Serif SC + Source Sans Pro)
- **图标**：Unicode Emoji
- **响应式**：CSS Grid + Flexbox
- **兼容性**：现代浏览器

---

如有问题或需要帮助，请参考现有代码或寻求技术支持。
