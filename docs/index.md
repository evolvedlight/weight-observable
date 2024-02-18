---
toc: false
---

<style>

.hero {
  display: flex;
  flex-direction: column;
  align-items: center;
  font-family: var(--sans-serif);
  margin: 4rem 0 8rem;
  text-wrap: balance;
  text-align: center;
}

.hero h1 {
  margin: 2rem 0;
  max-width: none;
  font-size: 14vw;
  font-weight: 900;
  line-height: 1;
  background: linear-gradient(30deg, var(--theme-foreground-focus), currentColor);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.hero h2 {
  margin: 0;
  max-width: 34em;
  font-size: 20px;
  font-style: initial;
  font-weight: 500;
  line-height: 1.5;
  color: var(--theme-foreground-muted);
}

@media (min-width: 640px) {
  .hero h1 {
    font-size: 90px;
  }
}

</style>

<div class="hero">
  <h1>Goodbye, excess weight</h1>
  <h2>Tracking a single person's weight loss</h2>
  <a href="https://brown.bg" target="_blank">back to the blog<span style="display: inline-block; margin-left: 0.25rem;">↗︎</span></a>
</div>

```js
const weights = await FileAttachment("./data/weight.csv").csv({typed: true});
```

<div class="grid grid-cols-1" style="grid-auto-rows: 504px;">
  <div class="card">${
    resize((width) => Plot.plot({
      title: "How big is Steve, anyway? 🐧",
      width,
      grid: true,
      x: {label: "Date"},
      y: {label: "Body mass (kg)"},
      marks: [
        Plot.dot(weights, {y: "weight", x: "date", stroke: "green", tip: true})
      ],
      y: {domain: [80, 88]}
    }))
  }</div>
</div>