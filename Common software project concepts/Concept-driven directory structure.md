A hierarchical directory structure of a [[Project]] where on the first level there are only [[Concept|concepts]], and on the 2nd and deeper levels there are the [[Reflection|reflections]] of the corresponding concepts

**The problem it solves:**
For the entire software development history, project directory structures were created for tools to ingest, not for humans to read. Tools want files grouped *by the tool* that uses them: tests ran with PHPUnit in /tests, source code compiled with esbuild in /src/resources/typescript. But for people it is more natural to group files *by the concep*t they reflect.

Inspiration is drawn from:
- Feature-sliced directory structure
- Wikipedia - organizing everything about a concept in one place, with links between concepts and no single definitional hierarchy of the concepts, there is no "root" concept on wikipedia - only reflections of the real world.

See [[Diagram.url]]

**Structure:**
All project code is separated into:
- /concepts - concepts code is all reflections of the concepts, grouped in directories by a specific concept
- /platform - code that prepares framework, runtime environment, inftrastructure - any means that run our application reflect the problem being solved with it.
- /platform/commands - for the project developer to operate the project in building. 
	- Setting up the project
	- Bringing it up for manual testing
	- Operating data state from command line
	- CLI commands
	- GUI commands (like some launcher)
- /sandbox - anything we have to actively work on but have yet do decide how to properly decompose it into concepts/platform. Staging area for ongoing experiments.

**Example:**

```
/concepts/
/platform/
/commands/
/concepts/apples/
/concepts/apples/Apple.php
/concepts/apples/Apple.vue
/concepts/trees
/concepts/trees/Tree.php
/concepts/trees/tree.ini
/concepts/trees/images/Tree1.png
/concepts/trees/images/Tree2.png
/concepts/trees/README.md
/platform/docker
/platform/vite
/platform/npm
/plttform/entrypoints
/commands/up
```

**Rules:**
- Concepts code and platform code are the main separation. It is deemed the most useful distinction for the project code, because most of the time you can definitely say if some expression reflects a concept code or is platform code. 
	- UI views, 
	- database models, 
	- controllers, 
	- resources, 
	- tests
	- migrations for the models - extracted in classes, with subsequent migration  code as separate methods, but called somewhere in called in /platform/migrtations / /platform/databases
- Platform code is anything that sets up the frameworks and operating system tools to run the application: 
	- Docker, 
	- package managers, 
	- linters, 
	- test runners
	- entry points for various runtime environments (e.g. artisan.php as CLI entry point and index.php as web entry point for Laravel)
- Commands is anything that is used by the administrator (of the production or dev environment) to run the application.
	- Use /commands/$ENVIRONMENT_NAME directories , e.g. /commands/dev, /commands/prod
	- Use symlink at /commands/local to point to the current environment, set it up at deployment time (when developer sets up the project, or when administrator deploys the project on production)


Anything that is still in /platform but relates to a specific concept must be extracted from platform to that concept directory. Theoretically, in a degenerate case, /platform can contain the whole application if it is extremely simple and fits to a single entry point (like a Hello World application):

/platform/entrypoints/index.php

```
<?php
function helloWorld() {
  echo "Hello world!";
}
if ($_GET['hello']) {
  helloWorld();
}
```
