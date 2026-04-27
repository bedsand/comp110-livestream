---
# Do not edit the text between these lines!
layout: default
title: "Should COMP110 Livestream Lectures?"
---

# Should COMP110 Livestream Its Lectures?

*An Analysis of the Spring 2026 course survey*

**Blake Sanders & Ethan Kramer** — COMP 110, Spring 2026, EX09
---
## Summary

This project analyzes a proposed change to COMP110: that in-person lectures should be livestreamed. Drawing on the survey responses from 764 students across all three sections, the analysis tests whether livestreaming would create real value, and who would benefit most.

The survey directly asks students to rate their support for livestreaming on a 1-to-7 Likert scale. It also captures variables we can use to find which subgroups want it most.

## Finding 1 — Overall support is strong

The distribution of `add_livestream` responses is sharply skewed to the right. The single most common answer was Strongly Agree, and roughly 3/4 of students rated their support at 5 or higher.

![Chart 1: Overall support for livestreaming](images/chart1_distribution.png)

Livestreaming's popularity is not enough on its own, though. A student who wants livestreaming is different from a student who needs it. The next two findings ask which students drive the demand.

---

## Finding 2 — Demand is broad-based, not subgroup-specific

The first hypothesis was that demand would be concentrated in particular subgroups such as transfer students or students with little prior programming experience. Neither hypothesis  held well.

Transfer and nontransfer students reported nearly identical mean support. And mean support across the five prior experience categories were in a narrow band around 5.5 to 5.8 out of 7, with no group meaningfully above or below the others.

![Chart 2: Mean support by prior experience](images/chart2_prior_exp.png)

Clearly, livestream demand isn't a niche request from one experience band.

---

## Finding 3 — Demand rises sharply with perceived difficulty

If experience doesn't drive demand, what does? The clearest pattern in the analysis comes from `difficulty`.
![Chart 3: Livestream support by difficulty](images/chart3_difficulty.png)

Mean support for livestreaming rises substantially as perceived difficulty rises, climbing from 4.88 at `difficulty=1` up to 6.37 at `difficulty=7`. The box plot shows the entire distribution shifting up as difficulty rises.

An independent check against the `understanding` variable reproduces a similar pattern: students who feel "lost" want livestreaming more than students who feel they understand the material.
---

## Conclusion

The data supports livestreaming COMP110 lectures. Support is broad yet is strongest among students reporting the most difficulty with the course. That makes this a change that creates value.

### Trade-offs to consider

1. **In-person attendance may decline,** which would erode in person engagement that the current lecture format provides.
2. **Technical and staffing overhead.** A reliable livestream requires working AV equipment, a platform, and ideally a TA monitoring chat.
3. **Signal about course norms.** Adopting livestreaming may implicitly communicate that in-person attendance is optional, which may impact attendance expectations in a large intro course.

### What's next

- **Livestream-on-demand,** available by short advance request rather than as a default, to preserve inperson attendance norms while still supporting students the data identifies.
- **Live TA-moderated chat** alongside the stream so remote viewers can participate actively rather than just receive a glorified recording.


