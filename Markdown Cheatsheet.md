Markdown interactive website at [**Markdown Tutorial](https://www.markdowntutorial.com)

## Headers 見出し
___
```
# H1
## H2
### H3
#### H4
##### H5
###### H6
```
# H1
## H2
### H3
#### H4
##### H5
###### H6

## Emphasis 強調
___
```
Emphasis(italics): *asterisks* or _underscores_
Strong emphasis(bold): **asterisks** or __underscores__
Combined emphasis: **asterisks and _underscores_**
Strikethrough: ~~Strikethrough~~
```
Emphasis(italics): *asterisks* or _underscores_
Strong emphasis(bold): **asterisks** or __underscores__
Combined emphasis: **asterisks and _underscores_**
Strikethrough: ~~Strikethrough~~

## Paragraphs 段落/改行
___
```
Hard breaks:
Do I contradict myself?
<hard break>
Very well then I contradict myself.

Soft breaks:
Do I contradict myself?··
Very well then I contradict myself.
```
**Hard breaks:**
Do I contradict myself?

Very well then I contradict myself.

**Soft breaks:**
Do I contradict myself?  
Very well then I contradict myself.

## Lists リスト
___
```
Ordered list:
1. First item
2. Second item

Unorder list:
* Use asterisks
- Use minuses
+ Use pluses

Nested list:
1. First item
··* Sub-list
····1. More items
2. Second item··
··indented Sub-text
··* Sub-list
····* More items
```
**Ordered list:**
1. First item
2. Second item

**Unorder list:**
* Use asterisks
- Use minuses
+ Use pluses

**Nested list:**
1. First item
 * Sub-list
    1. More items
2. Second item··
 indented Sub-text
 * Sub-list
    * More items

## Links リンク
___
```
Inline link:
[_Text_](_Link_)
[Visit GitHub!](www.github.com)

Reference link:
Here's [_the first link_][First link].
Here's [_another link_][Another link].
Now back to [_the first link_][First link].
[First link]: www.github.com
[Another link]: www.google.com
```
**Inline link:**
[Visit GitHub!](www.github.com)

**Reference link:**
Here's [_the first link_][First link].
Here's [_another link_][Another link].
Now back to [_the first link_][First link].
[First link]: www.github.com
[Another link]: www.google.com

## Images 画像
___
```
Inline image link:
![_Alt Text_](Link)
![Lion](http://icons.iconarchive.com/icons/google/noto-emoji-animals-nature/96/22222-lion-face-icon.png)

Reference image link:
![_Alt Text_](Defined Link)
[Defined Link]: Link itself

![Orange cat][Orange]
[Orange]:http://icons.iconarchive.com/icons/google/noto-emoji-animals-nature/96/22222-lion-face-icon.png
```
Inline image link:
![Lion](http://icons.iconarchive.com/icons/google/noto-emoji-animals-nature/96/22222-lion-face-icon.png)

Reference image link:
![Orange cat][Orange]
[Orange]:http://icons.iconarchive.com/icons/google/noto-emoji-animals-nature/96/22222-lion-face-icon.png

## Blockquotes 引用
___
```
> An investment in knowledge pays the best interest.
Quote break.
> Education is not only a ladder of opportunity, but it is also an investment in our future.

```
> An investment in knowledge pays the best interest.

> Education is not only a ladder of opportunity, but it is also an investment in our future.

## Tables 表
___
`:` to align
At least three `---` to separate each header cell.
The outer pipes `|` is optoonal.
```
Type 1:
| Tables        | Something     | Something     |
| ------------- |:-------------:| -------------:|
| Left-aligned  | Centered      | Right-alighed |
| 1             | 2             | 3             |
| 4             | 5             | 6             |

Type 2:
Table | Something | Something
:--- | :---: | ---:
Left-aligned | Centered | Right-alighed
_Mix with_ | `other` | **styles**
```
**Type 1:**
| Tables        | Something     | Something     |
| ------------- |:-------------:| -------------:|
| Left-aligned  | Centered      | Right-alighed |
| 1             | 2             | 3             |
| 4             | 5             | 6             |

**Type 2:**
Table | Something | Something
:--- | :---: | ---:
Left-aligned | Centered | Right-alighed
_Mix with_ | `other` | **styles**

## Code and Syntax Highlighting コード
___
```
  Inline code:
  `code`

  ```
  No language
  ```

  ```python
  s = "Python"
  print s
  ```

  ```javascript
  var s = "JavaScript";
  alert(s);
  ```
```
Inline code:
`code`
```
No language
```

```python
s = "Python"
print s
```

```javascript
var s = "JavaScript";
alert(s);
```

## Link to YouTube Videos
___
You can add an image with a link to the video
**inline html**
```
<a href="http://www.youtube.com/watch?feature=player_embedded&v=YOUTUBE_VIDEO_ID_HERE
" target="_blank"><img src="http://img.youtube.com/vi/YOUTUBE_VIDEO_ID_HERE/0.jpg" 
alt="IMAGE ALT TEXT HERE" width="240" height="180" border="10" /></a>
```
or using pure Markdown (losing the image sizing and border)
```
[![IMAGE ALT TEXT HERE](http://img.youtube.com/vi/YOUTUBE_VIDEO_ID_HERE/0.jpg)](http://www.youtube.com/watch?v=YOUTUBE_VIDEO_ID_HERE)
```
<a href="http://www.youtube.com/watch?feature=player_embedded&v=sFC69gKJRis
" target="_blank"><img src="http://img.youtube.com/vi/sFC69gKJRis/0.jpg" 
alt="IMAGE ALT TEXT HERE" width="240" height="180" border="10" /></a>

[![IMAGE ALT TEXT HERE](http://img.youtube.com/vi/sFC69gKJRis/0.jpg)](http://www.youtube.com/watch?v=sFC69gKJRis)