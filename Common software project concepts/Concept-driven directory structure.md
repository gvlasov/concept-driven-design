A hierarchical directory structure of a [[Project]] where on the first level there are only [[Concept|concepts]], and on the 2nd and deeper levels there are the [[Reflection|reflections]] of the corresponding concepts

Similar to feature-sliced directory structure

**Example:**
/app/
/platform/
/commands/
/app/apples/
/app/apples/Apple.php
/apples/Apple.vue
/app//trees
/app//trees/Tree.php
/app//trees/tree.ini
/app//trees/images/Tree1.png
/app//trees/images/Tree2.png
/app/trees/README.md
/platform/docker
/platform/vite
/platform/npm
/commands/up

**Rules:**
- Application code and platform code are separate. Application code is all reflections of the concepts: 
	- UI views, 
	- database models, 
	- controllers, 
	- resources, 
	- tests
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
<?php
echo "Hello world!";


But as the application grows, 