---
name: vocational-project-teaching-designer
description: Convert traditional course content for vocational or undergraduate teaching into project-based teaching designs. Use when the user provides a learner level such as 中职, 高职, or 本科 and asks to transform teaching content into projects, task decomposition, task-skill and task-knowledge matrices, key knowledge explanations, skill and knowledge mind maps, teaching animations, assessment rubrics, or a light-theme interactive teaching process webpage.
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

### 5. Draw The Skill Mind Map

Create a project skill mind map using Mermaid mindmap syntax unless the user requests another format.

Center node: project title.

Branches:

- Task sequence.
- Core skills.
- Sub-skills.
- Tools/equipment/software.
- Performance evidence.

### 6. Draw The Knowledge Mind Map

Create a project knowledge mind map using Mermaid mindmap syntax.

Center node: project title.

Branches:

- Foundational knowledge.
- Task-specific knowledge.
- Key knowledge marked with `★`.
- Difficult knowledge marked with `▲`.
- Knowledge-to-skill transfer points.

### 7. Design Teaching Reference Animations

For each key or difficult knowledge point, design a short teaching animation plan and include an implementable HTML/CSS/JS animation block in the final webpage.

Each animation design must include:

- Animation title.
- Target misconception.
- Visual metaphor or process.
- Teacher narration script.
- Student interaction.
- Expected learning breakthrough.

Keep animations lightweight and self-contained. Prefer SVG/CSS/vanilla JavaScript so the webpage can run locally without network access.

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
7. Skill mind map.
8. Knowledge mind map with key markers.
9. Teaching reference animations.
10. Acceptance standards and task rubrics.
11. Real-time classroom interaction area.

Use `assets/interactive-page-template.html` as the preferred structure. Adapt copy, colors, and components to the subject. The page must work as a standalone local file.

## Design Requirements For The Webpage

- Use a light background and a professional teaching layout.
- Treat the teacher as facilitator and students as active participants.
- Provide tabs or step navigation for the teaching process.
- Include checklists, expandable details, formative questions, and interaction prompts.
- Render Mermaid diagrams if an internet connection is available, but also include readable text fallback.
- Avoid relying on external assets. Use inline SVG/CSS/JS for animations.
- Keep Chinese labels clear and suitable for vocational education.

## References

- Read `references/project-teaching-method.md` when designing projects, tasks, skills, knowledge support, mind maps, animations, or rubrics.
- Use `assets/interactive-page-template.html` when generating the final webpage.
