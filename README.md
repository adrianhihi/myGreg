### Summary
The goal of this challenge is to create a simple version of `grep`, which we shall refer to as `mygrep`. 

If you are unfamiliar with `grep`, it is a command line tool for finding files that contain a particular string. Your implementation, `mygrep`, will be a command line tool with a similar interface but fewer features.

You'll have 40 minutes to work on this question.

### Spec
The interface for `mygrep` is as follows:
```shell
> ./mygrep [query] [path]
```
In other words, `mygrep` takes two arguments. The first argument `[query]` is the string that we are searching for. The second argument `[path]` is the path of the folder from which we will begin our search. Note that the path may be either relative or absolute.

The output of this command is a list of lines which contain the query as a substring. `mygrep` should search through all files which are descendants of `[path]`. Each line of output must be of the form:
```
/path/to/file:linenum	the entire text of the matched line
```
Note that `/path/to/file` must be an absolute path, that `linenum` must be 1-indexed, and that there is exactly one tab character (an actual tab character `"\t"`) before the text of the matched line. The matched line itself should be stripped of whitespace on both ends (so if the matched line starts with 5 spaces, these spaces should be removed before printing the line).

### Examples

We will be using some short stories as our source text. Download the short stories with following commands:
```shell
curl -sL https://github.com/qualialabs/grep-stories/archive/master.zip -o stories.zip \
&& unzip stories.zip \
&& mv grep-stories-master stories
```
You should now have a directory named `stories`. For the sake of simplicity, the following examples assume that the absolute path to `stories` is `/src/stories` and that your `mygrep` script is located in `/src`.

**Example 1**
```
> ./mygrep exceedingly stories
/src/stories/a-dark-brown-dog.txt:147	their casual approach often exasperated them exceedingly. They used to gain a
/src/stories/1908/jack-london/to-build-a-fire.txt:4	Day had broken cold and grey, exceedingly cold and grey, when the man turned
```
**Example 2**
```
> ./mygrep never stories/poe
/src/stories/poe/the-tell-tale-heart.txt:12	none. I loved the old man. He had never wronged me. He had never given me
/src/stories/poe/the-tell-tale-heart.txt:15	it. Whenever it fell upon me, my blood ran cold; and so by degrees--very
/src/stories/poe/the-tell-tale-heart.txt:23	I was never kinder to the old man than during the whole week before I killed
/src/stories/poe/tales-of-mystery-and-imagination/the-cask-of-amontillado.txt:24	vintages myself, and bought largely whenever I could.
/src/stories/poe/tales-of-mystery-and-imagination/the-cask-of-amontillado.txt:30	was so pleased to see him that I thought I should never have done wringing his
/src/stories/poe/tales-of-mystery-and-imagination/the-cask-of-amontillado.txt:76	"Let us go, nevertheless. The cold is merely nothing. Amontillado! You have been
```
**Example 3**
```
> ./mygrep former stories
/src/stories/an-occurrence-at-owl-creek-bridge.txt:58	captain; it was now held by that of the sergeant. At a signal from the former
/src/stories/fairy-tales/1845/the-little-match-girl.txt:78	brighter than at noon-day: never formerly had the grandmother been so beautiful
/src/stories/holidays/the-gift-of-the-magi.txt:24	The "Dillingham" had been flung to the breeze during a former period of
/src/stories/three-wishes/the-monkeys-paw.txt:10	chess; the former, who possessed ideas about the game involving radical chances,
```

### Rules
  * Your implementation of `mygrep` must be callable from the command line.
  * The examples use the syntax `./mygrep`. Here is [an example](https://stackoverflow.com/questions/17592394/how-to-make-a-python-file-run-without-py-extension) on how to make a Python script callable in this way. The process is nearly identical for other languages.
  * You may assume that the input is well-formed.
  * You can use any programming language. 
  * You may use the core libraries of your language of choice, but you may not use 3rd party libraries.
  * You may use the internet as a resource, but do not search for how to solve this exact problem.
  
It is recommended that you complete this challenge with a scripting language. Writing something callable from the command line does not require compiling a binary. That said, use whatever tools you are comfortable with.
