---
title: 08. Adding Sound
weight: 80
--- 

In this chapter we will add sound to the game, which is rather simple, given that FXGL
has a convenience method `play` that takes the name of a sound asset and plays it. FXGL
supports two types of sound - .wav files for sound effects, and .mp3 files for background
music. The `play` method automatically plays the sound as a sound effect or as background 
music depending on the file extension. If you need more control over audio, you can also
retrieve a reference to the audio player using `FXGL.getAudioPlayer`.


### Sound Assets

The sound assets belong in the folder "assets/sounds". There are a number of sound assets
to copy from the main [resources](https://github.com/dykstrom/mazela-man/tree/main/resources) folder:

* cherry.wav - when eating a cherry
* death.wav - when colliding with a ghost
* level.wav - when levelling up
* pill.wav - when eating a pill


### Calling Play

All calls to `FXGL.play` belong in the collision handlers. For example, here is the 
player-pill collision handler as it looks with sound effects added:

```java
    @Override
    protected void onCollisionBegin(Entity player, Entity pill) {
        FXGL.play("pill.wav");
        pill.removeFromWorld();
        FXGL.inc("score", 10);
        FXGL.inc("pills", -1);
        if (FXGL.geti("pills") == 0) {
            FXGL.inc("level", 1);
            FXGL.play("level.wav");
            Platform.runLater(() -> initLevel());
        }
    }
```

This was a short chapter, but then sound in FXGL is not very complicated. Now you can
proceed to the [next chapter](https://dykstrom.github.io/mazela-man-web/09_enable_main_menu/), where we enable the main menu.
