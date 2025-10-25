# 🎬 Kristian Gabriel – AE Scripts & Expressions Handbook

Welcome to your central library of After Effects expressions and micro-training modules.  
Each category includes explanations, examples, and professional shortcuts for motion design, rigging, and automation.

---

## 📘 Table of Contents
- [Core Animation](#core-animation)
- [Text & Type](#text--type)
- [Motion & Physics](#motion--physics)
- [Controllers & Rigging](#controllers--rigging)
- [Color & Lighting](#color--lighting)
- [Time & Looping](#time--looping)
- [Utility & Automation](#utility--automation)
- [Project Management / Organization](#project-management--organization)

---

## 🎬 Core Animation
Elastic, bounce, damping, and motion-flow expressions for shape and logo animation.

### Elastic Overshoot
```js
amp = 20; freq = 3; decay = 5;
value + amp*Math.sin(freq*time*Math.PI)*Math.exp(-decay*time);
