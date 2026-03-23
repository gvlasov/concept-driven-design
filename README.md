Concept-driven design (CDD) is a code organization methodology whose goal is to put the developer experience at the heart of software project development, in any kind of software project. It turns codebases from arcane spellbooks into accessible encyclopedias.

Open this repository as your [Obsidian](https://obsidian.md/) vault

CDD helps achieve:

- Accidental complexity reduction: less boilerplate, more cohesion.
- Discoverability of codebase capabilities: the directory structure is universal and can be applied to any new project.
- Ease of code maintenance by keeping the source code structure corresponding to the conceptual structure of the software
- Writing code that is equivalent to its specification in ease of reading by humans and LLMs, so that even when the project is being written by an LLM, specifications produce mostly deterministic results (they are just code)

The core of the methodology is:

- A [[Concept-driven directory structure|universal directory structure]] 
	- Every file is a [[Reflection]] of a concept
	- Every concept has its own directory where its reflections are grouped

CDD is based on the following axioms:

- Software exists to reflect some [[Reality|reality]] to a user
- Any reality consists of [[Concept|concepts]]
- Every software system consists of 
  - concept [[Reflection|reflections]], 
  - software [[Platform|platform]] and 
  - command [[Shell|shell]]
- Concept-driven design helps 
  - de-mingle concept reflections from the software platform and 
  - organize every kind of automated operation required during development

CDD will suit you well if you are:
- Someone who doesn't think that being pragmatic requires being messy
- A single developer or a tight small team of developers who need a structure that gives a strong base and allows great flexibility
- Someone with OCD on code organization

Downsides to CDD:
- You will have to figure out how to apply it to your technology stack
- Moving a legacy codebase to CDD will most probably take an unacceptable amount of time