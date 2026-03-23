Concept-driven design (CDD) is a code organization methodology whose goal is to put the developer experience at the heart of software project development, in any kind of software project. It turns codebases from arcane spellbooks into accessible encyclopedias.

It helps achieve:

- Accidental complexity reduction - less boilerplate, more cohesion.
- Discoverability of codebase capabilities
- Ease of code maintenance by keeping the source code structure corresponding to the conceptual structure of the software
- Writing code that is equivalent to its specification in ease of reading by humans and LLMs, so that even when the project is being written by an LLM, specifications produce mostly deterministic results (they are just code)

The core of the methodology is:

- A [[Concept-driven directory structure|universal directory structure]] 
	- Every file is a [[Reflection]] of a concept
	- Every concept has its own directory where its reflections are grouped

CDD is based on the following axioms:

- Software exists to reflect some reality to a user
- Any reality consists of concepts
- Every software system consists of concept reflections, platform and command shell
- Concept-driven design helps demingle concept reflections from platform and 

CDD will suit you well if you are:
- A single developer or a tight small team of developer who prefer agility over standardization
- Someone with OCD on code organization
- 