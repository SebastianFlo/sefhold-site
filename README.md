# sefhold.com

Static parallax desert scene served by GitHub Pages at https://sefhold.com.

No build step and no JavaScript: `index.html` holds all markup and CSS, and `assets/` holds the layer images. Push to `main` to deploy.

## Layout

All vertical sizes use `cqh` (1% of the scene height), so the scene scales with the viewport height and portrait screens show a centre crop. The values reproduce the original design 1:1 at 1440×900.

| Layer | Image | Cycle |
|---|---|---|
| `.sky` | `background.webp` | static |
| `.layer--far` | `mountains-middle.webp` | 864 s |
| `.layer--mid` | `mountains-front.webp` | 288 s |
| `.layer--near` | `giraffe.svg` | 86.4 s |
| `.layer--front` | `tree.svg`, `clouds.webp` | 28.8 s |

Visitors with `prefers-reduced-motion: reduce` get a still scene.

## Images

The WebP layers were converted from the original PNGs with `cwebp -q 92 -m 6 -sharp_yuv` (add `-alpha_q 100` for transparent layers). Lower quality smooths away the sand grain.

## DNS

Cloudflare, DNS only (grey cloud): four `A` records for `@` pointing at `185.199.108–111.153`, `www` as a `CNAME` to `sebastianflo.github.io`, and the `_github-pages-challenge-SebastianFlo` TXT record for domain verification.
