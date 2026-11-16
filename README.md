# pastoral-margin-media

Public images and videos for Pastoral Margin social posts. Buffer reads each file from its raw GitHub link when a post publishes, so this repository must stay public and files must stay where they are.

## How a file becomes a link

Every file on `main` has a permanent public link:

```
https://raw.githubusercontent.com/SonofThor23/pastoral-margin-media/main/<path>
```

For example, the Monday quote card for the week of Nov 16, 2026:

```
https://raw.githubusercontent.com/SonofThor23/pastoral-margin-media/main/2026/11-16-week/ig-mon-quote-card-guidebook.jpg
```

## Folder layout

Files are grouped by year, then by the Monday that starts the posting week:

```
2026/
  11-16-week/        posts for Mon Nov 16 to Sun Nov 22, 2026
  11-23-week/
  ...
2027/
  01-04-week/
```

- Year folder: `YYYY`
- Week folder: `MM-DD-week`, where `MM-DD` is that week's Monday
- Everything for one week sits in its week folder, with no subfolders. The file name says the platform, day, and post type.

## Naming convention

All names are lowercase, words joined with hyphens, no spaces.

### Images (quote cards, carousels, single feed images)

```
<platform>-<day>-<type>-<slug>.jpg
```

| Part | Values |
| --- | --- |
| platform | `ig` (Instagram), `x` (X) |
| day | `mon`, `tue`, `wed`, `thu`, `fri`, `sat`, `sun` |
| type | `quote-card`, `carousel`, `image` |
| slug | 1 to 3 words from the post's topic, such as `guidebook` or `quiet-time` |

**Quote card:** one file per card.

```
ig-mon-quote-card-guidebook.jpg
```

**Carousel slides:** one file per slide, with a two-digit slide number at the end, starting at `01`. The numbers set the slide order in Buffer, so keep them two digits (`01` to `10`).

```
ig-wed-carousel-quiet-time-01.jpg
ig-wed-carousel-quiet-time-02.jpg
...
ig-wed-carousel-quiet-time-07.jpg
```

### Videos

**Reels and Shorts** posted on a set day:

```
reel-<day>-<slug>-vertical.mp4
```

Example: `reel-fri-my-warning-signs-vertical.mp4`

**Vlog clips** that are reused across platforms and days (vertical for Reels and Shorts, square for X):

```
clip<N>-<slug>-<vertical|square>.mp4
```

`N` is the clip number from that week's clip notes. Examples: `clip1-20-hours-vertical.mp4`, `clip1-20-hours-square.mp4`.

## Rules

- **Never move, rename, or delete a file once a post uses it.** Buffer fetches the file when the post goes out, and a changed path breaks the post. This includes posts that already published, since Buffer may re-fetch them.
- To fix an image after it is scheduled, replace the file at the same path (same name) and commit to `main`. The link stays the same.
- Use JPG for images and MP4 (H.264) for video. Keep each file under 100 MB (GitHub's limit per file).
- Commit straight to `main`. Raw links only work for files on `main`.
