---
title: "How to Install Hugo and Deploy with GitHub Actions"
date: 2026-03-07
draft: false
---

<style>
/* =========================
   Glassmorphism Post Styling
========================= */
.post-content {
    max-width: 900px;
    margin: 50px auto;
    padding: 30px;
    background: rgba(255, 255, 255, 0.08);
    backdrop-filter: blur(15px);
    border-radius: 20px;
    box-shadow: 0 10px 40px rgba(0, 0, 0, 0.35);
    color: #ffffff;
    font-family: 'Segoe UI', sans-serif;
}

/* Blurred background image behind post */
body::before {
    content: "";
    position: fixed;
    inset: 0;
    background: url('/images/bg-blur.jpg') center/cover no-repeat;
    filter: blur(12px);
    transform: scale(1.1);
    z-index: -2;
}

body::after {
    content: "";
    position: fixed;
    inset: 0;
    background: rgba(0,0,0,0.5);
    z-index: -1;
}

.post-content h1, .post-content h2 {
    font-weight: 700;
    margin-bottom: 20px;
}

.post-content h1 {
    font-size: 2.5rem;
    background: linear-gradient(90deg, #00f0ff, #ff61e0);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
}

.post-content h2 {
    font-size: 2rem;
    margin-top: 30px;
}

.post-content pre {
    background: rgba(0,0,0,0.3);
    padding: 15px;
    border-radius: 10px;
    overflow-x: auto;
    font-family: monospace;
}

.post-content code {
    background: rgba(0,0,0,0.3);
    padding: 2px 6px;
    border-radius: 5px;
    font-family: monospace;
}

.btn-gradient {
    padding: 12px 28px;
    border-radius: 25px;
    color: #fff;
    display: inline-block;
    margin-top: 15px;
    text-decoration: none;
    font-weight: 600;
    background: linear-gradient(135deg, #00f0ff, #ff61e0);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.btn-gradient:hover {
    transform: scale(1.05);
    box-shadow: 0 8px 30px rgba(0, 240, 255, 0.5);
}

.code-label {
    font-weight: 600;
    margin-bottom: 5px;
    display: block;
}
</style>

<div class="post-content">

<h1>How to Install Hugo and Deploy with GitHub Actions</h1>

<p>This guide shows step-by-step instructions to install Hugo on Arch Linux, create a new site, and deploy it automatically to GitHub Pages using GitHub Actions.</p>

<h2>Step 1: Install Hugo</h2>

<span class="code-label">Update your system and install Hugo:</span>
<pre><code>sudo pacman -Syu hugo</code></pre>

Verify the installation:

<pre><code>hugo version</code></pre>

---

<h2>Step 2: Create a New Hugo Site</h2>

<pre><code>hugo new site my-blog
cd my-blog</code></pre>

This creates the folder structure for your Hugo project.

---

<h2>Step 3: Add the PaperMod Theme</h2>

<pre><code>git init
git submodule add https://github.com/adityatelange/hugo-PaperMod.git themes/hugo-PaperMod
echo 'theme = "hugo-PaperMod"' >> config.toml</code></pre>

---

<h2>Step 4: Create Your First Post</h2>

<pre><code>hugo new posts/first-post.md</code></pre>

Edit it in your favorite editor:

```bash
nano content/posts/first-post.md