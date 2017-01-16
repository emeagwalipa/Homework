# Implementation Engineering Homework

## Instructions

Please clone this repository and deliver your solutions in an archive format of your choice
(e.g. zip or tarball), including the entire contents of this repo along with your answers.<br/><br/>
_Do not submit your solution via pull request to this repository!_

## Questions

1. Download `http://www.google-analytics.com/ga.js` to a file named `ga_local.js` on your machine.

    1. How did you accomplish this?
    1. This file is full of a lot of gibberish. Are there more instances of the character a or g?<br/>
    How many of each? How did you determine this?
    1. Google has sensibly chosen size over readability for this file. Suppose that for your local copy,
    however, you wanted to rename the variables a, b, c, and g to apple, banana, carrot, and grapefruit.
    How would you do this?

1. For the following questions use the `./src/main/resources/aSkDddKs.csv` file found in this repo and assume the
file is 100GB in size and too big to simply open in an editor:

    1. Does the file include a header row? How did you determine this?
    1. How many lines, words, and characters are in the file? How did you determine this?
    1. Suppose you wanted to load this file into table in a database. How would you accomplish this?
    1. Column 0 contains the filename of jpg files. Imagine these files were hosted at: `http://www.yourdomain.com/images/`
    and you wanted to download all of these images to a local folder on your machine. How would you accomplish this?

1. Write a regular expression to capture the three components of a standard 10 digit US telephone number.
Your regular expression should handle, at a minimum, the following formats:

    ```bash
    xxx-xxx-xxxx
    (xxx) xxx-xxxx
    xxx xxx xxxx
    xxx.xxx.xxxx
    ```

    1. Adapt your regular expression to support the area code being optional.

1. Write standard SQL syntax that will create a `users` table, including indexes, with the following structure:

    ```sql
    id (integer, primary key)
    username (string)
    email (string)
    signup_date (date)
    ```

    1. Imagine that this table does not enforce uniqueness on `username`. An application that uses this table has allowed
    the table to be "corrupted" by allowing multiple users to sign up with the same `username`. Write SQL that would
    generate a list of the usernames and the most recent `signup_date` for that `username`, for all usernames that have
    multiple instances in the table.
    1. Write SQL that will generate a list of unique `email` addresses for all the usernames returned in the previous question
       (part i)
    1. Imagine your schema includes a second table `user_actions` that contains a `user_id` column that is a foreign key
    to the `users.id` column. Write SQL that will return the usernames and emails for all users in the `users` tables that
    have no rows in the `user_actions` table.
    1. Imagine your "corrupted" table has magically been cleaned such that no `username` exists on multiple rows in the table.
    Write SQL that will modify the structure of the table that will enforce that the multiple `username` scenario cannot reoccur.

1. What utility would you use to schedule a job under UNIX?

    1. What syntax would you use to schedule a script `run.sh` to run at 6:15PM every Tuesday during March, June,
    September and December.
    1. Adapt this so that it runs only every other Tuesday during those same months.
