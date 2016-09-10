to run this project set the startup project as "CQRSGui" (will start a web UI).

to see what the program to do see:
- GUI (the program start)
  - the application start, with bus creation, handlers registration (in "CQRSGui/Global.asax.cs/Application_Start")
  - the command launched from the GUI (in "CQRSGui/HomeController.cs")
- CQRS implementation
  - command definition (in "SimpleCQRS/Commands.cs")
  - command handlers (in "SimpleCQRS/CommandHandlers.cs")
  - events (in "SimpleCQRS/Events.cs")
  - event handlers ("InventoryItemDetailView" and "InventoryListView" in "SimpleCQRS/ReadModel.cs")
