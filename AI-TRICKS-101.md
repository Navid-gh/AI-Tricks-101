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

## [GRAPH ENGEERING VS LOOP ENGEERING](https://www.aibuilderclub.com/blog/graph-engineering-vs-loop-engineering) 

Loop engineering is designing the loop one agent runs: discover, plan, execute, verify, repeat until a stop condition. You stop hand-writing prompts and start designing the cycle and its exit test. (That's the whole discipline - our Loop Engineering guide covers why the verifier, not the model, is the bottleneck.)

Graph engineering is what you do when one loop isn't enough: you wire multiple specialized agents or steps into a graph.

Read the article in title link.


## [SDD (SPEC DRIVEN DEVELOPMENT)](https://martinfowler.com/articles/exploring-gen-ai/sdd-3-tools.html)
The spec becomes the source of truth for the human and the AI.

Read the article in title link.

---

## MY TOP SKILLS

## FRONT-MATTER

## EVALS

## WRITE SKILL

## WRITE SPEC

---

## AGENTS

## MEMORY

## FACTS

---

## MCP

## CDP (CHROM DEVTOOLS PROTOCOL)

## DESIGN
---

