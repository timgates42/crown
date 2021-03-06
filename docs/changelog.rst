Changelog
=========

0.40.0
------
*DD MMM YYYY*

**Data Compiler**

* Fixed an issue that caused the compiler to crash when reading empty source files
* Fixed an issue that prevented the output from external data compilers to not be read under Windows

**Runtime**

* Removed support for multiple components per Unit.

**Tools**

* Added the ability to select from a number of templates (samples) when creating new projects
* Fixed an issue that caused the Level Editor to ask multiple times whether save the level in some circumnstances
* Level Editor now restores the Console's history from previous sessions

**Lua API**

* All component managers accessors have been uniformed to accept a component instance ID (instead of a UnitId or both):
	- All ``AnimationStateMachine.*``, except ``AnimationStateMachine.create()``
	- All ``RenderWorld.light_*``, except ``RenderWorld.light_create()``
	- All ``RenderWorld.sprite_*``, except ``RenderWorld.sprite_create()``
	- All ``SceneGraph.*``, except ``SceneGraph.create()``
	- All ``World.camera_*``, except ``World.camera_create()``
	- ``PhysicsWorld.actor_instances()``
* Added AnimationStateMachine.instance()
* ``RenderWorld.set_mesh_visible()`` will now work as expected

0.39.0
------
*24 Oct 2020*

**Data Compiler**

* Fixed detection on new sub-directories and sub-directory renames
* Fixed handling of paths without type extension
* Improved file deletion detection and data directory coherence
* Improved file modification detection and source index caching
* Improved the unit compiler by fixing a number of bugs and adding support to "deleted_components"

**Runtime**

* Removed support for 32-bit x86 architectures

**Tools**

* Added ability to crate new scripts from Project Browser
* Added ability to crate new units from Project Browser
* Added Debug > Build Data
* Added QWER accelerators to place, move, rotate and scale object actions
* Added support for Windows
* Added the ability to duplicate objects from Level Tree
* Added Welcome panel with a list of recent projects and the ability to create new projects or import existing ones
* Bumped minimum GTK+ version to 3.16 (Ubuntu 16.04.2+)
* Fix an issue that caused the Editor View camera not returning to idle in some circumnstances
* Fixed a number of dialog boxes that were not centered to the Level Editor's main window
* Fixed an issue that allowed the user to enter blank names when creating new folders in the Project Browser
* Fixed an issue that caused Project Browser to show inconsistent folder structured in some circumnstances
* Fixed an issue that caused the camera view accelerators to interfere with text input
* Fixed an issue that prevented some components from being removed when reimporting sprites
* Fixed and issue that caused generation of spurious "set-actions" when editing properties in the Properties panel
* Fixed modifier keys getting stuck in the wrong state in some circumnstances
* Fixed multiple selection in Level Tree
* Fixed undo/redo when setting properties of some unit components
* Improved Project Browser to not show irrelevant items
* Improved Test Level/Start Game button behavior when game failed to launch
* Level Editor connection to the Data Compiler, Editor View(s) and Game is now faster and more robust
* Level Editor now saves aggregate logs to disk. User can browse logs folder from Help > Browse Logs...
* New Project dialog no longer allows selecting non-empty folders for new projects
* Objects inside .level files are now ordered by their ID before serialization
* Save Level dialog now warns before overwriting a file that already exists
* Unified Engine and Run menubar items into a single Debug menubar item

**Lua API**

* Added Matrix4x4.equal()

0.38.0
------
*24 Aug 2020*

**Runtime**

* Added "help" command
* Core primitives now include UV, tangent and bitangent data
* Fixed a crash when multiple clients were connected to the Console Server
* Fixed a crash when reloading lua scripts that haden't been loaded previously
* Fixed an issue that caused levels to be compiled successfully even when the units they depended on contained errors
* Fixed reloading of main.lua files from samples
* The Data Compiler now detects when files are deleted

**Tools**

* Added Gizmo size and Autosave timer options to Preferences dialog
* Added the ability to toggle visibility of the Inspector inside the Level Editor
* Added the Project Browser
* Added the Statusbar
* Fixed an issue that allowed the Level Editor to load or save levels outside the source directory
* Fixed an issue that allowed the user to enter blank names when renaming objects in the Level Tree
* Fixed an issue that caused level auto-saving in Level Editor not triggering at the intended interval
* Fixed an issue that caused the Level Editor to not include "core/units/camera" in the boot.package of a newly created project
* Fixed an issue that caused the Level Editor to start the Editor View before data compilation was done in some circumstances
* Fixed main.lua files generated by Level Editor for new projects
* Improved look of EntryVector3 widget
* Lua reloading has been extended to the running game when pressing F5 from the Level Editor
* Nodes in the Level Tree can now be exanded by clicking on the corresponding row
* Preferences are now saved to the user's config directory
* Renaming of objects in the Level Tree is now handled with a modal dialog
* The Editor View will now show a message explaining how to recover the session after a crash or unintended disconnection
* Unified the asset import dialogs

**Samples**

* Unified projects directory structure

0.37.0
------
*26 Jun 2020*

**Runtime**

* Added Material.set_vector4() and Material.set_matrix4x4()
* Added PhysicsWorld.actor_destroy()
* Added RenderWorld.mesh_material(), RenderWorld.mesh_set_material() and RenderWorld.sprite_material()
* Added the ability to hot-reload Lua files
* Added the ability to scale the shape of colliders at Unit spawn time
* Added Window.set_cursor_mode()
* Added World.unit_by_name() to retrieve unit by its name in the Level Editor
* Bumped minimum Android version to 7.0+
* Bumped minimum OpenGL version to 3.2+ for Linux
* Fixed an issue that caused PhysicsWorld.set_gravity() to re-enable gravity to actors that previously disabled it with PhysicsWorld.actor_disable_gravity()
* Fixed an issue that prevented kinematic actors to be controlled via the SceneGraph
* Fixed an issue that prevented PhysicsWorld.actor_center_of_mass() to be called for static actors
* Fixed an issue that prevented PhysicsWorld.actor_world_{position,rotation,pose}() to be called for static actors
* Fixed an issue that reset the sprite animation to the beginning even when loop was set to false
* Fixed an issue where a regular Matrix4x4 was returned if Matrix4x4Box is called without arguments
* Removed "io" and "os" libraries from Lua API
* Small fixes and performance improvements
* Sprite's frame number now wraps if it is greater than the total number of frames in the sprite

**Tools**

* Added the ability to specify a circle collider in the Sprite Importer
* Added the ability to specify the actor class in the Sprite Importer
* Added the ability to specify the destination of the console commands between Game and Editor
* Fixed a crash when entering empty commands in the console
* Fixed an issue that caused the Level Editor to not correctly save a level specified from command line
* Fixed an issue that could cause the Level Editor to crash when large number of TCP/IP packets were sent to it
* Fixed an issue that could cause the Level Editor to crash when scrolling through the console history
* Fixed an issue that could cause the Level Editor to incorrectly parse identifiers in SJSON files
* Fixed an issue that generated wrong render states when blending is enabled while no blend function/equation is specified
* Fixed an issue that prevented some operations in the Level Editor from being (un/re)done
* Fixed an issue that prevented the data compiler from restoring and saving its state when launched by the Level Editor
* Improved the numeric entry widget which now takes less space and provides more convenient input workflows
* Resources autoload is disabled when testing levels from Level Editor
* The Data Compiler will now track data "requirements" and automatically include them in packages when it's needed
* The game will now be started or stopped according to its running state when launched from the Level Editor
* The Properties Panel now accepts more sensible numeric ranges
* The Properties Panel now allows the user to modify most Unit's component properties
