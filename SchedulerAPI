package io.hrsn.apis.scheduler;

import org.bukkit.Bukkit;
import org.bukkit.plugin.Plugin;

import java.text.DecimalFormat;

/**
 * THIS FILE AND ALL CONTENTS IN IT ARE COPYRIGHT (C) HRSN0410 2016, ALL RIGHTS RESERVED.
 * <p>
 * Any code contained within this document, as well as any associated APIs with similar branding
 * are the property of HRSN0410. Distribution, reproduction, taking snippets, or claiming any
 * content as your own will break the terms of this license, and void any agreements with you.
 */
public class SchedulerAPI {

    public enum RunType {

        SYNC,
        ASYNC

    }

    private static Plugin instance;

    public static boolean setInstance(Plugin pl) {

        instance = pl;

        return (instance != null);

    }

    @SuppressWarnings("deprecation")
    public static int scheduleDelayedTask(Runnable runnable, RunType runType) {

        if (runType == RunType.ASYNC) {

            return Bukkit.getServer().getScheduler().scheduleAsyncDelayedTask(instance, runnable);

        } else {

            return Bukkit.getServer().getScheduler().scheduleSyncDelayedTask(instance, runnable);

        }

    }

    @SuppressWarnings("deprecation")
    public static int scheduleDelayedTask(Runnable runnable) {

        return Bukkit.getServer().getScheduler().scheduleSyncDelayedTask(instance, runnable);

    }

    @SuppressWarnings("deprecation")
    public static int scheduleDelayedTask(Runnable runnable, RunType runType, double delay) {

        if (runType == RunType.ASYNC) {

            return Bukkit.getServer().getScheduler().scheduleAsyncDelayedTask(instance, runnable, (long)round(delay) * 20L);

        } else {

            return Bukkit.getServer().getScheduler().scheduleSyncDelayedTask(instance, runnable, (long)round(delay) * 20L);

        }

    }

    @SuppressWarnings("deprecation")
    public static int scheduleDelayedTask(Runnable runnable, double delay) {

        return Bukkit.getServer().getScheduler().scheduleSyncDelayedTask(instance, runnable, (long)round(delay) * 20L);

    }

    @SuppressWarnings("deprecation")
    public static int scheduleRepeatingTask(Runnable runnable, RunType runType, double interval) {

        if (runType == RunType.ASYNC) {

            return Bukkit.getServer().getScheduler().scheduleAsyncRepeatingTask(instance, runnable, 0L, (long)round(interval) * 20L);

        } else {

            return Bukkit.getServer().getScheduler().scheduleSyncRepeatingTask(instance, runnable, 0L, (long)round(interval) * 20L);

        }

    }

    @SuppressWarnings("deprecation")
    public static int scheduleRepeatingTask(Runnable runnable, double interval) {

        return Bukkit.getServer().getScheduler().scheduleSyncRepeatingTask(instance, runnable, 0L, (long)round(interval) * 20L);

    }

    @SuppressWarnings("deprecation")
    public static int scheduleRepeatingTask(Runnable runnable, RunType runType, double interval, double delay) {

        if (runType == RunType.ASYNC) {

            return Bukkit.getServer().getScheduler().scheduleAsyncRepeatingTask(instance, runnable, (long)round(delay) * 20L, (long)round(interval) * 20L);

        } else {

            return Bukkit.getServer().getScheduler().scheduleSyncRepeatingTask(instance, runnable, (long)round(delay) * 20L, (long)round(interval) * 20L);

        }

    }

    @SuppressWarnings("deprecation")
    public static int scheduleRepeatingTask(Runnable runnable, double interval, double delay) {

        return Bukkit.getServer().getScheduler().scheduleSyncRepeatingTask(instance, runnable, (long)round(delay) * 20L, (long)round(interval) * 20L);

    }

    public static void delayMethodTest() {

        SchedulerAPI.scheduleRepeatingTask(() -> {

            // run code here

        }, 5.3);

    }

    private static double round(double d) {

        DecimalFormat twoDForm = new DecimalFormat("#.#");
        return Double.valueOf(twoDForm.format(d));

    }

}
