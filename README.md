### Sublime-specific instructions

Install [Terminus](https://packagecontrol.io/packages/Terminus) (via package control). This is a terminal run within sublime, and it lets us write some plugins that take the state in sublime, like where your cursor is, what's highlighted, etc., and use that to run a desired command line instruction.

Take the files in the "sublime_custom_commands" sub-directory of this repo, and copy them into the Packages/User/ directory of your Sublime Application. This should be a directory with a path that looks something like /wherever/your/sublime/lives/Packages/User/

Add some keybindings to reference these commands. Here's what I have inside my key_bindings file, you can find your own under the menu Sublime Text -> Settings -> Keybindings

```
    { "keys": ["shift+alt+r"], "command": "manim_run_scene" },
    { "keys": ["alt+r"], "command": "manim_checkpoint_paste" },
    { "keys": ["ctrl+shift+r"], "command": "manim_recorded_checkpoint_paste" },
    { "keys": ["ctrl+alt+r"], "command": "manim_skipped_checkpoint_paste" },
    { "keys": ["alt+e"], "command": "manim_exit" },
    { "keys": ["alt+/"], "command": "comment_fold"},
```

For example, I bind the "shift + alt + R" to a custom "manim_run_scene" command. If the cursor is inside a line of a scene, this will drop you into the interactive mode at that point of the scene. If the cursor is on the line defining the scene, it will copy to the clipboard the command needed to render that full scene to file.

I bind "alt + R" to a "manim_checkpoint_paste" command, which will copy whatever bit of code is highlighted, and run "checkpoint_paste()" in the interactive terminal.

Of course, you could set these to whatever keyboard shortcuts you prefer.