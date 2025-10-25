# 🎬 Kristian Gabriel — AE Scripts & Expressions Handbook

Welcome! This page is a living handbook of After Effects expressions with short, copy-ready snippets and how to use them.

## Table of Contents
- [Elastic & Bounce](#elastic--bounce)
- [Text & Type](#text--type)
- [Utility & Rigs](#utility--rigs)

---

## Elastic & Bounce

### Elastic Overshoot (paste on Scale/Position/Rotation)
```js
amp = 20; freq = 3; decay = 5;
value + amp*Math.sin(freq*time*Math.PI)*Math.exp(-decay*time);
