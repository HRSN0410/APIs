# HRSN's APIs

## SchedulerAPI
An API dealing with the non-user-friendliness of the Bukkit API's Scheduler component.

<b>To Use:</b> Copy/Paste the contents of the SchedulerAPI.java into a new class called SchedulerAPI in your bukkit plugin.

<b>First,</b> you need to add the onEnable and onDisable methods.
```javascript
@Override
public void onEnable() {
    SchedulerAPI.onEnable();
}

@Override
public void onDisable() {
    SchedulerAPI.onDisable();
}
```
Notice: The SchedulerAPI.onEnable() method returns a boolean if successful!
