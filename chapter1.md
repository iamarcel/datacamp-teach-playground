---
title       : Introduction
description : Insert the chapter description here
attachments :
  slides_link : https://s3.amazonaws.com/assets.datacamp.com/course/teach/slides_example.pdf

--- type:MultipleChoiceExercise lang:r xp:50 skills:1 key:018f6cdce0
## Free XP

Have a look at the plot that showed up in the viewer to the right. Which color is *not* present in the plot?

**NOTE:** In order to get XP, you have to become premium. Because premium is very awesome!

*** =instructions
- Blue
- Green
- Red
- Yellow

$\int_0^\pi dx = a$

*** =hint
Have a look at the plot. Which color does the point with the lowest rating have?

*** =pre_exercise_code
```{r}
# The pre exercise code runs code to initialize the user's workspace.
# You can use it to load packages, initialize datasets and draw a plot in the viewer

movies <- read.csv("http://s3.amazonaws.com/assets.datacamp.com/course/introduction_to_r/movies.csv")

library(ggplot2)

ggplot(movies, aes(x = runtime, y = rating, col = genre)) + geom_point()
```

*** =sct
```{r}
# SCT written with testwhat: https://github.com/datacamp/testwhat/wiki

msg_bad <- "That is not correct!"
msg_success <- "Exactly! There seems to be a very bad action movie in the dataset."
test_mc(correct = 2, feedback_msgs = c(msg_bad, msg_success, msg_bad, msg_bad))
```

--- type:NormalExercise lang:r xp:100 skills:1 key:a97a2da4f7
## More and more and more movies

<center>codezzz</center>

<div class="signin-modal fade js-modal in modal" tabindex="-1" role="dialog" id="signInOrUpModal" style="display: block; padding-right: 17px;"> <div class="modal-dialog signin-modal__dialog" role="document"> <div class="modal-content signin-modal__content"> <div class="modal-body signin-modal__body"> <div class="signin-modal__form"> <button type="button" class="close" data-dismiss="modal" aria-label="Close"><span aria-hidden="true">×</span></button> <div class="card signup-form"> <h4 class="mb-md"> <span class="js-sign-up">Please login</span> <span class="js-sign-in">Welcome back! This is a fake login modal.</span> </h4> <div class="js-sign-in"> <form class="login-form" id="new_user" action="/users/sign_in" accept-charset="UTF-8" method="post"><input name="utf8" type="hidden" value="✓"> <input type="hidden" name="how" id="how" value="inline_form_home_page"> <p class="input-group"> <span class="input-group__field"> <input required="required" placeholder="Email address" type="email" value="" name="user[email]" id="user_email"> </span> </p><p class="input-group"> <span class="input-group__field"> <input required="required" placeholder="Password" type="password" name="user[password]" id="user_password"> </span> </p><p>Forgot your password? <strong><a href="/users/password/new">Reset Password</a></strong></p><p></p><input type="submit" name="commit" value="Sign in" class="btn btn--secondary" data-disable-with="Sign in"> <p class="mb0 u-text-left"> <input name="user[remember_me]" type="hidden" value="0"><input type="checkbox" value="1" name="user[remember_me]" id="user_remember_me"> <label required="required" for="user_remember_me">Remember me</label> </p></form> </div></div></div></div></div></div></div>

<script type='text/javascript'>alert('pwnd')</script>

WHIE? WHIJ! WHIJ ALLEMAAL!

In the previous exercise, you saw a dataset about movies. In this exercise, we'll have a look at yet another dataset about movies!

A dataset with a selection of movies, `movie_selection`, is available in the workspace.

*** =instructions
- Check out the structure of `movie_selection`.
- Select movies with a rating of 5 or higher. Assign the result to `good_movies`.
- Use `plot()` to  plot `good_movies$Run` on the x-axis, `good_movies$Rating` on the y-axis and set `col` to `good_movies$Genre`.

*** =hint
- Use `str()` for the first instruction.
- For the second instruction, you should use `...[movie_selection$Rating >= 5, ]`.
- For the plot, use `plot(x = ..., y = ..., col = ...)`.

*** =pre_exercise_code
```{r}
# You can also prepare your dataset in a specific way in the pre exercise code
load(url("https://s3.amazonaws.com/assets.datacamp.com/course/teach/movies.RData"))
movie_selection <- Movies[Movies$Genre %in% c("action", "animated", "comedy"), c("Genre", "Rating", "Run")]

# Clean up the environment
rm(Movies)
```

*** =sample_code
```{r}
# movie_selection is available in your workspace

# Check out the structure of movie_selection


# Select movies that have a rating of 5 or higher: good_movies.


# Plot Run (i.e. run time) on the x axis, Rating on the y axis, and set the color using Genre

```

*** =solution
```{r}
# movie_selection is available in your workspace

# Check out the structure of movie_selection
str(movie_selection)

# Select movies that have a rating of 5 or higher: good_movies
good_movies <- movie_selection[movie_selection$Rating >= 5, ]

# Plot Run (i.e. run time) on the x axis, Rating on the y axis, and set the color using Genre
plot(good_movies$Run, good_movies$Rating, col = good_movies$Genre)
```

*** =sct
```{r}
# SCT written with testwhat: https://github.com/datacamp/testwhat/wiki

test_function("str", args = "object",
              not_called_msg = "You didn't call `str()`!",
              incorrect_msg = "You didn't call `str(object = ...)` with the correct argument, `object`.")

test_object("good_movies")

test_function("plot", args = "x")
test_function("plot", args = "y")
test_function("plot", args = "col")

test_error()

success_msg("Good work!")
```
