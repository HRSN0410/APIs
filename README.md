# HRSN's APIs

## SchedulerAPI
An API dealing with the non-user-friendliness of the Bukkit API's Scheduler component.

<b>To Use:</b> Copy/Paste the contents of the SchedulerAPI.java into a new class called SchedulerAPI in your bukkit plugin.

<b>First,</b> you need to add the following code to the onEnable and onDisable methods in your main class:
```java
@Override
public void onEnable() {
    SchedulerAPI.onEnable(this);
}

@Override
public void onDisable() {
    SchedulerAPI.onDisable();
}
```
Notice: The SchedulerAPI.onEnable() method returns a boolean if successful!

###Different ways of scheduling tasks using Lambdas (Java 8+)
Sync Delayed Task (without delay?):
```java
SchedulerAPI.scheduleDelayedTask(() -> {
    // run code here
});
```

Sync Delayed Task:
```java
SchedulerAPI.scheduleDelayedTask(() -> {
    // run code here
}, double secondsUntilRun);
```

Async Delayed Task (without delay?):
```java
SchedulerAPI.scheduleDelayedTask(() -> {
    // run code here
}, boolean isSync);
```
If isSync is false, the task will run async.

Async Delayed Task:
```java
SchedulerAPI.scheduleDelayedTask(() -> {
    // run code here
}, boolean isSync, double secondsUntilRun);
```

Sync Repeating Task:
```java
SchedulerAPI.scheduleRepeatingTask(() -> {
    // run code here
}, double timeBetweenRuns);
```
If you use this, the delay will automatically be 0L.

Sync Repeating Task with Delay:
```java
SchedulerAPI.scheduleRepeatingTask(() -> {
    // run code here
}, double timeBetweenRuns, double secondsUntilRun);
```

Async Repeating Task:
```java
SchedulerAPI.scheduleRepeatingTask(() -> {
    // run code here
}, boolean isSync, double timeBetweenRuns);
```
As with the delayed tasks, if isSync is false, the task will run async.

Async Repeating Task with Delay:
```java
SchedulerAPI.scheduleRepeatingTask(() -> {
    // run code here
}, boolean isSync, double timeBetweenRuns, double secondsUntilRun);
```

<b>NOTE!</b> All of these methods return an integer, which is the TaskID of the Bukkit task! To cancel a task, save the integer somewhere, and run this bit of code:
```java
SchedulerAPI.cancelTask(int taskID);
```

###Without Lambdas (All versions of Java)
You can adapt the following snippets to meet your own needs:
```java
SchedulerAPI.scheduleDelayedTask(new Runnable() {
    @Override
    public void run() {
        // run code here
    }
}, arguments);

SchedulerAPI.scheduleRepeatingTask(new Runnable() {
    @Override
    public void run() {
        // run code here
    }
}, arguments);
```
Note: I personally thing Lambdas look super cool, but if you want to use the old way, you can.
