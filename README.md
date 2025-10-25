# 🎬 Kristian Gabriel – AE Scripts & Expressions Handbook
Welcome to your central library of After Effects expressions and micro-training modules. My name is Kristian Gabriel, Creative Director,Graphic & Motion Design Artist, and other things they haven't defined yet. LOL. The following is a WORK IN PROGRESS and something I wish I would have had when I was learning After Effects. Once again, this is a work in progress and there are definitely issues and errors. Please bring them to my attention and I would be happy to fix them. I fully acknowledge that every motion designer will do and code things differently and thats okay! At the end of the day its about all of us getting our work done and meeting those deadlines. I have information, you have information, we all have information and between...hopefully all this can help those who need it. Anyways! Each category includes explanations, examples, and professional shortcuts for motion design, rigging, and automation. Hope you have fun and enjoy!

---

## 📘 Table of Contents
- [Introduction to Expressions](#-introduction-to-after-effects-expressions)
- [Core Animation](#-core-animation)
- [Core Animation – Part II: Practical Motion Recipes](#core-animation-part-ii)
- [Text & Type](#text-and-type)
- [Motion & Physics](#motion-and-physics)
- [Controllers & Rigging](#controllers-and-rigging)
- [Color & Lighting](#color-and-lighting)
- [Environmental FX & Camera Systems](#environmental-fx-and-camera-systems)
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

<a id="motion-and-physics"></a>
## 🌪️ Motion & Physics — Practical Motion Recipes
This section explores motion that feels *real* — with momentum, drag, gravity, friction, and follow-through.  
You’ll learn how to add inertia to any property, simulate floating drift, create gravitational pull, and add realistic damped spring motion.

────────────────────────────────────────────────────────────────────────

### 🧭 Quick Note on Approach
All “physics” here are simplified — they use **expressions**, not simulations.  
You can paste these directly on Position, Rotation, or custom properties.  
They’re designed to feel *cinematic* and responsive without needing plugins.

────────────────────────────────────────────────────────────────────────

### 1) Inertia / Momentum
**What it does:** continues motion naturally after the keyframes stop, gradually slowing down.  
**Where:** any keyframed property (Position, Rotation, Scale).

**How to set up:**
1. Animate your layer as usual (ending keyframes).  
2. Paste this on the animated property.

```js
n = 0;
if (numKeys > 0){
  n = nearestKey(time).index;
  if (key(n).time > time) n--;
}
if (n == 0){
  value;
}else{
  t = time - key(n).time;
  v = velocityAtTime(key(n).time - thisComp.frameDuration/10);
  amp = .85;    // momentum strength
  decay = 4;    // drag (higher = stops faster)
  value + v*amp*Math.exp(-decay*t);
}
```

**Tune:**  
- Lower `decay` for slower, gliding stops.  
- Raise `amp` for more momentum.  
**Example:** Camera drift after stop, UI panel easing to rest.

────────────────────────────────────────────────────────────────────────

### 2) Floating Drift / Ambient Motion
**What it does:** continuous slow, smooth random drift for background elements.  
**Where:** Position or Rotation.

```js
amp = [20,10];   // movement amplitude X,Y
freq = 0.08;     // cycles per second
seedRandom(index,true);
[sin(time*freq*2*Math.PI)*amp[0],
 cos(time*freq*2*Math.PI)*amp[1]]
```

**Tune:**  
- Lower `freq` for slower motion.  
- Adjust amplitude for subtle or large sway.  
**Example:** Floating HUD panels, hovering icons, parallax layers.

────────────────────────────────────────────────────────────────────────

### 3) Friction (Progressive Resistance)
**What it does:** simulates gradual deceleration over time — like air resistance.  
**Where:** any continuously animated property.

```js
vel = velocity;       // built-in velocity at this frame
fric = 0.85;          // 0–1 range (lower = more resistance)
value - vel*(1-fric);
```

**Tip:** combine with looped or oscillating animation for more natural slowing.  
**Example:** mechanical dials, rotating wheels, swinging pointers.

────────────────────────────────────────────────────────────────────────

### 4) Spring Physics (Hooke’s Law)
**What it does:** creates a spring that pulls toward a target value with realistic bounce.  
**Where:** Position, Scale, or Rotation.

```js
target = thisComp.layer("CTRL").transform.position; // or any target
stiffness = 5;    // higher = stiffer spring
damping   = 1.5;  // higher = more damped
mass      = 1;

t = time - inPoint;
x = value - target;
accel = (-stiffness/mass)*x - damping*velocity/mass;
value + accel;
```

**Tune:**  
- Lower `damping` = bouncier.  
- Higher `stiffness` = tighter spring.  
**Example:** camera rig sway, UI follow, connected elements.

────────────────────────────────────────────────────────────────────────

### 5) Gravity Drop
**What it does:** simulates a simple fall under gravity with optional bounce.  
**Where:** Position (Y-axis typically).

```js
g = 1200;        // gravity
b = 0.6;         // bounce coefficient (0–1)
floor = 800;     // ground Y
t = time - inPoint;
y = value[1] + g*t*t/2;
if (y > floor){
  t = Math.sqrt(2*(y-floor)/g);
  v = g*t*(1-b);
  y = floor - v*v/(2*g);
}
[value[0], y];
```

**Tune:**  
- Lower `b` for flatter bounces.  
- Adjust `floor` for comp height.  
**Example:** falling logo, icon drop-in, physics toys.

────────────────────────────────────────────────────────────────────────

### 6) Orbit / Centripetal Force
**What it does:** keeps a layer orbiting another layer’s position in circular motion.  
**Where:** Position.

```js
center = thisComp.layer("CENTER").transform.position;
radius = 200;
speed  = 1.2;       // rotations per second
angle  = time*speed*2*Math.PI;
[center[0] + Math.cos(angle)*radius,
 center[1] + Math.sin(angle)*radius];
```

**Tip:** animate `radius` or `speed` for dynamic orbits.  
**Example:** spinning satellites, atomic diagrams, UI radar sweeps.

────────────────────────────────────────────────────────────────────────

### 7) Follow / Chase (Smooth Target Tracking)
**What it does:** makes a layer follow another with lag and smoothing.  
**Where:** Position.

```js
leader = thisComp.layer("Leader");
lag = 0.25;         // seconds of delay
follow = leader.transform.position.valueAtTime(time - lag);
damp = 8;           // damping for extra smoothness
linear(value, follow, follow, follow, value + (follow - value)/damp);
```

**Example:** camera follow shots, trailing icons, soft object pursuit.

────────────────────────────────────────────────────────────────────────

### 8) Pendulum Swing
**What it does:** oscillating rotation like a pendulum with natural decay.  
**Where:** Rotation.

```js
amp = 45;      // degrees
freq = 0.5;    // swings per second
decay = 0.8;   // exponential damping
amp*Math.sin(freq*time*2*Math.PI)/Math.exp(decay*time);
```

**Tune:**  
- Smaller `decay` = longer swing.  
- Higher `amp` = wider swing.  
**Example:** hanging signs, character tails, swinging lamps.

────────────────────────────────────────────────────────────────────────

### 9) Dampened Oscillator (Universal Bounce)
**What it does:** reusable “bounce physics” for any property.  
**Where:** any keyframed property.

```js
amp = .6; freq = 3; decay = 5;
n = 0;
if (numKeys > 0){
  n = nearestKey(time).index;
  if (key(n).time > time) n--;
}
if (n == 0){ value; }
else {
  t = time - key(n).time;
  v = velocityAtTime(key(n).time - thisComp.frameDuration/10);
  value + v*amp*Math.sin(freq*t*2*Math.PI)/Math.exp(decay*t);
}
```

**Tune:**  
- `amp` controls strength, `freq` speed, `decay` damping.  
**Example:** universal “spring-back” for sliders, panels, or limbs.

────────────────────────────────────────────────────────────────────────

### 🔧 Troubleshooting
• Nothing moves → ensure layer has keyframes or target reference.  
• Too fast → reduce `freq` or increase `decay`.  
• Motion drifts offscreen → check comp units (pixels vs 3D space).  
• For linked layers, verify target layer names match exactly.

────────────────────────────────────────────────────────────────────────

### 🧪 Practice Exercises
1. Apply *Inertia* to a logo’s Position so it drifts after stop.  
2. Create a *Floating Drift* background using slow sine motion.  
3. Add *Gravity Drop* to icons that bounce onto a floor line.  
4. Combine *Follow/Chase* + *Spring Physics* for a soft camera rig.  
5. Build a *Pendulum Swing* title and gradually increase `decay` until it rests.

────────────────────────────────────────────────────────────────────────

Next → **Controllers & Rigging**: learn to centralize multiple physics expressions under shared sliders and layer controls.

<a id="controllers-and-rigging"></a>
## 🎛️ Controllers & Rigging — Practical Motion Recipes
Centralize control of many layers, create reusable UI (**sliders, checkboxes, angles, colors, points**), and build lightweight rigs (stagger systems, look-at targets, simple 2-bone IK, state blends, and global timing). This chapter gives you repeatable patterns that scale from one layer to an entire sequence.

────────────────────────────────────────────────────────────────────────

### 🧭 Controller Philosophy
- **One place to art-direct:** a single CTRL layer drives many dependent expressions.
- **Non-destructive:** keyframe the child layers as usual; controllers *add* behavior.
- **Name discipline wins:** consistent effect names prevent broken pickwhips.

**Recommended controller layer**
- Add a **Null** named **CTRL**.
- Add the following controls (Effects > Expression Controls):
  - Slider: **Amp**, **Freq**, **Decay** (motion DNA, reused everywhere)
  - Slider: **Global Delay**, **Global Speed**
  - Checkbox: **Enable Rig**
  - Angle Control: **Aim**
  - Color Control: **Primary Color**
  - Point Control: **Target**
  
You’ll reference controls like:
```js
C = thisComp.layer("CTRL");
amp   = C.effect("Amp")("Slider");
freq  = C.effect("Freq")("Slider");
decay = C.effect("Decay")("Slider");
```

────────────────────────────────────────────────────────────────────────

### 1) Master On/Off (safety switch)
**What it does:** cleanly gates an expression so you can toggle a rig globally.

**Where:** paste on any driven property (Position/Scale/Rotation/Opacity).

```js
C = thisComp.layer("CTRL");
on = C.effect("Enable Rig")("Checkbox") > 0;
on ? value : valueAtTime(time); // same value, but no added behavior when off
```

**Tip:** Use this at the top of “spicy” expressions. Flip one checkbox to compare rigged vs. vanilla motion.

────────────────────────────────────────────────────────────────────────

### 2) Global Amplitude / Timing (central art direction)
**What it does:** lets **Amp / Freq / Decay** act as global dials across your comp.

**Where:** wrap existing bounce/elastic snippets with globals.

```js
C=thisComp.layer("CTRL");
A=C.effect("Amp")("Slider");
F=C.effect("Freq")("Slider");
D=C.effect("Decay")("Slider");

t=time - inPoint;
value + A*Math.sin(F*t*2*Math.PI)*Math.exp(-D*t);
```

**Use:** tweak three numbers to retime a whole sequence without touching child layers.

────────────────────────────────────────────────────────────────────────

### 3) Global Stagger (delay everything from one slider)
**What it does:** offset many layers by a controllable delay.

**Where:** paste on any animated property of followers.

```js
C=thisComp.layer("CTRL");
dPer = C.effect("Global Delay")("Slider")/100; // seconds per index
lag  = (thisLayer.index - 1) * dPer;
valueAtTime(time - lag);
```

**Tip:** Duplicate layers, reorder to re-sequence the wave. The slider changes flow in one move.

────────────────────────────────────────────────────────────────────────

### 4) Marker-Driven Stepper (choreograph beats from the controller)
**What it does:** uses **CTRL layer markers** as global timing cues for all children.

**Setup:** add markers on **CTRL** where hits should land.  
**Where:** paste on children’s properties.

```js
C = thisComp.layer("CTRL");
n = 0;
if (C.marker.numKeys>0){
  n = C.marker.nearestKey(time).index;
  if (C.marker.key(n).time > time) n--;
}
if (n>0){
  t=time - C.marker.key(n).time;
  // simple pop; swap your favorite hit here
  value + [0,0] + (10*Math.sin(6*t*2*Math.PI)*Math.exp(-5*t));
}else{
  value
}
```

**Use:** edit one marker track → entire comp reacts.

────────────────────────────────────────────────────────────────────────

### 5) Index-Aware Rig (smart variations with one expression)
**What it does:** gives each duplicate its own offset/scale based on **layer index** and a single controller slider.

```js
C=thisComp.layer("CTRL");
spread = C.effect("Global Delay")("Slider")/100; // seconds
seedRandom(index, true);
perLayer = (index-1) * spread;
valueAtTime(time - perLayer);
```

**Use:** cards, dots, list items—one expression scales to N layers.

────────────────────────────────────────────────────────────────────────

### 6) Look-At (2D target aiming)
**What it does:** rotate a layer to face a **Target** point on CTRL.

**Setup:** on **CTRL**, set a **Point Control** named **Target**.  
**Where:** paste on **Rotation** of the aiming layer.

```js
C=thisComp.layer("CTRL");
T=C.effect("Target")("Point");
p = toWorld(anchorPoint);
v = T - p;
radiansToDegrees(Math.atan2(v[1], v[0]));
```

**Extras:** add an **Aim** Angle Control to add/subtract an offset; clamp or damp for smoother aiming.

────────────────────────────────────────────────────────────────────────

### 7) Follow with Lag + Damping (but controllable)
**What it does:** smooth follow of a moving **Target** point with time lag and damping.

**Where:** paste on **Position** of follower.

```js
C=thisComp.layer("CTRL");
T=C.effect("Target")("Point");
lag   = 0.18; // seconds
damp  = 8;    // higher = snappier
goal  = T;
base  = valueAtTime(time - lag);
base + (goal - base)/damp;
```

**Use:** soft camera rigs, secondary elements trailing primaries.

────────────────────────────────────────────────────────────────────────

### 8) 2-Bone IK (simple 2D limb rig)
**What it does:** upper/lower bones rotate to reach a **Target** (law of cosines).  
**Setup:**
- Create 3 nulls: **Upper**, **Lower**, **Effector** (the end point to reach).
- Set **Upper** as parent of **Lower**; **Lower** parent of your hand/foot layer.
- On **CTRL**, reuse **Target** (Point Control) as the effector target.

**Paste on Upper ROTATION:**
```js
C=thisComp.layer("CTRL");
A=thisLayer;              // Upper
B=thisComp.layer("Lower");// Lower (child)
T=C.effect("Target")("Point");

a = A.toWorld(A.anchorPoint);
b = B.toWorld(B.anchorPoint);
t = T;

L1 = length(B.anchorPoint - A.anchorPoint); // approximate bone lengths in layer space
L2 = length(B.parent.transform.position);   // or set fixed numbers if preferred
d  = length(t - a);

d = clamp(d, Math.abs(L1-L2)+0.001, L1+L2-0.001); // triangle inequality

angA = Math.acos( (L1*L1 + d*d - L2*L2) / (2*L1*d) );
angAToTarget = Math.atan2((t - a)[1], (t - a)[0]);
radiansToDegrees(angAToTarget - angA);
```

**Paste on Lower ROTATION:**
```js
C=thisComp.layer("CTRL");
A=thisLayer.parent;   // Upper
B=thisLayer;          // Lower
T=C.effect("Target")("Point");

a = A.toWorld(A.anchorPoint);
b = B.toWorld(B.anchorPoint);
t = T;

L1 = length(B.anchorPoint - A.anchorPoint);
L2 = length(B.anchorPoint - B.toWorld(B.anchorPoint)); // fallback
d  = length(t - a);

d = clamp(d, Math.abs(L1-L2)+0.001, L1+L2-0.001);

angB = Math.acos( (L1*L1 + L2*L2 - d*d) / (2*L1*L2) );
- radiansToDegrees(Math.PI - angB);
```

**Notes:** AE layer spaces can vary by art; for production, measure L1/L2 once and hardcode. Add a **Pole** control (Point) to guide elbow direction if needed (by biasing angles toward pole).

────────────────────────────────────────────────────────────────────────

### 9) Slider-Driven State Blend (morph between two poses/timings)
**What it does:** blends between **State A** and **State B** using a single slider on CTRL.

**Setup:** on **CTRL**, add **Slider** named **State** (0–100).  
**Where:** paste on any numeric property you want to blend.

```js
C=thisComp.layer("CTRL");
S=C.effect("State")("Slider")/100; // 0..1

A = valueAtTime(inPoint + 0.0);  // pose/time A (can be keyframed time)
B = valueAtTime(inPoint + 0.5);  // pose/time B (or a different comp time)

linear(S, 0, 1, A, B);
```

**Use:** one slider morphs an icon from compact → expanded; or blends between two timing offsets.

────────────────────────────────────────────────────────────────────────

### 10) Global Color Rig (palette from a single control)
**What it does:** all fills/strokes pick their color from **CTRL**.

**Where:** on shape/text **Fill Color** expression.

```js
C=thisComp.layer("CTRL");
C.effect("Primary Color")("Color");
```

**Use:** recolor an entire styleframe with one click.

────────────────────────────────────────────────────────────────────────

### 11) Time-Remap Scrubber (controller as a timeline)
**What it does:** one slider scrubs a precomp’s animation.

**Setup:** precomp a clip, enable **Time-Remap** (Layer > Time > Enable Time Remapping).  
On **CTRL**, add **Slider** named **Playhead** (0–100).

**Paste on the precomp’s Time Remap:**
```js
C = thisComp.layer("CTRL");
S = C.effect("Playhead")("Slider");   // 0..100
t0 = 0; 
t1 = thisLayer.source.duration;       // full source range
linear(S, 0, 100, t0, t1);
```

**Use:** sequencer control, scrubbing a montage, quick A/B timing.

────────────────────────────────────────────────────────────────────────

### 12) Comp-Wide Speed Control (slow-mo / time-crunch)
**What it does:** multiplies time for expressions globally.

**Setup:** on **CTRL**, add **Slider** named **Global Speed** (100 = normal).

**Pattern to use inside any expression:**
```js
C=thisComp.layer("CTRL");
speed = C.effect("Global Speed")("Slider")/100; // 0.5=half-speed, 2=double
t = inPoint + (time - inPoint)*speed;
// then use t instead of time:
valueAtTime(t);
```

**Use:** quickly slow everything down for review or ramp up for previews.

────────────────────────────────────────────────────────────────────────

### 🔧 Troubleshooting
- **“Nothing changes”** → verify effect names on CTRL (case-sensitive) and target layer names (e.g., “CTRL”, “Leader”).  
- **“My rig fights keyframes”** → keep base keyframes minimal; let controllers add behavior, not replace every curve.  
- **“Angles flip”** → clamp inputs; avoid gimbal by staying in 2D for simple look-at and IK.  
- **“IK jitters”** → lock bone lengths (hardcode L1/L2), add a Pole bias, or slightly damp target motion.  
- **“Performance dips”** → reduce nested `valueAtTime` calls; centralize computations (cache CTRL variables at top).

────────────────────────────────────────────────────────────────────────

### 🧪 Practice Drills
1) Build a **Global Stagger** rig that offsets 12 cards—art-direct the wave from one slider.  
2) Create a **Look-At** pointer that tracks a CTRL Target; add a small lag/damp to avoid twitch.  
3) Rig a **State Blend** slider that morphs an icon from compact to expanded.  
4) Drive a **Time-Remap Scrubber** for a montage precomp—set “Playhead” to 0–100 for students to explore timing.  
5) Prototype a simple **2-bone IK** arm reaching for the Target; add a Pole to steer elbow direction.

────────────────────────────────────────────────────────────────────────

Next → **Color & Lighting**: build global palettes, light-linked responses, and auto-toning rigs driven from a single controller.


<a id="color-and-lighting"></a>
## 🎨 Color & Lighting — Practical Motion Recipes
This section teaches you how to build color systems and pseudo-lighting directly inside After Effects using expressions.  
You’ll link palettes to controllers, automate tonal shifts, drive gradients from motion, and simulate environmental light sweeps—all fully procedural and keyframe-free.

────────────────────────────────────────────────────────────────────────

### 🧭 Color Philosophy
- **Centralize color.** One “Master Color” drives every layer for effortless recoloring.
- **Use hue, brightness, and contrast as story tools, not decorations.**
- **Lighting in 2D ≠ real physics.** We mimic falloff, directionality, and reflection through gradients, blurs, and math.

Recommended setup:
- Create a Null named **CTRL**.
- Add the following Expression Controls:
  - Color Control → **Master Color**
  - Slider → **Light Intensity**
  - Slider → **Shadow Depth**
  - Angle Control → **Light Angle**
  - Checkbox → **Dynamic Lighting**

────────────────────────────────────────────────────────────────────────

### 1) Global Palette Control
**What it does:** applies one color palette across multiple elements.

**Where:** Shape Fill Color or Text Fill Color.

```js
C = thisComp.layer("CTRL");
C.effect("Master Color")("Color");
```

**Usage tip:** duplicate CTRL and recolor for alternative schemes (day/night, brand A/brand B).

────────────────────────────────────────────────────────────────────────

### 2) Light-Intensity → Brightness Mapping
**What it does:** converts a slider value (0–100) into brightness variations across layers.

**Where:** Shape Fill Color, set base color as value; add this expression.

```js
C = thisComp.layer("CTRL");
base = value; 
intensity = C.effect("Light Intensity")("Slider")/100;
base + [intensity*0.2, intensity*0.2, intensity*0.2, 0];
```

**Tune:** increase the 0.2 multipliers for stronger brightness reaction.  
**Example:** global “fade to daylight” when intensity ramps.

────────────────────────────────────────────────────────────────────────

### 3) Directional Lighting (Angle-Based Highlight)
**What it does:** simulates light direction by altering brightness based on the layer’s position relative to a virtual angle.

**Where:** Shape Fill Color.

```js
C = thisComp.layer("CTRL");
ang = degreesToRadians(C.effect("Light Angle")("Angle"));
lightVec = [Math.cos(ang), Math.sin(ang)];
pos = toWorld(anchorPoint);
rel = normalize(pos - thisComp.width/2);
dot = clamp(dot(rel, lightVec), -1, 1);
brightness = linear(dot, -1, 1, 0.6, 1.4);
value*brightness;
```

**Tune:** adjust 0.6–1.4 range for contrast strength.  
**Example:** pseudo-sunlight sweep across icons.

────────────────────────────────────────────────────────────────────────

### 4) Shadow Depth → Opacity Falloff
**What it does:** darkens objects based on distance from a virtual light source.

**Where:** Shape Layer Opacity.

```js
C=thisComp.layer("CTRL");
depth = C.effect("Shadow Depth")("Slider");
src = thisComp.layer("CTRL").toWorld([0,0,0]);
pos = toWorld(anchorPoint);
dist = length(pos - src);
linear(dist, 0, 600, 100, 100 - depth);
```

**Example:** as objects move away from the “light source,” they dim.

────────────────────────────────────────────────────────────────────────

### 5) Motion-Linked Color Shift
**What it does:** shifts hue based on speed—adds energy to fast motion.

**Where:** Shape Fill Color.

```js
spd = length(velocity);
hsl = rgbToHsl(value);
hsl[0] += spd/1000;          // hue shift
hsl[1] = clamp(hsl[1],0,1);  // keep saturation safe
hsl[2] = clamp(hsl[2],0,1);  // keep brightness safe
hslToRgb(hsl);
```

**Tune:** smaller divisor (e.g., 800) = stronger hue change.  
**Example:** streaks that tint warmer when accelerating.

────────────────────────────────────────────────────────────────────────

### 6) Auto Gradient Lighting (per-object two-tone)
**What it does:** creates an automatic gradient from top-to-bottom brightness or depth.

**Where:** Gradient Fill’s Start Color or End Color.

```js
C = thisComp.layer("CTRL");
intensity = C.effect("Light Intensity")("Slider")/100;
dir = normalize([0, -1]); // light from above
p = toWorld(anchorPoint);
val = linear(p[1], 0, thisComp.height, 1.2, 0.8);
value * val * (1 + intensity*0.5);
```

**Example:** UI panels with self-shading; pseudo-3D cylinders.

────────────────────────────────────────────────────────────────────────

### 7) Flicker Light Pulse
**What it does:** generates organic flicker using random noise.

**Where:** Opacity, Exposure, or Color Brightness.

```js
freq = 5; amp = 15;
seedRandom(index + time*10, true);
value + (random(-amp, amp) * Math.sin(time*freq));
```

**Tip:** link `freq` and `amp` to CTRL sliders for art-directed chaos.  
**Example:** neon signage, projector jitter, candlelight.

────────────────────────────────────────────────────────────────────────

### 8) Global Warm/Cool Tint Blend
**What it does:** lets a single slider fade the scene from cool (blue) to warm (orange).

**Where:** Adjustment Layer > Tint Effect > Map White To.

```js
C = thisComp.layer("CTRL");
S = C.effect("WarmCool")("Slider")/100;
cool = [0.3,0.6,1];
warm = [1,0.7,0.4];
linear(S,0,1,cool,warm);
```

**Add a “WarmCool” Slider** (0=cool, 100=warm) to CTRL.  
**Example:** dynamic time-of-day shifts.

────────────────────────────────────────────────────────────────────────

### 9) Auto Color Balance on Exposure Change
**What it does:** keeps colors vibrant when global exposure changes.

**Where:** Adjustment Layer > Exposure Effect > Exposure Expression.

```js
C=thisComp.layer("CTRL");
exp = C.effect("Light Intensity")("Slider")/100;
exp*1.5 - 0.5; // scale and bias
```

Then on the Tint or Curves layer:
```js
C=thisComp.layer("CTRL");
exp = C.effect("Light Intensity")("Slider")/100;
linear(exp,0,1,1.0,1.2);
```

**Result:** bright scenes stay colorful; dim scenes avoid crush.

────────────────────────────────────────────────────────────────────────

### 10) Procedural Rim Light Simulation
**What it does:** fakes rim-light edge glow based on angle to light source.

**Where:** Opacity of a duplicate layer set to “Add” blend mode.

```js
C=thisComp.layer("CTRL");
ang = degreesToRadians(C.effect("Light Angle")("Angle"));
lightVec = [Math.cos(ang), Math.sin(ang)];
n = normalize(toWorldVec([0,1,0]));
rim = clamp(dot(n, lightVec), 0, 1);
linear(rim,0,1,0,100);
```

**Example:** glowing edges reacting to virtual sunlight angle.

────────────────────────────────────────────────────────────────────────

### 11) Motion Blur Compensation for Light Flicker
**What it does:** ties light intensity to comp’s shutter angle for cinematic flicker.

**Where:** Exposure or Glow Intensity.

```js
shutter = thisComp.frameDuration * thisComp.frameRate;
amp = shutter*120; // adjust scaling
value * (1 + Math.sin(time*amp)*0.05);
```

**Use:** subtle pulse matching motion-blur rhythm.

────────────────────────────────────────────────────────────────────────

### 12) Color Loop for Abstract Backgrounds
**What it does:** cycles hue endlessly—useful for animated gradients.

**Where:** Solid Layer > Fill Color.

```js
speed = 0.1; // cycles per second
hsl = rgbToHsl(value);
hsl[0] += time*speed;
hslToRgb(hsl);
```

**Example:** looping pastel fields, ambient mood lighting.

────────────────────────────────────────────────────────────────────────

### 🔧 Troubleshooting
- **Colors oversaturate:** clamp hue/brightness after conversion.  
- **Nothing changes:** verify effect names on CTRL match exactly.  
- **Flicker too strong:** lower amplitude or apply smooth() to time.  
- **Performance:** group related expressions on an Adjustment Layer and reference its result with sampleImage() for efficiency.

────────────────────────────────────────────────────────────────────────

### 🧪 Practice Exercises
1. Build a **Master Color** rig controlling 10 layers; test instant recoloring.  
2. Add a **Light Angle** sweep animating across a logo.  
3. Create a **Warm/Cool** slider for “sunset → night” transition.  
4. Link **Motion Hue Shift** to a bouncing icon; observe live color energy.  
5. Combine **Flicker Pulse** + **Directional Light** for vintage film glow.

────────────────────────────────────────────────────────────────────────

Next → **Environmental FX & Camera Systems:** integrate fog, depth haze, and parallax light reactions for cinematic realism.


<a id="environmental-fx-and-camera-systems"></a>
## 🌫️ Environmental FX & Camera Systems — Practical Motion Recipes
This chapter focuses on *cinematic space*: haze, fog, depth, light rays, and practical camera rigs. You’ll build depth-aware looks, parallax that sells scale, and camera behaviors (handheld, orbit, dolly, rack focus) that feel like a real shoot.

────────────────────────────────────────────────────────────────────────

### 🧭 Concepts You’ll Use
- **Depth ≠ 3D only.** In 2.5D comps you can fake depth from distance-to-camera, layer order, or a custom grayscale “depth map.”
- **Atmosphere sells scale.** Minimal haze + parallax beats heavy VFX for most UI/graphics shots.
- **Camera first, FX second.** Rig motion you love → then make FX react to it (distance, angle, speed).

**Controller suggestion (on CTRL):**
- Sliders: **Haze Amount**, **Ray Intensity**, **Shake Amount**, **Dolly Speed**
- Angle: **Light Angle**
- Color: **Fog Color**
- Checkbox: **Enable Handheld**
- Point: **Focus Target**

You’ll reference controls like:
```js
C=thisComp.layer("CTRL");
haze=C.effect("Haze Amount")("Slider");
ray =C.effect("Ray Intensity")("Slider");
shake=C.effect("Shake Amount")("Slider");
```

────────────────────────────────────────────────────────────────────────

## 1) Depth Haze / Fog (2.5D friendly)
**What it does**  
Adds atmospheric perspective so distant layers fade toward a fog color.

**Where**  
On an **Adjustment Layer** above your scene → apply *Fill* (or *Tint*) and *Exposure/Curves*. Paste on **Opacity**:

```js
C = thisComp.layer("CTRL");
fog = C.effect("Haze Amount")("Slider"); // 0..100
// assume 2.5D: use camera distance for depth
cam = thisComp.activeCamera.toWorld([0,0,0]);
p   = thisLayer.sampleImage(thisLayer.fromComp(cam), [thisComp.width,thisComp.height]); // placeholder sample; opacity uses a base ramp instead:
linear(0,0,1,0,1); // (kept for structure)
```

**Better: per-layer version (on each layer’s Opacity)**  
Fade each layer by its distance to camera; use an Adjustment Layer with *Fill* set to your **Fog Color** above all layers.

```js
C=thisComp.layer("CTRL");
fog = C.effect("Haze Amount")("Slider"); // 0..100
cam = thisComp.activeCamera;
camPos = cam.toWorld([0,0,0]);
d = length(toWorld(anchorPoint) - camPos);   // pixel distance
near = 200; far = 3000;                      // tune to your scene scale
fogPct = linear(d, near, far, 0, 100);
clamp(fogPct * (fog/100), 0, 100);
```

**Tune**  
- Increase **far** for larger scenes; adjust **near** so close objects stay crisp.  
**Example**  
3 layered skylines: front text reads crisp, far buildings melt into fog.

────────────────────────────────────────────────────────────────────────

## 2) Parallax by Camera (2.5D stacks)
**What it does**  
Simple, robust 2.5D parallax: background moves less than foreground as camera moves.

**Where**  
Use **3D layers**; different Z positions; animate/dolly the **Camera Position**. To auto-offset background layers relative to a “base plate”:

```js
// On BG layer Position: follow camera with reduced factor
cam   = thisComp.activeCamera;
factor= 0.2; // 0=no follow (static), 1=sticks to camera; small values = big parallax
world = toWorld(anchorPoint);
camPan= cam.toWorld([0,0,0]) - cam.position; // camera translation proxy
value + (camPan * factor);
```

**Tip**  
Manually place layers at different Z values for stronger depth.

────────────────────────────────────────────────────────────────────────

## 3) Volumetric Light Rays (fake, fast)
**What it does**  
Creates directional “God rays” that react to camera/angle.

**Where**  
Duplicate your bright element (text/logo), blur it heavily, set to **Add** blend mode. On duplicate **Opacity**:

```js
C=thisComp.layer("CTRL");
ang = degreesToRadians(C.effect("Light Angle")("Angle"));
ray = C.effect("Ray Intensity")("Slider");
dir = [Math.cos(ang), Math.sin(ang)];
// intensity grows with alignment to direction (cheap dot trick)
n = normalize(toWorldVec([0,-1,0]));
align = clamp(dot(n, dir), 0, 1);
linear(align, 0, 1, 0, ray);
```

**Tip**  
Stack with *Radial Blur (Zoom)* centered off-screen along the light angle.

────────────────────────────────────────────────────────────────────────

## 4) Camera Orbit Rig (clean, predictable)
**What it does**  
Orbits a camera around a subject at a fixed radius with easy art direction.

**Where**  
On **Camera Position** (leave Point of Interest at the subject or use a target Null).

```js
C=thisComp.layer("CTRL");
speed=C.effect("Dolly Speed")("Slider")/100; // rotations/sec
radius=1200;
center=thisComp.layer("Subject").toWorld([0,0,0]);
ang = time*speed*2*Math.PI;
[x, y, z] = [Math.cos(ang)*radius, -200, Math.sin(ang)*radius];
center + [x,y,z];
```

**Tip**  
Animate **radius** for dynamic orbit in/out; keyframe **y** for subtle boom.

────────────────────────────────────────────────────────────────────────

## 5) Handheld / Micro-Jitter (tasteful)
**What it does**  
Adds organic micro-movement to camera without seasickness.

**Where**  
On **Camera Position** (or a parent Null). Keep small.

```js
C=thisComp.layer("CTRL");
on = C.effect("Enable Handheld")("Checkbox")>0;
amt = C.effect("Shake Amount")("Slider"); // 0..100
seedRandom(0,true);
freq1=0.8; freq2=1.3;
x = amt*0.6*Math.sin(time*freq1*2*Math.PI);
y = amt*0.4*Math.sin((time+0.37)*freq2*2*Math.PI);
z = amt*0.3*Math.sin((time+0.71)*0.5*2*Math.PI);
value + (on ? [x,y,z] : [0,0,0]);
```

**Tip**  
Less is more. 2–8 px is enough for UI/product; more for gritty handheld.

────────────────────────────────────────────────────────────────────────

## 6) Speed-Reactive Motion Blur / Exposure
**What it does**  
Brightens or blurs slightly when camera moves quickly.

**Where**  
Adjustment Layer → *Exposure* (or Glow) → **Exposure** expression:

```js
cam = thisComp.activeCamera;
dt = thisComp.frameDuration;
p1 = cam.position;
p0 = cam.position.valueAtTime(time - dt);
spd = length(p1 - p0)/dt;     // px/sec
gain = clamp(spd/4000, 0, 0.35);
value + gain;
```

**Example**  
Tasteful highlight lift on fast sliders/pans.

────────────────────────────────────────────────────────────────────────

## 7) Rack Focus (target-based DOF)
**What it does**  
Automatically sets **Focus Distance** to a target Null for reliable rack focus.

**Where**  
On **Camera > Focus Distance**:

```js
target = thisComp.layer("CTRL").effect("Focus Target")("Point");
cam    = thisComp.activeCamera;
camPos = cam.toWorld([0,0,0]);
// convert target comp point to 3D ray from camera
tWorld = cam.fromCompToWorld([target[0], target[1], 0]);
length(tWorld - camPos);
```

**Tip**  
Enable DOF on camera; control **Aperture** for depth strength.

────────────────────────────────────────────────────────────────────────

## 8) Depth-Driven Fake DOF (works without camera DOF)
**What it does**  
Blurs layers based on distance to camera—fast fallback when real DOF is too heavy.

**Where**  
On each layer’s *Gaussian Blur* **Blurriness**:

```js
camPos = thisComp.activeCamera.toWorld([0,0,0]);
d = length(toWorld(anchorPoint) - camPos);
near= 300; far= 2500; maxBlur = 24;
amt = linear(d, near, far, 0, maxBlur);
clamp(amt, 0, maxBlur);
```

**Tip**  
Blur backgrounds more; keep hero layers with lower maxBlur.

────────────────────────────────────────────────────────────────────────

## 9) Light Sweep / Sheen (angle + time)
**What it does**  
Adds a moving highlight band across text/logos based on light angle.

**Where**  
Use a duplicate set to **Add** with a feathered mask. On **Opacity**:

```js
C=thisComp.layer("CTRL");
ang = degreesToRadians(C.effect("Light Angle")("Angle"));
dir = [Math.cos(ang), Math.sin(ang)];
// project world position onto light direction
p = toWorld(anchorPoint);
t = (p[0]*dir[0] + p[1]*dir[1]) / 1000 + time*0.3; // scale + time sweep
band = 1 - Math.abs(fract(t)*2 - 1); // 0..1 triangle wave
linear(band, 0.6, 1, 0, 100);
```

**Tune**  
Increase the slope of `band` mapping for tighter sweeps.

────────────────────────────────────────────────────────────────────────

## 10) Distance-Aware Particles (fog dust / motes)
**What it does**  
Makes particles more/less visible based on camera distance for believable depth.

**Where**  
On particle layer **Opacity**:

```js
camPos = thisComp.activeCamera.toWorld([0,0,0]);
d = length(toWorld(anchorPoint) - camPos);
near=200; far=2400;
linear(d, near, far, 100, 10); // nearer = denser
```

**Tip**  
Use CC Particle World/Particular for emission; keep sizes tiny, speeds low.

────────────────────────────────────────────────────────────────────────

## 11) Auto-Parallax for 2D UI (no 3D required)
**What it does**  
Creates parallax drift linked to mouse/target in 2D comps (promo sites, dashboards).

**Where**  
On a group’s **Position**:

```js
C=thisComp.layer("CTRL");
T=C.effect("Focus Target")("Point"); // repurpose as “parallax target”
strength = 0.08;
center = [thisComp.width/2, thisComp.height/2];
offset = (T - center) * strength;
value + [offset[0], offset[1]];
```

**Use**  
Move the target to “parallax” the UI stack subtly for depth.

────────────────────────────────────────────────────────────────────────

## 12) Cinematic Framing Overlay (guides, not FX)
**What it does**  
Draws safe area / aspect bars driven by one slider.

**Where**  
On a dedicated shape overlay layer’s **Opacity**:

```js
C=thisComp.layer("CTRL");
bars = C.effect("Cinematic Bars")("Slider"); // 0..100
bars; // simply show/hide; animate slider to on/off
```

Add a **Rectangle** scaled to create letterbox bars; tie its **Size** to comp height with an expression if you want responsive bars.

────────────────────────────────────────────────────────────────────────

### 🔧 Troubleshooting
- **Parallax too strong** → lower radius or parallax factor; keep orbits shallow for UI.
- **Rays look cheesy** → keep Add/Screen duplicates subtle; stack blur + light angle.
- **DOF noisy/slow** → use Fake DOF (per-layer blur) or limit DOF to hero objects.
- **Handheld feels seasick** → lower Shake Amount and frequencies; keep Z wobble tiny.
- **Haze washes color** → tint your fog toward scene palette; apply slight contrast after haze.

────────────────────────────────────────────────────────────────────────

### 🧪 Practice Exercises
1) Build a 2.5D parallax scene (3 planes); add depth haze and a slow camera orbit.  
2) Add a Light Sweep to a logo and keyframe Light Angle to rake across it.  
3) Set up Rack Focus between two text cards using Focus Target.  
4) Create a Fake DOF pass for a dense UI scene; compare render speed vs Camera DOF.  
5) Add tasteful Handheld to a dolly pass, then modulate Exposure with camera speed.

────────────────────────────────────────────────────────────────────────

Next → **Time & Looping**: global speed controls, beats, markers, and procedural time tricks for complex sequences.
```
