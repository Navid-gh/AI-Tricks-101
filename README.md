# AI TRICKS 101

in this file, i describe AI tricks and the some usefull concepts.
if you think missing concepts, please send me PR and complete this file.

--- 

## 1. PROMPT

prompt is share language between user and AI model. each agent can enhance the input prompt to get better result.
therefore, if we more describe what we need, we reach the better results.

### 1.1 REMEMBER 

```
"AI models are stupid workers that don't know what you want, so tell exatly their jobs".  
in the other words, "You can drink wine in bowl or glass. with both of them, you drinking watter. BUT AT WHAT COST?"
```

### 1.1 ROLE

i giving role to my model when i wanna writing spec (describe in following), implement feature, or big jobs.
this trick help ai model to how it SHOULD thinking and reasonning.

#### Example
```
you are senior software engineer.

i wanna write spec file to implement something...  
```

## 1.2 AI QUESTIONS

you should learn that humans has question when you say your idea. so, AI models can have it.
my trick is write this line at the ANY PROMPT.

```
you are senior software engineer.

i wanna write spec file to implement something...  

if you have any question, ask them before starting.
```

it help to AI model for being in the same page. 

**this trick is the most important trick!**

## 1.3 I/O FORMAT

one of the most missing information in spec files, skills and etc is i/o format.
that means AI agent what should expected as input (prompt, file, etc) and how to generate output.

#### Example

```
you are senior software engineer.

i wanna write spec file to implement something...  

the input format should be one **spec file in md format** with this templete:

"""
# {FEATURE_TITLE}
[description about the feature]

## GOALS
[list of the goals]
"""

you should write the **spec file in md format** as output in this format:

"""
# {FEATURE NAME}
[description about the feature]

## BESINESS LOGIC
[describe besiness logic step by step]
"""

if you have any question, ask them before starting.
```

## 1.4 GAURDRAILS

gaurdrails are prohibited rules. if you wanna limit AI model to doing something, this section for it.

#### Example

```
you are senior software engineer.

i wanna write spec file to implement something...  

the input format should be one **spec file in md format** with this templete:

"""
# {FEATURE_TITLE}
[description about the feature]

## GOALS
[list of the goals]
"""

you should write the **spec file in md format** as output in this format:

"""
# {FEATURE NAME}
[description about the feature]

## BESINESS LOGIC
[describe besiness logic step by step]
"""

GAURDRAILS:
- never delete anything without user permission
- you should follow the i/o format and do not add extra sections 

if you have any question, ask them before starting.
```

## 1.5 DICTIONARY

some words has multiple or fancy meaning. you should describe those words to AI agent figure the exat meaning of them.

### Example

```
find the magic in the code.

magic: the complex with bad practice of the each section code are magic.
```

---

## 2. PHILOSOPHY

### 2.1 [GRAPH ENGEERING VS LOOP ENGEERING](https://www.aibuilderclub.com/blog/graph-engineering-vs-loop-engineering) 

Loop engineering is designing the loop one agent runs: discover, plan, execute, verify, repeat until a stop condition. You stop hand-writing prompts and start designing the cycle and its exit test. (That's the whole discipline - our Loop Engineering guide covers why the verifier, not the model, is the bottleneck.)

Graph engineering is what you do when one loop isn't enough: you wire multiple specialized agents or steps into a graph.

Read the article in title link.


### 2.2 [SDD (SPEC DRIVEN DEVELOPMENT)](https://martinfowler.com/articles/exploring-gen-ai/sdd-3-tools.html)
The spec becomes the source of truth for the human and the AI.

Read the article in title link.

---

## 3. MY TOP SKILLS

### 3.1 [graphify](https://github.com/Graphify-Labs/graphify)
Type `/graphify` in your AI coding assistant and it maps your entire project into a knowledge graph you can query instead of grepping through files.
it can help for travers in code easily and find the targets exatly. in implementation feature, it can increase your accurecy to reach a better results.

### 3.2 [skill-creator](https://github.com/anthropics/skills/tree/main/skills/skill-creator)
if you say that you create skill without this skill, doubt yourself.
maybe you need **review** and change some thing after generating skill via this skill.

### 3.3 [caveman](https://github.com/JuliusBrussee/caveman)
Make your AI coding agent talk like a caveman.
Same answers. 65% fewer output tokens on prose,
8.5% on long-horizon agentic coding runs. Brain still big. Mouth small.

### 3.4 [feature-manager](https://github.com/blkst8/skills/tree/master/skills/feature-manager)
this skill writen by me and it looks like [goalbuddy](https://github.com/tolibear/goalbuddy).
both skills generate md file that define some goals and tasks based on your feature. after define path for implementaion, they can starting implementaion with the goals.

---

## 4. SKILLS & SPEC

in this section i describe how to write skills and specs.  

### 4.1 FRONT-MATTER

Frontmatter is a **metadata block** at the very top of a Markdown file, wrapped in `---` delimiters.
frontmatter used in skills, but you can use it in your generated md files (e.g. docs).

#### Example

i create doc for a project and i add frontmatter in this template:

```
---
branch: main
commit-hash: 8jsid82
generated-by: blkst8
date: 2026-08-01
---
```

### 4.2 EVALS
“Evals skills” usually refers to evaluating AI skills — testing how well an AI model or agent performs specific tasks.

Evals is short for evaluations. In AI, evals are structured tests used to measure abilities such as:

- Reasoning
- Coding
- Math
- Writing quality
- Instruction following
- Tool use
- Safety
- Factual accuracy
- Multilingual ability
- Domain knowledge

AI evals help developers understand:

- What the AI is good at
- Where it fails
- Whether a new model is better than an old one
- Whether the AI follows instructions correctly
- Whether it is safe and reliable


## 4.3 WRITE SPEC

for most tasks i use spec file. spec file is source of truth of your AI.
therefore, it's more importent file in your workflow.

i ussuly write my specs something like this:

```
# {title of my feature}
[describe what i wanna in this spec file]

## DICTIONARY
[for more informaition read 1.5]

## TECH/BESINESS LOGIC
[describe what i need in text and bollet points]

## Measurement Criteria
[describe what criteria importent to you. e.g. maintainablity, test covrage, extenable, etc]

## ALGORITHM
[if you need run algorithm you should tell it to agent step by step.]

## Rules
[list all rules that AI models should to observe]

## ❌ Wrong Behavior (Do NOT do this)
[say with **example** that what exatly wrong in implementation. this section can help to model to prevent from over-enginering. this is diffrent from gaurdrails.]

## 📊 Expected Behavior
[say with **example** that what exatly you need.]

## GAURDRAILS
[for more informaition read 1.4]
```

you can add or remove sections.

after writing your spec, give it to agent to reviwe, find edge-cases, and their questions (read 1.2).
after it, you can tell your AI model to rewrite it. the new version of your spec file, is most complete and AI comatible.

**DO NOT FORGET TO REVIEW THE LAST VERSION OF SPEC WRITEN BY AI!!!**

## 4.4 WRITE SKILL


---

## AGENTS

## MEMORY

## FACTS

---

## MCP

## CDP (CHROM DEVTOOLS PROTOCOL)

## DESIGN
---

