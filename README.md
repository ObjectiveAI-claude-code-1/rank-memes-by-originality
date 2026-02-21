# rank-memes-by-originality

A vector function that ranks a collection of memes from most original to least original by evaluating how fresh, inventive, and surprising each meme feels compared to the others in the set.

## Purpose

The internet produces an enormous volume of memes every day, and the vast majority are derivative — recycled templates, familiar punchlines, and predictable formats. This function cuts through the noise by identifying the memes that feel like genuine discoveries. It does not measure humor, popularity, or production quality. It measures one thing: originality.

Given a set of memes, the function produces a ranked ordering from most original to most derivative, enabling users to quickly surface the content that is most likely to capture attention and reward creative risk-taking.

## Input

The function accepts an array of **2 or more images**, where each image is a meme to be evaluated.

```
[image, image, image, ...]
```

Each image is a self-contained meme — a piece of internet humor or commentary in visual form. The function evaluates every meme comparatively against the others in the set to produce a relative ranking.

## Output

The function returns an array of scores, one per input meme, that together form a probability distribution (summing to approximately 1). Higher scores indicate greater originality. The scores reflect the meme's position in the ranking relative to the other memes in the input set.

```
[0.45, 0.10, 0.30, 0.15]
```

In this example, the first meme is ranked as the most original in the set, followed by the third, then the fourth, with the second meme ranked as the least original.

## What It Evaluates

The function assesses originality across three core dimensions. Each dimension captures a distinct aspect of what makes a meme feel fresh, and together they form a complete picture of originality.

### 1. Conceptual Novelty

Does the meme introduce a genuinely unfamiliar idea? This dimension evaluates the freshness of the underlying thought — the joke, observation, or point of view at the meme's core. A meme that pairs ideas nobody has thought to combine, or finds humor in an uncommented-on corner of human experience, scores high. A meme that retells a joke the internet has already seen thousands of times, no matter how cleanly it is executed, scores low.

**Ranks higher:** A meme offering a perspective or connection the viewer has never encountered before.
**Ranks lower:** A meme restating a widely known truth or recycling a punchline that has already made its rounds.

### 2. Structural Inventiveness

Does the meme do something creative with its format? This dimension evaluates how the meme is constructed — its template usage, visual layout, image choices, and relationship between text and picture. A meme that subverts a familiar template, repurposes it in an unexpected context, layers formats on top of one another, or abandons conventional meme structures entirely demonstrates structural inventiveness. A meme that fills in the blanks of a well-known template exactly the way everyone else does does not.

**Ranks higher:** A meme that breaks the norms of how memes are typically assembled — unusual image choices, unexpected pairings, subverted templates, or entirely new formats.
**Ranks lower:** A meme that uses a standard template in the standard way with no creative deviation.

### 3. Surprise

Does the meme defy the viewer's expectations? This dimension evaluates the degree to which a meme catches the viewer off guard — not just in its punchline, but across its entire setup, delivery, and arc. A meme that sets up a familiar pattern and then breaks it, delivers meaning through an unexpected mechanism, or layers irony where sincerity was assumed scores high. A meme whose outcome could have been predicted before the viewer finished looking at it scores low.

**Ranks higher:** A meme that takes the viewer somewhere they did not anticipate — a twist, an unexpected delivery mechanism, or a subverted pattern.
**Ranks lower:** A meme that follows a predictable trajectory from setup to punchline with no deviation.

## Use Cases

- **Content curation:** Surface the most original memes from a large pool of submissions to feature on accounts, feeds, or community pages where capturing attention matters.
- **Creator rewards:** Identify creators who are pushing creative boundaries rather than efficiently recycling what already works, enabling platforms to reward genuine innovation.
- **Cultural research:** Distinguish creative breakthroughs from repetition when studying the evolution of internet humor and meme culture over time.
- **Feed ranking:** Prioritize original content in algorithmic feeds to increase engagement and reduce the fatigue caused by derivative, repetitive memes.

## How It Works

The function uses three vector completion tasks, each targeting one of the three evaluation dimensions. Each task presents the input memes as candidate responses to a prompt designed to elicit preference for that specific quality. The tasks use varied conversational structures — a direct request, a multi-turn rejection of formulaic content, and an expert persona evaluation — to capture each dimension from a different angle. The resulting scores across all three tasks are combined to produce the final ranking.