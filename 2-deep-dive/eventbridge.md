

## CloudWatch Events and EventBridge

CloudWatch Events and EventBridge have visibility over events generated by supported AWS services within an account.

They can monitor the default account event bus - and pattern match events flowing through and deliver these events to multiple targets.

They are also the source of scheduled events which can perform certain actions at certain times of day, days of the week, or multiple combinations of both - using the Unix CRON time expression format. Both services are one way how event-driven architectures can be implemented within AWS.

💡 **Note:** **EventBridge** is replacing **CloudWatch Events**

### Key Concepts

- **If X happens, or at Y time(s), do Z**
- EventBridge is sort of CloudWatch Events v2
- **Use EventBridge!**
- A default Event bus for the account
  - In CloudWatch Events this is the only bus (implicit)
  - EventBridge can have additional busses
- Rules match incoming events (or schedules)
  - Schedules sort of like CRON jobs
- Route the events to one or more Targets, e.g., AWS Lambda
