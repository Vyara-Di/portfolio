[README.md](https://github.com/user-attachments/files/28909560/README.md)
# project-01.html — File Guide

Standalone project page for **LG Electronics Inc.** — part of the Vyara Di portfolio.

---

## Folder structure

```
project-01.html
images/
  project-01/
    hero.jpg              ← Project hero (fullbleed, below page title)
    overview-01.jpg       ← Overview section, large panoramic image
    process-01.jpg        ← Section Two, left composition
    process-02.jpg        ← Section Two, right composition (flipped)
    explore-01.jpg        ← Section Three, masonry col 1
    explore-02.jpg        ← Section Three, masonry col 2
    explore-03.jpg        ← Section Three, masonry col 3
    explore-04.jpg        ← Section Three, masonry col 4
    detail-01.jpg         ← Section Four, left column
    detail-03.jpg         ← Section Four, right accent column
    impact-02.jpg         ← Section Five, horizontal scroll — slot 2
    impact-03.jpg         ← Section Five, horizontal scroll — slot 3
    impact-04.jpg         ← Section Five, horizontal scroll — slot 4

videos/
  project-01/
    intro.mp4             ← INTRO position (fullbleed strip, replaces image)
    overview-02.mp4       ← OVERVIEW-02 position (pair slot left)
    overview-03.mp4       ← OVERVIEW-03 position (pair slot right)
    detail-02.mp4         ← DETAIL-02 position (Section Four, centre column)
    impact-01.mp4         ← IMPACT-01 position (Section Five, horizontal scroll — slot 1)
```

---

## Video positions

Five image slots have been replaced with `<video>` elements. All videos use the same attributes:

```html
autoplay muted loop playsinline preload="metadata"
```

| Position | File | Location in page | Layout context |
|---|---|---|---|
| **Intro** | `videos/project-01/intro.mp4` | Fullbleed strip immediately after the project hero | `.p-vid-full` — 82 vh tall, `object-fit: cover` |
| **Overview-02** | `videos/project-01/overview-02.mp4` | Overview section, pair — left slot | `.fig.r43` inside `.pair` |
| **Overview-03** | `videos/project-01/overview-03.mp4` | Overview section, pair — right slot | `.fig.r43` inside `.pair` |
| **Detail-02** | `videos/project-01/detail-02.mp4` | Section Four (lay-layer), centre column | `.fig.l-front.r45` |
| **Impact-01** | `videos/project-01/impact-01.mp4` | Section Five horizontal scroll, first card | `.fig.r45` inside `.lay-seq` |

---

## Replacing a video file

Drop the new file into `videos/project-01/` using the exact filename listed above. The page references files by path, so no HTML edits are needed as long as the name matches.

To change a filename, update the `src` attribute on the relevant `<video>` tag.

---

## Notes

- Video figures carry the class `is-video`, which disables the zoom-cursor behaviour and the lightbox click handler that applies to images.
- The Intro video uses its own wrapper class `.p-vid-full` (parallax not applied). All other video figures sit inside standard `.fig` wrappers and inherit the existing layout rules (aspect ratio, reveal animations, scroll stagger).
- All five videos autoplay silently in a loop. For accessibility the `aria-label` attribute describes the clip — update this to match your actual content.
- Recommended formats: **MP4 (H.264)** for broadest browser support; add a `<source type="video/webm">` sibling for smaller file sizes on supporting browsers.
