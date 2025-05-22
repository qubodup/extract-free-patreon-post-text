# extract-free-patreon-post-text
Extract Patreon text to put it on Fandom wikis, specific to Nerd Poker Podcast

# How to use

1. Go to the patreon, use the filter to pick 1 year and start scrolling until there's nothing left or you reach the last tracked post
2. Open developer tools (F12), find the div that contains each post inside their own divs and copy it from the code view into the [post link extractor](https://qubodup.github.io/extract-free-patreon-post-text/links/)
3. Paste the result onto A4 in Libreoffice (or maybe Google Sheets or Excel)
4. Back to the patreon, now click drag from the bottom right to select the "Share" of the last post from the bottom, let go, scroll to the top, hold down SHIFT and click left above the filter to select all content. Scroll wildly up and down to make sure all posts are active. With >100 posts it seems their content is partially hidden? Wiggle up and down. (Or split the task into month ranges manually)
5. Copy
6. Paste into the [post text extractor](https://qubodup.github.io/extract-free-patreon-post-text/text/), click Extract, Escape Cells, Select, press CTRL+C
7. Make sure you pressed CTRL+C, otherwise you will paste WYSIWYG into Libreoffice which will freeze it for 5 minutes or so
8. After pressing CTRL+C paste into cell B1
9. Into Cell G1 paste the code at the bottom of this and then drag the bottom right corner down a few until it touches the content, then double-click the thingie in the bottom right of the bottommost cell in G to auto-'expand' downards. Then drag down some more if you'll repeat this with more ranges later.

```
="|-
| "&B1&"
| ["&A1&" "&C1&"]
| "&E1&"
| "&SUBSTITUTE(F1,CHAR(10),CHAR(10))&"
"
```
10. Copy the G range into Fandom in source editor. Make sure to edit sections, not the whole page, unless you love lag. Best use `?veaction=editsource&section=2` etc to load the edit page.
