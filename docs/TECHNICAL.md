# Technical Notes / 技术说明

## Architecture

The application is contained entirely in `index.html`:

- CSS provides the full-screen presentation and glass-style controls.
- Canvas renders stars, moonlight, rockets, trails, and particles.
- `requestAnimationFrame` drives the animation loop.
- Typed arrays cap particle and rocket counts for predictable memory use.
- Mouse and touch events share the same launch behavior.

## Heart geometry

Explosion velocities are sampled from the parametric heart curve:

```text
x = 16 sin³(t)
y = -(13 cos(t) - 5 cos(2t) - 2 cos(3t) - cos(4t))
```

Small random offsets keep the outline organic while the original gravity, drag, glow, and alpha-fade rendering remain intact.

## Deployment

GitHub Pages serves `index.html` from the root of the `main` branch. The project requires no build step and no external runtime dependencies.

GitHub Pages 直接发布 `main` 分支根目录中的 `index.html`，无需构建步骤或外部运行时依赖。
