# Academic Homepage with Jekyll Blog

This is the academic homepage for Jun Ma with integrated Jekyll blog functionality.

## 📁 File Structure

```
your-repo/
├── index.html              # Main homepage
├── thoughts.html           # Blog listing page
├── _config.yml            # Jekyll configuration
├── _layouts/              # Page templates
│   └── post.html         # Blog post template
├── _posts/                # Your blog posts (Markdown)
│   └── 2025-01-15-example.md
└── assets/                # Images, PDFs, etc.
    └── grabs.png
```

## ✍️ How to Write a New Blog Post

### Step 1: Create a new Markdown file

Create a new file in the `_posts` folder with this naming format:
```
YYYY-MM-DD-title-of-post.md
```

For example:
```
2025-01-20-my-research-thoughts.md
```

### Step 2: Add front matter

At the top of your Markdown file, add:

```yaml
---
layout: post
title: "Your Post Title Here"
date: 2025-01-20
categories: [Research, PDE, Optimization]
---
```

### Step 3: Write your content in Markdown

After the front matter, write your content using Markdown syntax:

```markdown
## Section Title

Your paragraph here with **bold** and *italic* text.

### Subsection

- Bullet point 1
- Bullet point 2

1. Numbered list
2. Another item

You can also include code:

```python
def hello():
    print("Hello, world!")
```

And math equations (if you add MathJax support):

$$
f(x) = \int_{-\infty}^{\infty} e^{-x^2} dx
$$
```

### Step 4: Commit and push to GitHub

```bash
git add _posts/2025-01-20-my-research-thoughts.md
git commit -m "Add new blog post"
git push
```

GitHub Pages will automatically build and deploy your site!

## 🎨 Markdown Syntax Reference

### Headers
```markdown
# H1
## H2
### H3
```

### Emphasis
```markdown
*italic* or _italic_
**bold** or __bold__
***bold italic***
```

### Lists
```markdown
- Item 1
- Item 2
  - Subitem

1. First
2. Second
```

### Links
```markdown
[Link text](https://example.com)
```

### Images
```markdown
![Alt text](/assets/image.png)
```

### Code
```markdown
Inline `code`

```python
# Code block
def function():
    pass
```
```

### Blockquotes
```markdown
> This is a quote
```

### Tables
```markdown
| Header 1 | Header 2 |
|----------|----------|
| Cell 1   | Cell 2   |
```

## ⚙️ Important: Remove .nojekyll

**CRITICAL:** Delete the `.nojekyll` file from your repository root to enable Jekyll!

```bash
git rm .nojekyll
git commit -m "Enable Jekyll"
git push
```

## 🚀 GitHub Pages Settings

1. Go to your repository Settings
2. Navigate to Pages section
3. Set Source to: Branch `main`, folder `/ (root)`
4. Save

Your site will be available at: `https://yourusername.github.io/repository-name/`

## 📝 Tips

- Blog posts must be in the `_posts` folder
- File names must follow the `YYYY-MM-DD-title.md` format
- Front matter (the YAML between `---`) is required
- The `date` in front matter should match the date in the filename
- Categories help organize your posts

## 🔧 Customization

### Change colors
Edit the CSS variables in `_layouts/post.html` and `thoughts.html`:

```css
:root {
  --primary: #0C7C59;
  --secondary: #1A5490;
  /* ... */
}
```

### Add more features
- Add MathJax for math equations
- Add Disqus for comments
- Add tags in addition to categories
- Add search functionality

## 📚 Example Post Categories

Good category examples:
- Research
- Topology Optimization
- PDE
- Numerical Methods
- Machine Learning
- Conference Notes
- Paper Reviews

Happy blogging! 🎉
