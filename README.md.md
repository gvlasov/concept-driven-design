Concept-driven design is a software engineering methodology whose goal is to promote

- Accidental complexity reduction
- Discoverability of codebase capabilities
- Ease of code maintenance
- Writing code that is equivalent to its specification in ease of reading by humans, so that even when the project is being written by an LLM, specifications produce deterministic results (they are just code)

The core of the methodology is:

- A [[Concept-driven directory structure|universal directory structure]] 
	- Every file is a [[Reflection]] of a concept
	- Every concept has its own directory where its reflections are grouped