# How to add a post

Posts are plain HTML files. There is no build step.

1. Copy `post-template.html` to `<slug>/index.html`.
   The folder name is the URL. `my-new-post/index.html` is served at `/my-new-post/`.
2. In the copy, replace the title, the canonical URL, the summary, the date (`YYYY-MM-DD`), the labels, and the body.
   Take `noindex` off the new page. Point newer/older links at the neighboring posts, or delete that nav.
3. For a code sample, use a `pre`/`code` block and escape `<` as `&lt;` and `&` as `&amp;`. Existing posts keep the highlighted markup they already have; you can paste a block like that too.
4. Add the post at the top of the list in both `index.html` (home) and `post/index.html`:

```html
<article class="post-item">
  <h2><a href="/my-new-post/">Post title</a></h2>
  <p class="meta"><time datetime="YYYY-MM-DD">YYYY-MM-DD</time> <span class="labels">Label · Label</span></p>
  <p>One-sentence summary.</p>
</article>
```

5. Add the same post to `index.xml` and `post/index.xml` (title, link, guid, pubDate, description), and bump `lastBuildDate`. Add a `url` entry to `sitemap.xml`.
6. Check it with a static server from the repo root: `python3 -m http.server`. Open `/my-new-post/`, `/`, and `/post/`.

The `master` branch is what GitHub Pages publishes to miguelabate.com. Change a branch and merge when the post should go live.

Do not put a phone number, birthday, personal Gmail address, home town, or employer and client names on the site.
