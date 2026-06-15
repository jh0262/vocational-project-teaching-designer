---
name: vocational-project-teaching-designer
description: Convert traditional course content for vocational or undergraduate teaching into project-based teaching designs. Use when the user provides a learner level such as 中职, 高职, or 本科 and asks to transform teaching content into projects, task decomposition, task-skill and task-knowledge matrices, key knowledge explanations, Image2-generated skill and knowledge mind map images, Remotion teaching animations, assessment rubrics, or a light-theme interactive teaching process webpage.
---

# Vocational Project Teaching Designer

## Purpose

Turn traditional subject-centered teaching content into a project-based teaching package for 中职, 高职, or 本科 learners, then generate an ordered interactive teaching process webpage.

## Required Input

Ask for missing essentials before designing:

- Learner level: 中职, 高职, or 本科.
- Traditional teaching content: textbook chapter, course unit, knowledge topic, practical module, or pasted syllabus text.
- Optional constraints: class hours, major, available equipment/software, assessment style, local industry context.

If optional constraints are absent, state reasonable assumptions briefly and continue.

## Installation And Capability Check

Before producing the final webpage, check that these capabilities are installed or enabled:

- Image2 or an equivalent image generation capability for producing the skill mind map and knowledge mind map as image files.
- Remotion plugin for producing teaching reference animations as video or embeddable animation assets.

If either capability is unavailable, stop before final asset generation and ask the user to install or enable it. Continue with text-only planning only when the user explicitly accepts a temporary fallback.

## Workflow

### 1. Convert Content Into Candidate Projects

Use the learner level and traditional content to propose 3-5 candidate projects.

For each project, include:

- Project title.
- Real work or life scenario.
- Final product or service outcome.
- Covered traditional content.
- Difficulty fit for the learner level.
- Required conditions or resources.
- Recommendation reason.

Stop and ask the user to choose one project or request revisions. Do not continue to task decomposition until the user confirms.

### 2. Decompose The Confirmed Project Into Tasks

Break the confirmed project into 4-8 teachable tasks ordered by work process.

For each task, include:

- Task name.
- Task goal.
- Student output.
- Teacher activity.
- Student activity.
- Suggested class hours.
- Task dependency.

Ask the user whether the decomposition is reasonable. If the user requests changes, revise and ask again. Continue only after confirmation.

### 3. Build The Task-Skill Matrix

For each task, identify required skills from observable work performance.

Generate a project task-skill matrix with columns:

- Task.
- Core skill.
- Sub-skills.
- Operation steps.
- Tools/equipment/software.
- Expected performance evidence.
- Common mistakes.
- Remediation strategy.

Prefer verbs that describe observable ability: identify, select, calculate, connect, debug, measure, compare, explain, document, present, optimize.

### 4. Build The Task-Knowledge Matrix And Key Explanations

Analyze the knowledge needed to support each skill.

Generate:

- Task-knowledge matrix with task, supporting knowledge, key knowledge, difficult knowledge, application point, evidence of understanding.
- Key knowledge explanations for all marked key or difficult knowledge points.

For each key explanation, include:

- Plain-language meaning.
- Why students need it for the task.
- Typical misconception.
- Concrete example.
- Teacher question prompts.
- Quick formative check.

### 5. Generate The Skill Mind Map Image

Use Image2 to generate a polished project skill mind map image. Do not leave the final webpage with only Mermaid or plain-text mind map code.

Before calling Image2, prepare a concise image prompt containing:

- Center node: project title.
- Main branches: task sequence, core skills, sub-skills, tools/equipment/software, performance evidence.
- Visual style: light background, professional teaching style, clear Chinese labels, readable hierarchy.
- Output target: local image file suitable for insertion into the webpage.

Also keep a text fallback outline for accessibility and review.

Insert the generated image into the final webpage with `alt` text and a text fallback.

### 6. Generate The Knowledge Mind Map Image

Use Image2 to generate a polished project knowledge mind map image. Do not leave the final webpage with only Mermaid or plain-text mind map code.

Before calling Image2, prepare a concise image prompt containing:

- Center node: project title.
- Main branches: foundational knowledge, task-specific knowledge, key knowledge, difficult knowledge, knowledge-to-skill transfer points.
- Marker rule: key knowledge marked with `★`; difficult knowledge marked with `▲`.
- Visual style: light background, professional teaching style, clear Chinese labels, readable hierarchy.
- Output target: local image file suitable for insertion into the webpage.

Also keep a text fallback outline for accessibility and review.

### 7. Produce Teaching Reference Animations With Remotion

For each key or difficult knowledge point, design a short teaching animation plan and use the Remotion plugin to produce the teaching reference animation. Do not implement final teaching animations as plain CSS/SVG/vanilla JavaScript unless the user explicitly accepts a fallback.

Each animation design must include:

- Animation title.
- Target misconception.
- Visual metaphor or process.
- Teacher narration script.
- Student interaction.
- Expected learning breakthrough.

For Remotion output, include:

- Composition name.
- Duration and aspect ratio.
- Scene sequence.
- On-screen text.
- Motion description.
- Optional voiceover script.
- Rendered video or local preview asset path.

Insert the rendered Remotion output into the final webpage with a `<video controls>` element or an equivalent local embed. Include the narration script and teacher-use notes below each animation.

### 8. Design Assessment And Acceptance Standards

Create an assessment scheme aligned with tasks and skills.

Include:

- Overall project acceptance standard.
- Task-level acceptance tables.
- Process assessment.
- Product assessment.
- Knowledge assessment.
- Safety/specification/compliance checks when relevant.
- Rubric levels such as Excellent, Qualified, Needs Improvement.

Task acceptance tables should include task, evidence, criteria, score, method, assessor, and feedback.

### 9. Generate The Interactive Teaching Process Webpage

Create a complete light-theme HTML file that orders content as:

1. Learner level and source content.
2. Selected project overview.
3. Task decomposition.
4. Task-skill matrix.
5. Task-knowledge matrix.
6. Key knowledge explanations.
7. Image2-generated skill mind map image.
8. Image2-generated knowledge mind map image with key markers.
9. Remotion teaching reference animations.
10. Acceptance standards and task rubrics.
11. Real-time classroom interaction area.

Use `assets/interactive-page-template.html` as the preferred structure. Adapt copy, colors, and components to the subject. The page must work as a standalone local file.

## Design Requirements For The Webpage

- Use a light background and a professional teaching layout.
- Treat the teacher as facilitator and students as active participants.
- Provide tabs or step navigation for the teaching process.
- Include checklists, expandable details, formative questions, and interaction prompts.
- Insert local Image2-generated mind map images, with text fallbacks.
- Insert local Remotion-rendered animation videos or embeds, with narration and usage notes.
- Avoid relying on remote assets. Generated images and videos should be local files referenced by relative paths.
- Keep Chinese labels clear and suitable for vocational education.

## References

- Read `references/project-teaching-method.md` when designing projects, tasks, skills, knowledge support, mind maps, animations, or rubrics.
- Use `assets/interactive-page-template.html` when generating the final webpage.
