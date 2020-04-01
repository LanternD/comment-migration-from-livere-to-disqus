# Intro

This is a short script to convert the LiveRe comments to disqus-compatible Generic(WXR) format.

# Steps

## Step 1

Go to LiveRe Admin, change the data start/end date, which generates a table with 10 comments per page.

## Step 2

- Right click the table on Chrome (or whatever browsers that do the work), click "Inspect".
- Find the "table" element in the material list. 
- Right click on it and select "Copy -> Copy element".
- Create a new file naming `table_<page_number>.html` in the "html_tables" folder.
- Repeat this for all the pages. Or use some crawler to finish this step.

## Step 3

Change the func_switch to 1 at the end of `migration_main.py`. Run the code, and get the json file, `livere_comments.json`. Check the whole file and make sure everything is good.

## Step 4

Change the func_switch to 2 at the end of `migration_main.py`. Run the code, and get the Generic(WXR) file, `disqus_import.xml`'.

## Step 5

Go to Disqus Admin, import the file.

Check this video: https://youtu.be/qQ8i6cYhGzk

# Note

- My code does not deal with comment thread. Please implement it yourself if you need it. 
- I prepended "【LiveRe】" to every comment. If you don't like it, remove at around Line 197 in "html_to_disqus_xml.py"
- No IP available at LiveRe, so I set the exported value as "127.0.0.2".
- No avartar available. But I think it is possible to add it.
