This markdown document contains coding standards for Godot projects that you must follow whenever writing code or interacting with the GDAI MCP server to update Godot projects.

# Test ability

- Optimize for readability and ease of troubleshooting
- Break out node trees into independently runnable and testable scenes
- Minimize coupling and direct dependencies between scenes and export configuration variables where it makes editor usability and testing easier

# Naming standards
Begin by complying with the naming standards published [here](https://docs.godotengine.org/en/stable/tutorials/scripting/gdscript/gdscript_styleguide.html).Then, treat the below requirements as superceding mandates.

- Generic naming such as, Button_1, is never used. Instead, descriptive names will be used for all variables, functions, scenes, nodes, etc. For example, Button_1, could become, SaveButton.
- Abbreviations are avoided in favor of using fully qualified words/names.
- Variables are strongly typed for any method signatures
- Void functions are explicitly labeled as void

# Project Structure

- Minimize the use of direct method calls between Nodes. Instead, favor the use of signals for communication
- Every project should have a SceneHandler that autoloads and is accessible to all scenes
- Every project's starting node is named Game and is the generic Node type
- On ready, the Game script will call a method in the SceneHandler to load the openning scene
- Generic helper functions and global variables are kept in an AutoLoad script named Global
- Purpose-specific configuration files are used, when appropriate, to keep game configuration abstracted away from scene code
- When using inheritance, always leverage class_names rather than ```extends "res://"``` formats

# 