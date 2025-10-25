# 🎬 Kristian Gabriel – AE Scripts & Expressions Handbook
Welcome to your central library of After Effects expressions and micro-training modules. Each category includes explanations, examples, and professional shortcuts for motion design, rigging, and automation.

---

## 📘 Table of Contents
- [Introduction to Expressions](#-introduction-to-after-effects-expressions)
- [Core Animation](#-core-animation)
- [Core Animation – Part II: Practical Motion Recipes](#core-animation-part-ii)
- [Text & Type](#text-and-type)
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

---
<a id="core-animation-part-ii"></a>
## 🎬 Core Animation – Part II: Practical Motion Recipes
This is your hands-on module. Each recipe explains what it does, where to apply it, how to set it up, and how to tune it.

### 🪄 Prerequisites (one-time rig)
Create a Null named **CTRL** and add three *Slider Controls* (Amp, Freq, Decay). Then use them in any expression:

```js
ctrl=thisComp.layer("CTRL");
amp =ctrl.effect("Amp")("Slider");
freq=ctrl.effect("Freq")("Slider");
decay=ctrl.effect("Decay")("Slider");

```
Suggested starting values: Amp **30**, Freq **3**, Decay **4**.

────────────────────────────────────────────────────────────────────────

### 1) Elastic Overshoot — consistent rebound
**What it does:** Adds a springy rebound as the layer comes to rest (same size every time).  
**When to use:** Logo pop-ins, buttons releasing, icons landing.  
**Where:** Scale, Position, or Rotation of the animated layer.

**How to set up (quick):**
1) Keyframe your base move (optional, but looks best).
2) Paste the expression on the target property.

**Expression:**
```js
t=time-inPoint;
value + amp*Math.sin(freq*t*2*Math.PI)*Math.exp(-decay*t);
```

**Tune:** Higher **Decay** = quicker settle; higher **Freq** = tighter bounce; lower **Amp** = subtler.  
**Example workflow:** Animate Scale 0%→100% in 12f. Amp 25, Freq 3.5, Decay 5 for a tidy logo pop.

────────────────────────────────────────────────────────────────────────

### 2) Elastic Overshoot — velocity-based (reactive)
**What it does:** Overshoot size responds to the actual **arrival speed** at the last keyframe.  
**When to use:** Physical UI, character hits, panels that slam vs. drift.  
**Where:** Any **keyframed** property.

**How to set up:**
1) Animate your layer to a key pose.
2) Paste the expression on that property.

**Expression:**
```js
// normalize CTRL sliders for velocity use
amp  = amp/200;
freq = freq/30;
decay= decay/10;

n=(numKeys>0)?nearestKey(time).index:0;
if(n && key(n).time>time) n--;
if(n>0){
  t=time-key(n).time;
  v=velocityAtTime(key(n).time - thisComp.frameDuration/10);
  value + v*amp*Math.sin(freq*t*2*Math.PI)*Math.exp(-decay*t);
}else{
  value;
}
```

**Tune:** If it “snaps” at the key, increase the sample offset to `thisComp.frameDuration/5`.  
**Example workflow:** Big panel flies in, smaller card glides in. Same expression → panel overshoots more because it’s faster.

────────────────────────────────────────────────────────────────────────

### 3) Delay Chain — “follow the leader”
**What it does:** Duplicates trail a leader with a per-layer time offset (beautiful cascades).  
**When to use:** Stacks of cards, ribbons, list reveals, dot trails.  
**Where:** Followers’ Position/Rotation/Scale.

**How to set up:**
1) Name your lead layer **Leader**.
2) Duplicate your follower layers.
3) Paste on followers’ animated property.

**Expression:**
```js
leader=thisComp.layer("Leader");
delayPerLayer=0.05; // seconds between indices
lag=(thisLayer.index - leader.index) * delayPerLayer;
valueAtTime(time - lag);
```

**Tune:** Smaller **delayPerLayer** = tighter wave; larger = more laggy flow.  
**Example workflow:** Animate Position on Leader only → duplicate 8x → instant cascading reveal.

────────────────────────────────────────────────────────────────────────

### 4) Anticipation — pre-motion nudge
**What it does:** Tiny “wind-up” before motion that clarifies intent and adds snap.  
**When to use:** Characters, cursors, buttons about to move.  
**Where:** Position.

**How to set up:** Paste on the moving layer’s Position (works with or without additional keys).

**Expression:**
```js
lead=0.06;          // seconds of look-ahead
nudge=[-20,0];      // oppose main move (example: going right → nudge left)
t=time + lead;
valueAtTime(t) + nudge*Math.exp(-t*10);
```

**Tune:** Shorter **lead** = snappier cue; adjust **nudge** direction/amount for taste.  
**Example workflow:** Button grows on hover → add a tiny left nudge before its rightward slide.

────────────────────────────────────────────────────────────────────────

### 5) Follow-Through — secondary settle
**What it does:** Child parts trail and settle after the body stops (inertia).  
**When to use:** Flags, pointers, accents, limbs.  
**Where:** Rotation or Position of the *trailing* piece.

**How to set up:** Parent the trailing piece to the main object. Paste on the trailer.

**Expression:**
```js
lag = 0.08;  // how far behind
damp= 6;     // higher = crisper stop
base = valueAtTime(time - lag);
delta= value - base;
base + delta*Math.exp(-damp*lag);
```

**Tune:** Increase **lag** for softer drag; increase **damp** for a quicker stop.  
**Example workflow:** A pointer arrow rotates; its tail cap follows with lag for lively overlap.

────────────────────────────────────────────────────────────────────────

### 6) Bounce & Drop — gravity + energy loss
**What it does:** Simulates vertical drop with diminishing bounces.  
**When to use:** Dropping icons, chips, badges.  
**Where:** Position (Y).

**How to set up:** Paste on Position and set `floorY` to your ground.

**Expression:**
```js
g=1800;          // gravity
b=0.45;          // bounciness (0..1)
floorY=900;      // ground Y

t=time - inPoint;
y=value[1] + g*t*t/2;

if (y>floorY){
  t = Math.sqrt(2*(y-floorY)/g);
  v = g*t*(1-b);
  y = floorY - v*v/(2*g);
}
[value[0], y];
```

**Tune:** Lower **b** = flatter, higher **b** = rubberier. Adjust **floorY** to your comp.  
**Example workflow:** Badge drops into frame, hits “ground,” then settles with two quick diminishing bounces.

────────────────────────────────────────────────────────────────────────

### 7) Squash & Stretch — speed-aware (smoothed)
**What it does:** Deforms Scale based on **motion speed**, smoothed to avoid jitter; returns to 100% at rest.  
**When to use:** Bouncy UI chips, balls, stickers; character motion.  
**Where:** Scale.

**How to set up (self-driven):** Layer (or its parent) must actually move.

**Expression (self-driven):**
```js
maxSquash=22; normSpeed=800; smoothWin=0.10; samples=5;
dt=thisComp.frameDuration;

function spdAt(t){
  p1=transform.position.valueAtTime(t);
  p0=transform.position.valueAtTime(t - dt);
  v=(p1-p0)/dt;
  return length(v);
}

sum=0;
for(i=0;i<samples;i++){
  tt=time - i*(smoothWin/Math.max(1,(samples-1)));
  sum+=spdAt(tt);
}
spd=sum/samples;

k = clamp(spd/normSpeed,0,1);
sx=100 + (maxSquash*k);
sy=100 - (maxSquash*k);
[sx,sy];
```

**Alternative (leader-driven):** Works even if this layer is static; follows a layer named “Leader”.
```js
leader=thisComp.layer("Leader");
maxSquash=22; normSpeed=800; smoothWin=0.10; samples=5;
dt=thisComp.frameDuration;

function spdAt(t){
  p1=leader.transform.position.valueAtTime(t);
  p0=leader.transform.position.valueAtTime(t - dt);
  v=(p1-p0)/dt;
  return length(v);
}

sum=0;
for(i=0;i<samples;i++){
  tt=time - i*(smoothWin/Math.max(1,(samples-1)));
  sum+=spdAt(tt);
}
spd=sum/samples;

k = clamp(spd/normSpeed,0,1);
sx=100 + (maxSquash*k);
sy=100 - (maxSquash*k);
[sx,sy];
```

**Optional add-on (Rotation → face travel direction):**
```js
dt=thisComp.frameDuration;
p1=transform.position;
p0=transform.position.valueAtTime(time-dt);
v=p1-p0; spd=length(v);
(spd>0.1)?radiansToDegrees(Math.atan2(v[1],v[0])):value;
```

**Tune:** Lower **maxSquash** for subtlety; raise **normSpeed** if your motion is fast; increase **smoothWin/samples** to calm jitter.  
**Example workflow:** Ball moves across screen (Position keys). S&S on Scale delivers lively stretch on fast parts, subtle squash on slowdowns, and returns to 100% when still.

────────────────────────────────────────────────────────────────────────

### 8) Loops & Oscillation — perpetual motion
**What it does:** Keeps motion alive either from keyframes (ping-pong) or pure math (oscillator).  
**When to use:** Breathing icons, pulsing lights, pendulums.  
**Where:** Any property.

**How to set up:** Paste one of the following.

**Ping-pong existing keys:**
```js
loopOut("pingpong");
```

**Time-based oscillator (no keys):**
```js
amp=15; freq=1.2;
value + amp*Math.sin(freq*time*2*Math.PI);
```

**Tune:** Use small **amp** for tasteful “alive” motion.  
**Example workflow:** Two keyframes on Rotation for a small swing → `loopOut("pingpong")` → endless pendulum.

────────────────────────────────────────────────────────────────────────

### 9) Marker-Triggered Pop — manual beats/cues
**What it does:** Fires a quick bounce exactly on your **layer markers**.  
**When to use:** Musical hits, UI pips, timed pulses.  
**Where:** Scale or Opacity.

**How to set up:**
1) Add markers (`*` shortcut) where hits should happen.
2) Paste on the property.

**Expression:**
```js
n=0;
if(marker.numKeys>0){
  n=marker.nearestKey(time).index;
  if(marker.key(n).time>time) n--;
}
if(n>0){
  t=time - marker.key(n).time;
  value + 30*Math.sin(6*t*2*Math.PI)*Math.exp(-5*t);
}else{
  value;
}
```

**Tune:** Adjust the `30`, `6`, and `5` trinity (amplitude, frequency, decay) to fit your track.  
**Example workflow:** Place markers on kick hits; Scale pulses perfectly in sync.

────────────────────────────────────────────────────────────────────────

### 🔧 Troubleshooting (quick)
• Nothing happens → confirm layer names (`CTRL`, `Leader`), property target, and that the object (or leader) actually moves.  
• Too wild → lower **Amp**, raise **Decay**, reduce **Freq**.  
• Velocity overshoot snaps → increase the sample offset (`frameDuration/5`).  
• Followers misaligned → positive `delayPerLayer`, correct leader index.  
• S&S does nothing → ensure motion or use the leader-driven variant.

────────────────────────────────────────────────────────────────────────

Next → **Text & Type**: apply these same motion principles to typography (per-character delays, overshoots, and rhythm).

<a id="text-and-type"></a>
## 🔠 Text & Type — Practical Motion Recipes
This is your typography lab. Each recipe below includes full explanations, step-by-step setup, tuning tips, and real-world usage.

────────────────────────────────────────────────────────────────────────

### 🧭 Working with Text Expressions
Text layers have two main areas for expressions:

• **Source Text**  →  changes the text itself (typewriter, counters, scrambles).  
• **Animators + Expression Selector**  →  controls per-character/word/line transforms (opacity, scale, position, color).

Basic rule:  *Source Text* = modify content.  
*Animators* = modify motion/look per character.

────────────────────────────────────────────────────────────────────────

### 1) Typewriter — character by character
**What it does:** reveals letters one at a time, like live typing.  
**Where:** on **Source Text**.  
**How:**
1. Type your full sentence.  
2. Alt/Option-click Source Text stopwatch.  
3. Paste the code below.

```js
speed=12;                          // characters per second
s=value.toString();
n=Math.floor((time-inPoint)*speed);
n=clamp(n,0,s.length);
s.substr(0,n);
```
**Optional cursor:**  
```js
speed=12;
cursorOn=Math.sin(time*8)>0;
s=value.toString();
n=Math.floor((time-inPoint)*speed);
n=clamp(n,0,s.length);
s.substr(0,n)+(cursorOn?"|":"");
```
**Tune:** adjust **speed**.  
**Example:**  dialogue bubbles, console text, subtitles.

────────────────────────────────────────────────────────────────────────

### 2) Typewriter — word by word
**What it does:** reveals full words sequentially.  
**Where:** **Source Text**.

```js
delay=0.20;                         // seconds per word
words=value.toString().split(" ");
count=Math.floor((time-inPoint)/delay);
count=clamp(count,0,words.length);
words.slice(0,count).join(" ");
```
**Use:** taglines, lyric subtitles, timed quotes.

────────────────────────────────────────────────────────────────────────

### 3) Character Cascade — fade/slide reveal
**What it does:** each character (or word/line) appears with offset timing and motion.  
**Where:** in a **Text Animator** with *Opacity 0%* and optional *Position [0,20]*.  
Add an **Expression Selector** and paste on **Amount**.

```js
delay=0.03;rise=0.15;
t=time-inPoint-(textIndex-1)*delay;
ease(t,0,rise,0,100);
```
**Tune:** delay = spacing, rise = duration.  
**Example:** kinetic subtitles, lyric reveals, info lists.

────────────────────────────────────────────────────────────────────────

### 4) Elastic Overshoot per Character
**What it does:** each character pops in with a bounce.  
**Where:** Text Animator → Scale (+40,+40) → Expression Selector → Amount.

```js
delay=0.035;amp=60;freq=5;decay=6;
t=time-inPoint-(textIndex-1)*delay;
kick=amp*Math.sin(freq*t*2*Math.PI)*Math.exp(-decay*t);
clamp(kick,0,100);
```
**Tune:**  
• amp → strength  
• freq → bounces  
• decay → settle speed  
**Example:** energetic headlines, emoji pops, promo titles.

────────────────────────────────────────────────────────────────────────

### 5) Word / Line Stagger (reusable)
**What it does:** same cascade logic, usable for Characters, Words, or Lines depending on “Based On.”  
**Where:** any Text Animator → Expression Selector → Amount.

```js
delay=0.08;dur=0.18;
t=time-inPoint-(textIndex-1)*delay;
ease(t,0,dur,0,100);
```
Switch **Based On** to Words or Lines as needed.  
**Example:** multiline intros, caption slides.

────────────────────────────────────────────────────────────────────────

### 6) Random Scramble → Resolve
**What it does:** scrambles characters then resolves to the final text.  
**Where:** **Source Text**.

```js
charset="ABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789";
stepDur=0.05;
txt=value.toString();
elapsed=Math.max(0,time-inPoint);
revealCount=Math.floor(elapsed/stepDur);
out="";
for(i=0;i<txt.length;i++){
 if(i<revealCount) out+=txt[i];
 else if(txt[i]==" ") out+=" ";
 else{
  seedRandom(i+Math.floor(time*20),true);
  out+=charset[Math.floor(random(charset.length))];
 }
}
out;
```
**Tune:** smaller stepDur = faster resolve.  
**Example:** HUDs, sci-fi titles, digital counters.

────────────────────────────────────────────────────────────────────────

### 7) Numeric Counter
**What it does:** counts from start → end smoothly.  
**Where:** **Source Text**.

```js
start=0;end=1000;
t0=inPoint;t1=inPoint+2;
decimals=0;
v=linear(time,t0,t1,start,end);
v=(time<t0)?start:(time>t1)?end:v;
prefix="";suffix="";
formatted=decimals>0?v.toFixed(decimals):Math.round(v).toString();
prefix+formatted+suffix;
```
**Example:** progress %, dollar totals, milliseconds.  
Change prefix/suffix for units or currency.

────────────────────────────────────────────────────────────────────────

### 8) Slide-Up + Fade
**What it does:** each character slides upward and fades in.  
**Where:** Text Animator with *Position [0,20]* and *Opacity 0%*, Expression Selector → Amount.

```js
delay=0.025;dur=0.12;
t=time-inPoint-(textIndex-1)*delay;
ease(t,0,dur,0,100);
```
**Example:** modern UI titles, app onboarding text, credits.

────────────────────────────────────────────────────────────────────────

### 9) Color Pulse Accent
**What it does:** adds a brief color pulse as text reveals.  
**Where:** Text Animator → Fill Color RGB → Expression Selector → Amount.

```js
delay=0.03;dur=0.10;overshoot=120;
t=time-inPoint-(textIndex-1)*delay;
val=ease(t,0,dur,0,100);
(Math.abs(Math.sin(t*6))>0.9)?overshoot:val;
```
**Tip:** keep overshoot ≤120 for subtle shimmer.  
**Example:** highlight key words, lyric beats.

────────────────────────────────────────────────────────────────────────

### 🔧 Troubleshooting
• Nothing happens → confirm you’re on the correct property (Source Text vs. Expression Selector Amount).  
• All text appears instantly → check “Based On” in selector.  
• Timing off → tweak delay/dur.  
• Scramble unreadable → shorten stepDur.  
• Counter jumps → adjust t0/t1 and decimals.

────────────────────────────────────────────────────────────────────────

### 🧪 Quick Exercises
1. Create a typewriter headline with a blinking cursor.  
2. Add a slide-up cascade reveal (delay 0.02 s).  
3. Combine elastic overshoot with color pulse for a lively promo title.  
4. Make a numeric counter showing $0 → $999 over 3 s.  
5. Try a scramble→resolve effect for a “SYSTEM ONLINE” text.

────────────────────────────────────────────────────────────────────────

Next → **Motion & Physics:** explore realistic drifts, inertia, and simulated forces for both text and graphics.
```
