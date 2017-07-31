---
title       : Chapter 2
description : The Next Frontier

--- type:NormalExercise lang:r xp:10 key:2c3a3ca7e3
*** =video_link
//player.vimeo.com/video/108225030

*** =instructions
### An Exercise
This is my exercise. Plox assign 2 to `y`.

*** =pre_exercise_code
```{r}
```

*** =sample_code
```{r}
y # fill in
```

*** =hint
Use your brain. It's quite helpful.

*** =solution
```{r}
y <- 2
```

*** =sct
```{r}
test_error()
test_object("y",
    undefined_msg = "You should define `y`.",
    incorrect_msg = "`y` has an incorrect value.")
```
