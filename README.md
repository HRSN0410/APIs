# HRSN's APIs

## SchedulerAPI
An API dealing with the non-user-friendliness of the Bukkit API's Scheduler component.

<b>To Use:</b> Copy/Paste the contents of the SchedulerAPI.java into a new class called SchedulerAPI in your bukkit plugin.
(Then change the package name, of course)

<b>First,</b> you need to add the following code to the onEnable and onDisable methods in your main class:
```java
@Override
public void onEnable() {
    Scheduler.onEnable(this);
}

@Override
public void onDisable() {
    Scheduler.onDisable();
}
```
Note: The SchedulerAPI.onEnable() method returns true if successful, false if not!

Now, you're ready to use the API! There are two ways to schedule delayed tasks:
```java
Scheduler.scheduleDelayedTask(() -> {

}, double delayInTicks);
```

Or, if you need more options, you can do it like this:
```java
Scheduler.scheduleDelayedTask(() -> {

}, double delay, String options);
```

Similarly enough, you can schedule a repeating task simply:
```java
Scheduler.scheduleRepeatingTask(() -> {

}, double intervalInTicks);
```

Or the more complicated way:
```java
Scheduler.scheduleRepeatingTask(() -> {

}, double delay, String options);
```

As you can see, in some of these methods, there is a String argument called "options."
You can input various options to change the behavior of the method.
Some of the options include the following:
```"sync:false"``` runs your code async.
```"measurement:seconds"``` changes your delay to be in seconds instead of ticks.
```"delay:10"``` (Repeating tasks only). Delays your repeating task by that many of ticks or seconds, depending on which time measurement you're using.


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
