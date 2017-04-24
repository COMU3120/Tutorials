# Gephi Guide

## Sections

**CLICK TO JUMP**

1. [Scraping from Reaper](#Scraping-from-reaper)

   [Facebook](#Facebook)
   [Twitter](#Twitter)
   [Reddit](#Reddit)
   [Yotube](#Yotube)

2. [Using Gephi](#Using-gephi)

3. [Doing analysis](#Doing-analysis)

## Things you need to have installed

**THESE MUST BE INSTALLED FOR YOUR PRACTICAL**

| Name             | Download link                            | Notes                                    |
| ---------------- | ---------------------------------------- | ---------------------------------------- |
| Gephi            | https://gephi.org/users/download/        | You must install this for your practical |
| Openrefine       | http://openrefine.org/download.html      | You should already have this installed   |
| Sublime Text     | https://www.sublimetext.com/             | You should already have this installed   |
| CSV Editor       | https://github.com/ScriptSmith/csveditor/ | Instructions for use are on that page. **If on a mac you need to right-click the program to open it the first time** |
| Reaper >= v0.1.7 | https://github.com/ScriptSmith/reaper/releases | Must be a version greater than or equal to v0.1.7 |

## Things you can graph in Reaper

*These are the only functions you should attempt to graph in Gephi*

**Click the blue to jump to the section on the page**

1. [Facebook](#Facebook)
   1. Post's comments
   2. Page's posts' comments
   3. Group's posts' comments

2. [Twitter](#Twitter)
   1. Search's tweets
   2. Hashtag's tweets

3. [Reddit](#Reddit)
   1. Thread's comments
   2. Search's threads' comments
   3. Subreddit's threads' comments

4. [YouTube](#Youtube) (**Not currently available**)

   1. Video's comments
   2. Search's videos' comments
   3. Channel's videos' comments

# Scraping from Reaper

The following are instructions for scraping from a source in Reaper, editing the files it extracts and viewing them in Gephi

## Facebook

### Post's comments

Tick the box to include information from the original post

In the original post's fields, make sure `From` is ticked

In the comment's fields, make sure `Parent` is ticked

![](files/tut4/comment_post_input.png)

Save it as a CSV

![](files/tut4/comment_post_view.png)

Open it in OpenRefine

Rename `from.name` to `Source`

![](files/tut4/rename_from.name.png)

Add a column named `Target` based on `original_post.from.name`

![](files/tut4/add_column_from_op.png)

Expression: `if(isNonBlank(rows.cells["parent.from.name"]), rows.cells["parent.from.name"].value, value)`

![](files/tut4/add_column_from_op_text.png)

Export from OpenRefine

![](files/tut4/openrefine_export.png)

### Page's posts' comments

Tick the box to include information from the original post

In the original post's fields, make sure `From` is ticked

In the comment's fields, make sure `Parent` is ticked

Select `posts` as the post type if you want posts from the page, select `feed` from the post type if you want posts from others as well

![](files/tut4/page_post_input.png)

Save it as a CSV

![](files/tut4/page_post_view.png)

Open it in OpenRefine

Rename `from.name` to `Source`

![](files/tut4/rename_from.name.png)

Add a column named `Target` based on `original_post.from.name`

![](files/tut4/add_column_from_op.png)

Expression: `if(isNonBlank(row.cells["parent.from.name"]), row.cells["parent.from.name"].value, value)`

![](files/tut4/add_column_from_op_text.png)

Export from OpenRefine

![](files/tut4/openrefine_export.png)

### Group's posts' comments

Tick the box to include information from the original post

In the original post's fields, make sure `From` is ticked

In the comment's fields, make sure `Parent` is ticked

![](files/tut4/group_post_input.png)

Save it as a CSV

![](files/tut4/group_post_view.png)

Open it in OpenRefine

Rename `from.name` to `Source`

![](files/tut4/rename_from.name.png)

Add a column named `Target` based on `original_post.from.name`

![](files/tut4/add_column_from_op.png)

Expression: `if(isNonBlank(row.cells["parent.from.name"]), row.cells["parent.from.name"].value, value)`

![](files/tut4/add_column_from_op_text.png)

Export from OpenRefine

![](files/tut4/openrefine_export.png)

## Twitter

### Search's tweets

Make sure that your search topic is recent and trending. You may want to select `recent` as your Result type

![](files/tut4/twitter_search_input.png)

Save it as a CSV

![](files/tut4/twitter_view.png)

Open it in CSV Editor

Select the following columns

![](files/tut4/twitter_csv_editor.png)

Save it from CSV Editor as a new file

*wait until `New Row Count` is the same as `Old Row Count` to confirm it is finished saving*

Open the new file in Sublime text

![](files/tut4/twitter_sublime_before.png)

Rename `user.screen_name` to `Source`

Rename `retweeted_status.user.screen_name` to `Target`

![](files/tut4/twitter_sublime_after.png)

Save the file

### Hashtag's tweets

Make sure that your hashtag is recent and trending. You may want to select `recent` as your Result type

![](files/tut4/twitter_hashtag_input.png)

Save it as a CSV

![](files/tut4/twitter_view.png)

Open it in CSV Editor

Select the following columns

![](files/tut4/twitter_csv_editor.png)

Save it from CSV Editor as a new file

*wait until `New Row Count` is the same as `Old Row Count` to confirm it is finished saving*

Open the new file in Sublime text

![](files/tut4/twitter_sublime_before.png)

Rename `user.screen_name` to `Source`

Rename `retweeted_status.user.screen_name` to `Target`

![](files/tut4/twitter_sublime_after.png)

Save the file

## Reddit

### Thread's comments

Check the box that says `Include parent`

*Note that when it is checked, Reaper can only download a maximum of 500 comments / thread*

![](files/tut4/reddit_thread_input.png)

Save it as a CSV

![](files/tut4/reddit_view.png)

Open it in Sublime Text

![](files/tut4/reddit_sublime_before.png)

Rename `data.author` to `Source`

Rename `parent.data.author` to `Target`

![](files/tut4/reddit_sublime_after.png)

Save the file

### Search's threads' comments

Check the box that says `Include parent`

*Note that when it is checked, Reaper can only download a maximum of 500 comments / thread*

![](files/tut4/reddit_search_input.png)

Save it as a CSV

![](files/tut4/reddit_view.png)

Open it in Sublime Text

![](files/tut4/reddit_sublime_before.png)

Rename `data.author` to `Source`

Rename `parent.data.author` to `Target`

![](files/tut4/reddit_sublime_after.png)

Save the file

### Subreddit's threads' comments

Check the box that says `Include parent`

*Note that when it is checked, Reaper can only download a maximum of 500 comments / thread*

![](files/tut4/reddit_subreddit_input.png)

Save it as a CSV

![](files/tut4/reddit_view.png)

Open it in Sublime Text

![](files/tut4/reddit_sublime_before.png)

Rename `data.author` to `Source`

Rename `parent.data.author` to `Target`

![](files/tut4/reddit_sublime_after.png)

Save the file

## YouTube

*Not currently available*

### Video's comments

### Search's videos' comments

### Channel's videos' comments



# Using Gephi

When first setting up Gephi, make sure your plugins are up-to-date

`Tools` -> `Plugins`

![](files/tut4/gephi_plugins.png)

Click the `Check for Updates` button and follow the process to install the updates for your plugins

## Importing Data

Import data by going to `File` -> `Import spreadsheet`

![](files/tut4/gephi_import.png)

Select the CSV file you want to import and import it as an `Edges Table`

*If the warning `Found row(s) with empty Source and/or Target columns` appears **and** it won't let you click `Next>`, make sure you've updated your plugins*

![](files/tut4/gephi_import_table.png)

Click `Next>` and then `Finish`

![](files/tut4/gephi_untouched.png)

There are 3 viewing modes, `Overview`, `Data Laboratory` and `Preview`

![](files/tut4/gephi_viewing_modes.png)

In `Data Laboratory` select `Copy data to another column`  and select `Id`

![](files/tut4/gephi_lab_copy.png)

Then select `Label`

Now in the `Overview`, when you click the button to add labels (the black **`T`** at the bottom), you can see the node's name

Choose the `Force Atlas 2` Layout

![](files/tut4/gephi_force_atlas_2.png)

Press the `Run` button to run the Layout

Press the `Stop` button to stop it when the graph stops moving significantly

Use the `Expansion` and `Contraction` layouts to expand and contract nodes. Make the scale factor > 1 to expand, > 0 and < 1 to contract

Click the spyglass on the left toolbar to see the entire graph

![](files/tut4/gephi_graph_atlased.png)

## Accounting for weight

Gephi doesn't allow for parallel edges, so it merges those edges into a single edge.

If you want to visualize the frequency (how often nodes are connecting) of edges between nodes, you need to include a weight

1. In Openrefine / CSV Editor, remove all the columns other that the `Source` and `Target`

   *We do this because we need to remove the unique identifiers for particular edges, which prevents merging edges*

2. Add a new column based on the `Source` column

3. Call it `Weight`, set the value of the expression to just be `1`

4. Export the CSV

Now when you view the network, parallel edges will be merged so that their weight is increased according to the number of parallel edges

## Doing analysis

See the quick-start guide to see what analsis you can do in Gephi

https://gephi.org/tutorials/gephi-tutorial-quick_start.pdf