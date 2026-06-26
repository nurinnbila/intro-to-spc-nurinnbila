---
title-slide: false
bibliography: references.bib
csl: vancouver.csl
citeproc: true
theme: serif
background-color: "#ffffff"
transition: slide
navigationMode: linear
hash: true
---

:::: {.columns}
::: {.column width="50%"}

## Sample slides
#### PlaceHolderName
#### Universiti Malaysia Perlis
#### [placeholder@email.com](mailto:placeholder@email.com)

<audio id="bg-music" src="media/audio/sb.m4a" loop></audio>

<div id="audio-credit"
     style="position: absolute; bottom: 40px; right: 20px; font-size: 0.6em; opacity: 0.6;">
  Music: “Adrift” by Scott Buckley (CC BY 4.0)
</div>

<script>
  document.addEventListener('DOMContentLoaded', () => {
    const audio = document.getElementById('bg-music');
    const credit = document.getElementById('audio-credit');

    // hide credit by default
    credit.style.display = 'none';

    const test = new Audio('media/audio/bgm.mp3');

    test.addEventListener('canplaythrough', () => {
      // bgm.mp3 exists → use it, keep credit hidden
      audio.src = 'media/audio/bgm.mp3';
    }, { once: true });

    test.addEventListener('error', () => {
      // bgm.mp3 missing → sb.m4a will play → show credit
      credit.style.display = 'block';
    }, { once: true });

    document.addEventListener('click', () => {
      if (Reveal.getIndices().h === 0) {
        audio.volume = 0.5;
        audio.play();
      }
    }, { once: true });

    Reveal.on('slidechanged', (event) => {
      if (event.indexh > 0) { audio.pause(); }
      else { audio.play(); }
    });
  });
</script>


:::

::: {.column width="50%"}
![](media/pics/logo1.png)
:::

::::

---

:::: {.columns}
::: {.column width="50%"}
### Slide one
**Key Concepts:**
- Energy conservation per @carnot1824.
- $\Delta U = Q - W$
:::

::: {.column width="50%"}
![](media/pics/sample.png)
:::
::::

---

<span class="slide-title" data-title="My Hidden Slide Name"></span>

![](media/pics/wide.jpeg)

---

:::: {.columns}
::: {.column width="50%"}
### The Master Equation
The fundamental relation of thermodynamics:

$$\Delta U = Q - W$$

The work done $W$ is positive when the system expands against an external pressure.
:::

::: {.column width="50%"}
<video data-src="media/videos/sample.mp4" data-autoplay loop muted width="100%"></video>
:::

::::

---

:::: {.columns}
::: {.column width="50%"}
### Visualizing the Gas Law
**Interactive Model:**

- P, V, and T relationships.
- Use the slider to adjust pressure.
- Observe the phase boundary.
:::

::: {.column width="50%"}
<iframe 
  data-src="media/plots/sample.html" 
  width="100%" 
  height="500px" 
  style="border:none;" 
  scrolling="no">
</iframe>
:::
::::

---

:::: {.columns}
::: {.column width="50%"}
### Math Scores by Sex
We performed an independent samples t-test to compare the mean Math scores between male and female students. This analysis helps determine if there is a statistically significant difference in academic performance (specifically in Math) based on gender in our sample.

**T-test Results:**


::: {.column width="50%"}
<iframe data-src='media/plots/math_scores_boxplot.html' width='100%' height='500px' style='border:none;'></iframe>
:::

::::

---

:::: {.columns}
::: {.column width="50%"}
### Part Length by Machine
We conducted an independent samples t-test to assess if there is a significant difference in `PartLength` between Machine 1 and Machine 2, under controlled conditions of `Pressure` at 100 and `Temperature` at 303. The boxplot visually compares the distribution of `PartLength` for each machine.

**T-test Results:**


:::

::: {.column width="50%"}
<iframe data-src='media/plots/partlength_by_machine_boxplot.html' width='100%' height='500px' style='border:none;'></iframe>
:::

::::

---

:::: {.columns}
::: {.column width="50%"}
### PartResistance by Pressure for Machine 1
This boxplot illustrates the distribution of `PartResistance` across different `Pressure` levels specifically for `Machine 1`. This visualization helps to identify how varying pressure conditions affect the part resistance produced by this particular machine.

**Key Observations:**
- We can observe the median, spread, and potential outliers of `PartResistance` at each pressure setting.
- The plot helps in understanding the central tendency and variability of `PartResistance` as `Pressure` changes.
:::

::: {.column width="50%"}
<iframe data-src='media/plots/partresistance_by_pressure_machine1_boxplot.html' width='100%' height='500px' style='border:none;'></iframe>
:::

::::

---

:::: {.columns}
::: {.column width="50%"}
### ANOVA for PartResistance by Pressure (Machine 1)
We performed an ANOVA to investigate the effect of `Pressure` on `PartResistance` specifically for `Machine 1`. The ANOVA tests if there are statistically significant differences between the means of `PartResistance` across the different `Pressure` levels.

**ANOVA Results:**

- **Pr(>F) for Pressure_Factor**: 9.175118521470793e-63

Given the extremely low p-value (Pr(>F)), we can conclude that there is a highly significant effect of Pressure on PartResistance for Machine 1.
:::

::: {.column width="50%"}
<!-- Optionally, you can include the R code for the ANOVA here or a summary table if needed -->
```R
# R code for ANOVA
library(stats)

# Assuming x025_machine1 and Pressure_Factor are defined
anova_result <- aov(PartResistance ~ Pressure_Factor, data = x025_machine1)
summary(anova_result)
```
:::

::::

---

:::: {.columns}
::: {.column width="50%"}
### ANOVA for PartResistance by Pressure * Temperature (Machine 1)
We performed an ANOVA to investigate the interactive effect of `Pressure` and `Temperature` on `PartResistance` specifically for `Machine 1`. This ANOVA tests if the effect of one factor (e.g., Pressure) on `PartResistance` depends on the level of the other factor (Temperature).

**ANOVA Results:**

- **Pr(>F) for Pressure_Factor:Temperature_Factor interaction**: 0.5890634081802586

This low p-value suggests a significant interaction effect between Pressure and Temperature on PartResistance for Machine 1, meaning their combined effect is not simply additive.

### PartResistance by Pressure:Temperature Interaction (Machine 1)
This boxplot illustrates the distribution of `PartResistance` across various combinations of `Pressure` and `Temperature` for `Machine 1`. Visualizing the interaction helps to understand how different environmental conditions jointly influence the part resistance.

**Key Observations:**
- Each boxplot represents a unique combination of Pressure and Temperature.
- This plot allows us to identify specific Pressure-Temperature pairs that might lead to optimal or problematic PartResistance values.
:::

::: {.column width="50%"}
<iframe data-src='media/plots/partresistance_by_pt_interact_machine1_boxplot.html' width='100%' height='500px' style='border:none;'></iframe>
:::

::::
---
# Bibliography
<div id="refs"></div>
