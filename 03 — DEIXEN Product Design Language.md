# DEIXEN — Product Design Language

**Status:** Exploration framework. No final palette, accent color, typography, component library, or screen composition is approved here.

## 1. Purpose

Create a recognizable, modern, coherent visual and interactive language that can support DEIXEN's growing product complexity without becoming generic, cluttered, or difficult to use.

The design language must express the product's professional purpose and support real learning tasks. It is not decoration layered over an unrelated interface.

## 2. Reference directions

The user has identified three references for different qualities:

### Microsoft
Study:
- information organization and visual hierarchy;
- composition and distribution of content;
- clarity across products with many functions;
- consistency without making every screen identical.

### Samsung
Study:
- contemporary visual sophistication;
- depth, layers, and material treatment;
- careful details and transitions;
- motion and interaction feedback;
- usability without making the product feel simplistic.

### Higgsfield
Study:
- distinctive visual presence;
- strong presentation of tools and content;
- memorable use of an accent color;
- clear personality across a feature-rich product.

These are reference sources, not templates. Do not reproduce their layouts, components, exact colors, or brand assets.

## 3. Desired qualities

- Modern and forward-looking.
- Visually rich but organized.
- Distinctive rather than template-driven.
- Strong typography and deliberate content presentation.
- Thoughtful depth, layering, motion, and interaction.
- Able to support many sections and detailed scenarios.
- Clear enough for beginners and precise enough for operational work.
- Coherent across all five areas while allowing different compositions for different tasks.

## 4. Color and themes

- Dark and Light themes are both required design considerations.
- The accent color is **open**.
- Higgsfield's fluorescent accent is an example of a recognizable accent strategy, not a DEIXEN color decision.
- Do not assume fluorescent green, blue/cyan, red, or any other color is selected.
- Functional colors for error, warning, and success must remain semantically clear and must not be confused with brand accent use.
- Test contrast, hierarchy, readability, and visual balance in both themes.

## 5. Typography

Typography is a core part of the product's character, not a finishing detail. Explore type choices and hierarchy for:
- navigation and section titles;
- instructional content and long-form reading;
- dense operational information;
- command-entry and system-output areas;
- scenario descriptions and customer dialogue;
- evidence summaries and reports.

Preserve the Terminal's established LTR/monospace operational-record constraints where governed. Do not force one type treatment onto every content type.

## 6. Composition and content presentation

Avoid defaulting to generic dashboard grids, piles of cards, or document-like pages. Choose layout according to the user's task and the information relationship.

Study:
- meaningful grouping and spacing;
- strong hierarchy between primary and secondary information;
- content-rich layouts that remain scannable;
- distinct but related treatment of tools, learning content, scenarios, and evidence;
- responsive behavior and realistic content density.

## 7. Motion and interaction

Motion should communicate state, hierarchy, continuity, or feedback. It must not be decorative noise. Define consistent behavior for transitions, expansion, loading, success, error, focus, and reduced-motion preferences.

## 8. Coherence without uniformity

Shared foundations may include typography, spacing logic, color semantics, component behavior, interaction feedback, and accessibility. Individual areas can have different visual structures when their responsibilities differ.

## 9. Reference analysis method

For every reference, record:
1. What exact quality is attractive?
2. What user or product problem does it solve?
3. What principle can transfer to DEIXEN?
4. What should not be copied?
5. Where might the principle fail in DEIXEN?
6. How can it be tested in a real workflow?

## 10. Quality gates

Reject work that:
- looks like a generic AI-generated SaaS template;
- relies on glow, gradients, metallic effects, or dark backgrounds to fake sophistication;
- uses arbitrary geometry or decorative detail without purpose;
- has weak typography or inconsistent spacing;
- looks good only in a static mockup;
- fails with realistic content density;
- makes operational work harder;
- treats Dark Theme as the only finished experience.

## 11. Open decisions

Accent color, typefaces, exact spacing scale, component shapes, surface treatments, navigation composition, motion system, and final Dark/Light palettes remain open pending exploration and testing.


## 11. Architecture-informed presentation

The unified architecture proposes one connected task context with distinct responsibilities. The visual language should make those responsibilities legible without forcing them into one dashboard or identical panel layout.

Where relevant, the product may need to distinguish:

- case context and task objective;
- customer dialogue and disclosed facts;
- Terminal operational input and system output;
- Coach explanation and instructional hints;
- task phase/checkpoints;
- debrief and evidence interpretation.

These are semantic roles, not a fixed screen composition. Explore how hierarchy, spatial grouping, typography, density, and progressive reveal make their relationships clear. The correct solution may change between mobile and desktop and between learning, practice, scenario, and assessment states.

**Functional integration is not screen merger.** A cohesive experience can use separate workspaces or focused transitions while sharing context and a consistent design language.

## 12. Distinct information, distinct visual signals

The design language should provide unambiguous, consistent treatment for:

- customer statements versus system facts;
- operational output versus learner-entered commands;
- Coach narration versus case instructions;
- practice feedback versus independent-assessment state;
- recorded evidence versus derived learner-facing interpretation.

Do not rely on color alone to encode these distinctions. Use labels, placement, typography, interaction behavior, and accessible state cues. Do not introduce a new accent color or visual identity decision through this architecture work.

The Terminal operational record's LTR/monospace and content-purity constraints remain functional invariants, not optional styling preferences.

## 13. Architecture and visual-design boundary

This document translates the architecture into design questions only. It does not approve a persistent split-pane layout, a customer chat widget, a new navigation pattern, a component library, a color system, or any specific motion behavior. Those choices belong in task-specific prototypes and validated specifications.
