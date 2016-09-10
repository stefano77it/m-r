to run this project set the startup project as "CQRSGui" (will start a web UI).

to see what the program to do see:
- GUI (the program start)
  - the application start, with bus creation, handlers registration (in "CQRSGui/Global.asax.cs/Application_Start")
  - sent commands (in "CQRSGui/HomeController.cs")
- CQRS implementation:
  - bus:
    - handlers registration definition (in "SimpleCQRS/FakeBus.cs/FakeBus/RegisterHandler")
      - handlers registration fill a dictionary with Type as Key, Delegate as content (```Dictionary<Type, List<Action<Message>>> _routes``` in "SimpleCQRS/FakeBus.cs/FakeBus")
      - handlers registration (in "CQRSGui/Global.asax.cs/Application_Start")
    - send command definition (in "SimpleCQRS/FakeBus.cs/FakeBus/Send")
      - sent commands (in "CQRSGui/HomeController.cs")
    - publish events definition (in "SimpleCQRS/FakeBus.cs/FakeBus/Publish")
      - save events (in "SimpleCQRS/EventStore.cs/EventStore/SaveEvents")
      - published events, for further processing by subscribers (in "SimpleCQRS/EventStore.cs/EventStore/SaveEvents")
  - commands:
    - commands definition (in "SimpleCQRS/Commands.cs")
    - commands handlers definition (in "SimpleCQRS/CommandHandlers.cs")
  - events:
    - events definition (in "SimpleCQRS/Events.cs")
    - events handlers definition ("InventoryItemDetailView" and "InventoryListView" in "SimpleCQRS/ReadModel.cs")
- Relevant techniques:
  - dictionary with Type as Key, Delegate as content (```Dictionary<Type, List<Action<Message>>> _routes``` in "SimpleCQRS/FakeBus.cs/FakeBus"), filled by handlers registration 
