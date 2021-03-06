# UConsole

A simple in-game console for unity.

### How to use

Add the UConsole project files to the asset folder. Add the ConsoleGui Monobehavior to any gameobject in your scene and thats it.

### Creating custom commands
You can create a custom command by calling the static method ConsoleCommandDatabase.RegisterCommand. Give it a name, description, and callback for your command.
```cs
ConsoleCommandDatabase.RegisterCommand("MYCOMMAND", "Does something", MyCallBack);

string MyCallBack(params string[] args) {
  // Does something
}
```

or

```cs
using UConsole;

namespace UConsole.Commands
{
   [UConsole.Command("MyCommand", "My Commands description.", "[usage])]
   public class MyCommand : ICommand
   {
      public string Execute(params string[] args)
      {
         return "Hello world!"
      }
   }
}
```

Any and all ICommands within the calling assembly will automaticly be registered to  UConsole at runtime.