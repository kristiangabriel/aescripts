# 🎬 Kristian Gabriel – AE Scripts & Expressions Handbook
Welcome to your central library of After Effects expressions and micro-training modules. Each category includes explanations, examples, and professional shortcuts for motion design, rigging, and automation.

---

## 📘 Table of Contents
- [Introduction to Expressions](#-introduction-to-after-effects-expressions)
- [Core Animation](#-core-animation)
- [Text & Type](#-text--type)
- [Motion & Physics](#-motion--physics)
- [Controllers & Rigging](#-controllers--rigging)
- [Color & Lighting](#-color--lighting)
- [Time & Looping](#-time--looping)
- [Utility & Automation](#-utility--automation)
- [Project Management / Organization](#-project-management--organization)

---

## 🧠 Introduction to After Effects Expressions

## What Are Expressions?

Expressions are **tiny bits of code that control animation** inside After Effects.  
Instead of adding dozens of keyframes, you can describe how something behaves using a simple line or two of logic.

At their core, expressions tell a property *how* to change over time.  
They’re written in a scripting language **based on JavaScript**—but simplified and tailored for motion graphics.  
You don’t need to be a programmer.  
You just need to understand a few patterns: how to refer to a value, do basic math, and connect one property to another.

When you write an expression, you’re not replacing animation skills—you’re *enhancing* them.  
Expressions automate repetitive actions, create natural physics, link layers together, and let you explore creative motion that would take hours to keyframe manually.

---

## The Big Difference: Keyframes vs. Expressions

| Concept | Keyframes | Expressions |
|----------|------------|-------------|
| How it works | You set values at specific frames and AE interpolates between them. | You describe a rule or relationship; AE calculates values automatically each frame. |
| Example | Scale 0% → 100% over 1 second | `value + 10*Math.sin(time*2*Math.PI)` |
| Flexibility | Static — must be updated by hand. | Dynamic — updates automatically, even if timing changes. |

You can even *mix* them.  
Add keyframes first, then apply an expression on top to enhance the motion—AE simply layers the math over your keyframed base value.

---

## You Don’t Need to Know Full JavaScript

After Effects expressions use **a limited, friendly subset of JavaScript** called *ExtendScript Expressions*.  
It’s purpose-built for artists, not developers.  
Here’s the good news:

- You’ll **never** write full web-style JavaScript with functions, objects, and DOM calls.  
- You’ll mainly use small formulas—often one or two lines.  
- AE gives you built-in variables like `time`, `value`, `thisComp`, and helper functions like `wiggle()`, `linear()`, and `ease()`.

Think of it like learning to drive a car without becoming a mechanic.  
You’ll use the controls, not build the engine.

---

## Where Expressions Live

Every property that can be keyframed (Position, Scale, Opacity, Rotation, etc.) can also hold an expression.

1. **Alt-click (Windows)** or **Option-click (Mac)** the stopwatch icon next to the property.  
2. A small text field appears below it.  
3. Type or paste your expression.  
4. Press **Enter** (numpad) or **Return** to apply it.

If the code is valid, AE displays it in red text and animates immediately.  
If there’s an error, you’ll see a warning with a description—often as simple as a missing semicolon or parenthesis.

---

## How Expressions Think

When AE reads your expression:
1. It looks at the property’s current value (that’s the special variable `value`).  
2. It evaluates your code **for every frame** of the timeline.  
3. It returns a new value to display.

So an expression is a *formula* continuously evaluated—like a live calculator for motion.

Example idea:
> “Every frame, move the layer 50 pixels above another layer.”

That’s one line:
```js
thisComp.layer("Hero").transform.position - [0,50]
```
---

## 🎬 Core Animation

### Why Core Animation Matters
Core Animation is where expressions come alive.  
If the Introduction taught you *what* expressions are and *why* they exist, this section teaches you *how they shape motion itself.*

At its heart, animation is storytelling through movement.  
Expressions give that movement intelligence—turning static transitions into living, responsive motion. They let you describe *how* something should behave, not just *where* it should go. Whether it’s a bouncing logo, a button reacting to touch, or a swarm of layers cascading in rhythm, Core Animation builds the foundation for believable energy and timing.

Think of it as your first step into **expressive motion logic**: how to make After Effects understand physics, weight, anticipation, and reaction—all through a few lines of math and relationships between layers.

---

### The Mental Model
Before diving into code, it’s important to understand *how animators think when they use expressions*.

- **Keyframes define intention.**  
  They say, “Move from here to there.”  

- **Expressions define behavior.**  
  They say, “Move like this.”

Instead of manually animating every easing curve or bounce, you describe a motion rule—something like:
> “Every time this object lands, give it a little spring.”

That rule can apply to one layer or a hundred layers simultaneously.  
Core Animation is where that shift happens—from keyframe-by-keyframe design to *systemic animation thinking.*

---

### Quick Setup: Building a Safe Playground
Before any advanced work, it helps to build a quick testing setup:
1. **Create a Null layer** named `CTRL`.  
2. Add a few **Expression Controls → Slider Controls** and rename them “Amp,” “Freq,” and “Decay.”  
3. These act as universal dials to adjust the intensity, speed, and smoothness of any animation later.

You’re not writing code yet—you’re preparing your environment.  
These sliders become your “motion DNA”—a way to control how energy travels through your scene.

---

### The Philosophy of Core Motion
Every great animation—no matter how complex—comes down to a few timeless principles:
- **Anticipation**: the small pre-movement before an action.  
- **Overshoot**: the satisfying rebound after reaching a destination.  
- **Follow-Through**: parts of an object continuing to move after the main body stops.  
- **Delay and Offset**: staggered timing to create natural flow.  
- **Loops and Repetition**: energy that feels continuous, alive, rhythmic.  

Expressions don’t replace these principles—they **amplify** them.  
By describing them mathematically, you can repeat and control them endlessly without manually adjusting keyframes.

---

### Where You’re Headed Next
In the coming Core Animation modules, we’ll translate these ideas into action:
- How to build an elastic overshoot with a few lines of math.  
- How to make objects react with follow-through automatically.  
- How to offset animations so entire compositions flow together.  
- And how to loop or oscillate motion for dynamic, self-sustaining energy.

You’ll start small—just sliders and shapes—and end up creating motion systems that behave like living organisms.

> The goal isn’t to memorize code.  
> It’s to learn to think like motion behaves.

Once you’ve built this foundation, everything else—Text Animation, Physics, Rigging—builds effortlessly on top.

---

> 🪄 *Next:* “Core Animation – Part II” introduces the first real movement recipes: Elastic Overshoot, Delay Chains, and Follow-Through.
