to run this project set the startup project as "CQRSGui" (will start a web UI).

to see what the program to do see:
- GUI (the program start)
  - the application start, with bus creation, handlers registration (in "CQRSGui/Global.asax.cs/Application_Start")
  - the command launched from the GUI (in "CQRSGui/HomeController.cs")
- CQRS implementation:
  - bus:
    - handlers registration (in "SimpleCQRS/FakeBus.cs.cs/RegisterHandler")
    - send commands (in "SimpleCQRS/FakeBus.cs.cs/Send")
    - publish messages (in "SimpleCQRS/FakeBus.cs.cs/Publish")
  - commands:
    - commands definition (in "SimpleCQRS/Commands.cs")
    - commands handlers definition (in "SimpleCQRS/CommandHandlers.cs")
  - events:
    - events definition (in "SimpleCQRS/Events.cs")
    - events handlers definition ("InventoryItemDetailView" and "InventoryListView" in "SimpleCQRS/ReadModel.cs")

