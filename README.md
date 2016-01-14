# randomoji

This is a tiny script that randomly selects any number of GitHub-style [emoji tags](http://www.emoji-cheat-sheet.com/) and prints them to STDOUT.

This is useful for when you want to express that you like somebody's Pull Request, but a simple :+1: just won't cut it. There are hundreds of great emoji out there that you've never even heard of, just waiting to be used. Why stick with a tired thumbs-up when there are so many other options? Using a script to randomly select emoji gives every emoji's voice a chance to be heard.

## Example

```
$ ./randomoji 5
:cinema: :heart_eyes: :abcd: :older_woman: :japanese_ogre:
```

## Usage

`randomoji` requires [Boot](http://boot-clj.com) to run, so install that if you haven't already.

For greater convenience, I recommend setting up a shell function that composes `randomoji` with `pbcopy`, saving you the trouble of manually selecting and copying the emoji. Here's mine (note: this is [fish shell](http://fishshell.com/), not bash):

```fish
function randomoji
  set emoji (eval $HOME/Code/randomoji/randomoji $argv[1])
  printf $emoji | pbcopy
  echo "$emoji copied to clipboard"
end
```

This gives me the ability to run the script from any directory, and have the resulting emoji automatically copied to my clipboard, ready to drop straight into a Pull Request.

```
$ randomoji 5
:congratulations: :hatching_chick: :trollface: :large_orange_diamond: :meat_on_bone: copied to clipboard
```
