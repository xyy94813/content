---
title: Ink overflow
slug: Glossary/Ink_overflow
page-type: glossary-definition
sidebar: glossarysidebar
---

The **ink overflow** of a box refers to the part of the box and its contents that creates a visual effect outside of the box's border box. Being visual only, ink overflow does not affect layout as it has no impact on box model properties.

Ink overflow is the overflow of painting effects such as [box shadows](/en-US/docs/Web/CSS/box-shadow), [border images](/en-US/docs/Web/CSS/CSS_backgrounds_and_borders), [text decoration](/en-US/docs/Web/CSS/CSS_text_decoration), [outlines](/en-US/docs/Web/CSS/outline), etc. that do not affect layout or otherwise extend the scrollable overflow area. Ink overflow is also the overhanging of glyphs, such as ascenders and descenders extending outside the em box.

As {{ glossary("replaced elements")}} always establish an independent [formatting context](/en-US/docs/Web/CSS/CSS_display/Introduction_to_formatting_contexts), any overflow of replaced content is always ink overflow (as opposed to [scrollable overflow](/en-US/docs/Learn_web_development/Core/Styling_basics/Overflow)).

## See also

- [CSS overflow module](/en-US/docs/Web/CSS/CSS_overflow)
