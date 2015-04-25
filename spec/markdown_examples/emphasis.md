# Inline Formatting test for emphasis
## Simple feature test

**bold**

*italic*

`code`

`verbatim`

*underline*

~~strikethrough~~

[http://www.bing.com](http://www.bing.com)

[http://www.google.com](http://www.google.com)

http://www.gmail.com

[helpful text link](http://www.xkcd.com)

[http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg)

![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png)

[http://www.google.com](http://www.google.com)

## All together in one line

**bold** *italic* `code` `verbatim` *underline*  ~~strikethrough~~ [http://www.bing.com](http://www.bing.com) [http://www.google.com](http://www.google.com) http://www.gmail.com [helpful text link](http://www.xkcd.com) [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png) [http://www.google.com](http://www.google.com)

## Within code test

```
emphasis_tests = [
"*bold*",
"/italic/",
"=code=",
"~verbatim~",
"_underline_ ",
"+strikethrough+",
"[[http://www.bing.com]]",
"[[http://www.google.com]]",
"[[http://www.xkcd.com][helpful text link]]",
"[[http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg]]",
"[[http://www.xkcd.com][http://imgs.xkcd.com/comics/t_cells.png]]",
"<http://www.google.com>",
]

all = emphasis_tests.map do |a|
  emphasis_tests.map do |b|
    [b, ' ', a, ' ', b, "\n\n"].join('')
  end
end

all.each {|e| puts e}
```

## Mixed together test

```
emphasis_tests = ["*","/","=","~","_","+"]

all = emphasis_tests.map do |a|
  emphasis_tests.map do |b|
    [[a, 'Answer: ', b, '42', b, ' ',a, "\n\n"].join(''),
     [a, 'Answer: ', b, '42', b, '',a, "\n\n"].join('')].flatten
  end
end

all.each {|e| puts e}
```

**Answer: *42** *

**Answer: *42***

*Answer: *42* *

**Answer: /42/**

*Answer: `42` *

**Answer: =42=**

*Answer: `42` *

**Answer: ~42~**

*Answer: *42* *

**Answer: _42_**

*Answer: ~~42~~ *

**Answer: +42+**

/Answer: **42** /

*Answer: *42**

*Answer: /42* /

*Answer: /42/*

/Answer: `42` /

*Answer: =42=*

/Answer: `42` /

*Answer: ~42~*

/Answer: *42* /

*Answer: _42_*

/Answer: ~~42~~ /

*Answer: +42+*

=Answer: **42** =

`Answer: *42*`

=Answer: *42* =

`Answer: /42/`

`Answer: =42` =

`Answer: =42=`

=Answer: `42` =

`Answer: ~42~`

=Answer: *42* =

`Answer: _42_`

=Answer: ~~42~~ =

`Answer: +42+`

~Answer: **42** ~

`Answer: *42*`

~Answer: *42* ~

`Answer: /42/`

~Answer: `42` ~

`Answer: =42=`

`Answer: ~42` ~

`Answer: ~42~`

~Answer: *42* ~

`Answer: _42_`

~Answer: ~~42~~ ~

`Answer: +42+`

_Answer: **42** _

*Answer: *42**

_Answer: *42* _

*Answer: /42/*

_Answer: `42` _

*Answer: =42=*

_Answer: `42` _

*Answer: ~42~*

*Answer: _42* _

*Answer: _42_*

_Answer: ~~42~~ _

*Answer: +42+*

+Answer: **42** +

~~Answer: *42*~~

+Answer: *42* +

~~Answer: /42/~~

+Answer: `42` +

~~Answer: =42=~~

+Answer: `42` +

~~Answer: ~42~~~

+Answer: *42* +

~~Answer: _42_~~

~~Answer: +42~~ +

~~Answer: +42+~~

## Multiline support test :: one line

```
emphasis_tests = ["*","/","=","~","_","+"]

all = emphasis_tests.map do |a|
  emphasis_tests.map do |b|
    [a, 'Starting the line here ', "\n", b, 'and continuing here to close', b, a, "\n\n"].join('')
  end
end

all.each {|e| puts e}
```

**Starting the line here
*and continuing here to close***

**Starting the line here
/and continuing here to close/**

**Starting the line here
=and continuing here to close=**

**Starting the line here
~and continuing here to close~**

**Starting the line here
_and continuing here to close_**

**Starting the line here
+and continuing here to close+**

*Starting the line here
*and continuing here to close**

*Starting the line here
/and continuing here to close/*

*Starting the line here
=and continuing here to close=*

*Starting the line here
~and continuing here to close~*

*Starting the line here
_and continuing here to close_*

*Starting the line here
+and continuing here to close+*

`Starting the line here
*and continuing here to close*`

`Starting the line here
/and continuing here to close/`

`Starting the line here
=and continuing here to close=`

`Starting the line here
~and continuing here to close~`

`Starting the line here
_and continuing here to close_`

`Starting the line here
+and continuing here to close+`

`Starting the line here
*and continuing here to close*`

`Starting the line here
/and continuing here to close/`

`Starting the line here
=and continuing here to close=`

`Starting the line here
~and continuing here to close~`

`Starting the line here
_and continuing here to close_`

`Starting the line here
+and continuing here to close+`

*Starting the line here
*and continuing here to close**

*Starting the line here
/and continuing here to close/*

*Starting the line here
=and continuing here to close=*

*Starting the line here
~and continuing here to close~*

*Starting the line here
_and continuing here to close_*

*Starting the line here
+and continuing here to close+*

~~Starting the line here
*and continuing here to close*~~

~~Starting the line here
/and continuing here to close/~~

~~Starting the line here
=and continuing here to close=~~

~~Starting the line here
~and continuing here to close~~~

~~Starting the line here
_and continuing here to close_~~

~~Starting the line here
+and continuing here to close+~~

## Multiline support test :: two lines

```
emphasis_tests = ["*","/","=","~","_","+"]

all = emphasis_tests.map do |a|
  emphasis_tests.map do |b|
    [a, 'Starting the line here ', "\n", b, 'and continuing here', "\n", 'to close', b, a, "\n\n"].join('')
  end
end

all.each {|e| puts e}
```

*Starting the line here
**and continuing here
to close***

*Starting the line here
/and continuing here
to close/*

*Starting the line here
=and continuing here
to close=*

*Starting the line here
~and continuing here
to close~*

*Starting the line here
_and continuing here
to close_*

*Starting the line here
+and continuing here
to close+*

/Starting the line here
*and continuing here
to close*/

/Starting the line here
*and continuing here
to close/*

/Starting the line here
=and continuing here
to close=/

/Starting the line here
~and continuing here
to close~/

/Starting the line here
_and continuing here
to close_/

/Starting the line here
+and continuing here
to close+/

=Starting the line here
*and continuing here
to close*=

=Starting the line here
/and continuing here
to close/=

=Starting the line here
`and continuing here
to close=`

=Starting the line here
~and continuing here
to close~=

=Starting the line here
_and continuing here
to close_=

=Starting the line here
+and continuing here
to close+=

~Starting the line here
*and continuing here
to close*~

~Starting the line here
/and continuing here
to close/~

~Starting the line here
=and continuing here
to close=~

~Starting the line here
`and continuing here
to close~`

~Starting the line here
_and continuing here
to close_~

~Starting the line here
+and continuing here
to close+~

_Starting the line here
*and continuing here
to close*_

_Starting the line here
/and continuing here
to close/_

_Starting the line here
=and continuing here
to close=_

_Starting the line here
~and continuing here
to close~_

_Starting the line here
*and continuing here
to close_*

_Starting the line here
+and continuing here
to close+_

+Starting the line here
*and continuing here
to close*+

+Starting the line here
/and continuing here
to close/+

+Starting the line here
=and continuing here
to close=+

+Starting the line here
~and continuing here
to close~+

+Starting the line here
_and continuing here
to close_+

+Starting the line here
~~and continuing here
to close+~~

## Together in same paragraph test

**bold** **bold** **bold**

*italic* **bold** *italic*

`code` **bold** `code`

`verbatim` **bold** `verbatim`

*underline*  **bold** *underline*

~~strikethrough~~ **bold** ~~strikethrough~~

[http://www.bing.com](http://www.bing.com) **bold** [http://www.bing.com](http://www.bing.com)

[http://www.google.com](http://www.google.com) **bold** [http://www.google.com](http://www.google.com)

[helpful text link](http://www.xkcd.com) **bold** [helpful text link](http://www.xkcd.com)

[http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) **bold** [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg)

![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png) **bold** ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png)

[http://www.google.com](http://www.google.com) **bold** [http://www.google.com](http://www.google.com)

**bold** *italic* **bold**

*italic* *italic* *italic*

`code` *italic* `code`

`verbatim` *italic* `verbatim`

*underline*  *italic* *underline*

~~strikethrough~~ *italic* ~~strikethrough~~

[http://www.bing.com](http://www.bing.com) *italic* [http://www.bing.com](http://www.bing.com)

[http://www.google.com](http://www.google.com) *italic* [http://www.google.com](http://www.google.com)

[helpful text link](http://www.xkcd.com) *italic* [helpful text link](http://www.xkcd.com)

[http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) *italic* [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg)

![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png) *italic* ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png)

[http://www.google.com](http://www.google.com) *italic* [http://www.google.com](http://www.google.com)

**bold** `code` **bold**

*italic* `code` *italic*

`code` `code` `code`

`verbatim` `code` `verbatim`

*underline*  `code` *underline*

~~strikethrough~~ `code` ~~strikethrough~~

[http://www.bing.com](http://www.bing.com) `code` [http://www.bing.com](http://www.bing.com)

[http://www.google.com](http://www.google.com) `code` [http://www.google.com](http://www.google.com)

[helpful text link](http://www.xkcd.com) `code` [helpful text link](http://www.xkcd.com)

[http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) `code` [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg)

![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png) `code` ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png)

[http://www.google.com](http://www.google.com) `code` [http://www.google.com](http://www.google.com)

**bold** `verbatim` **bold**

*italic* `verbatim` *italic*

`code` `verbatim` `code`

`verbatim` `verbatim` `verbatim`

*underline*  `verbatim` *underline*

~~strikethrough~~ `verbatim` ~~strikethrough~~

[http://www.bing.com](http://www.bing.com) `verbatim` [http://www.bing.com](http://www.bing.com)

[http://www.google.com](http://www.google.com) `verbatim` [http://www.google.com](http://www.google.com)

[helpful text link](http://www.xkcd.com) `verbatim` [helpful text link](http://www.xkcd.com)

[http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) `verbatim` [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg)

![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png) `verbatim` ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png)

[http://www.google.com](http://www.google.com) `verbatim` [http://www.google.com](http://www.google.com)

**bold** *underline*  **bold**

*italic* *underline*  *italic*

`code` *underline*  `code`

`verbatim` *underline*  `verbatim`

*underline*  *underline*  *underline*

~~strikethrough~~ *underline*  ~~strikethrough~~

[http://www.bing.com](http://www.bing.com) *underline*  [http://www.bing.com](http://www.bing.com)

[http://www.google.com](http://www.google.com) *underline*  [http://www.google.com](http://www.google.com)

[helpful text link](http://www.xkcd.com) *underline*  [helpful text link](http://www.xkcd.com)

[http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) *underline*  [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg)

![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png) *underline*  ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png)

[http://www.google.com](http://www.google.com) *underline*  [http://www.google.com](http://www.google.com)

**bold** ~~strikethrough~~ **bold**

*italic* ~~strikethrough~~ *italic*

`code` ~~strikethrough~~ `code`

`verbatim` ~~strikethrough~~ `verbatim`

*underline*  ~~strikethrough~~ *underline*

~~strikethrough~~ ~~strikethrough~~ ~~strikethrough~~

[http://www.bing.com](http://www.bing.com) ~~strikethrough~~ [http://www.bing.com](http://www.bing.com)

[http://www.google.com](http://www.google.com) ~~strikethrough~~ [http://www.google.com](http://www.google.com)

[helpful text link](http://www.xkcd.com) ~~strikethrough~~ [helpful text link](http://www.xkcd.com)

[http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) ~~strikethrough~~ [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg)

![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png) ~~strikethrough~~ ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png)

[http://www.google.com](http://www.google.com) ~~strikethrough~~ [http://www.google.com](http://www.google.com)

**bold** [http://www.bing.com](http://www.bing.com) **bold**

*italic* [http://www.bing.com](http://www.bing.com) *italic*

`code` [http://www.bing.com](http://www.bing.com) `code`

`verbatim` [http://www.bing.com](http://www.bing.com) `verbatim`

*underline*  [http://www.bing.com](http://www.bing.com) *underline*

~~strikethrough~~ [http://www.bing.com](http://www.bing.com) ~~strikethrough~~

[http://www.bing.com](http://www.bing.com) [http://www.bing.com](http://www.bing.com) [http://www.bing.com](http://www.bing.com)

[http://www.google.com](http://www.google.com) [http://www.bing.com](http://www.bing.com) [http://www.google.com](http://www.google.com)

[helpful text link](http://www.xkcd.com) [http://www.bing.com](http://www.bing.com) [helpful text link](http://www.xkcd.com)

[http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) [http://www.bing.com](http://www.bing.com) [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg)

![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png) [http://www.bing.com](http://www.bing.com) ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png)

[http://www.google.com](http://www.google.com) [http://www.bing.com](http://www.bing.com) [http://www.google.com](http://www.google.com)

**bold** [http://www.google.com](http://www.google.com) **bold**

*italic* [http://www.google.com](http://www.google.com) *italic*

`code` [http://www.google.com](http://www.google.com) `code`

`verbatim` [http://www.google.com](http://www.google.com) `verbatim`

*underline*  [http://www.google.com](http://www.google.com) *underline*

~~strikethrough~~ [http://www.google.com](http://www.google.com) ~~strikethrough~~

[http://www.bing.com](http://www.bing.com) [http://www.google.com](http://www.google.com) [http://www.bing.com](http://www.bing.com)

[http://www.google.com](http://www.google.com) [http://www.google.com](http://www.google.com) [http://www.google.com](http://www.google.com)

[helpful text link](http://www.xkcd.com) [http://www.google.com](http://www.google.com) [helpful text link](http://www.xkcd.com)

[http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) [http://www.google.com](http://www.google.com) [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg)

![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png) [http://www.google.com](http://www.google.com) ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png)

[http://www.google.com](http://www.google.com) [http://www.google.com](http://www.google.com) [http://www.google.com](http://www.google.com)

**bold** [helpful text link](http://www.xkcd.com) **bold**

*italic* [helpful text link](http://www.xkcd.com) *italic*

`code` [helpful text link](http://www.xkcd.com) `code`

`verbatim` [helpful text link](http://www.xkcd.com) `verbatim`

*underline*  [helpful text link](http://www.xkcd.com) *underline*

~~strikethrough~~ [helpful text link](http://www.xkcd.com) ~~strikethrough~~

[http://www.bing.com](http://www.bing.com) [helpful text link](http://www.xkcd.com) [http://www.bing.com](http://www.bing.com)

[http://www.google.com](http://www.google.com) [helpful text link](http://www.xkcd.com) [http://www.google.com](http://www.google.com)

[helpful text link](http://www.xkcd.com) [helpful text link](http://www.xkcd.com) [helpful text link](http://www.xkcd.com)

[http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) [helpful text link](http://www.xkcd.com) [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg)

![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png) [helpful text link](http://www.xkcd.com) ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png)

[http://www.google.com](http://www.google.com) [helpful text link](http://www.xkcd.com) [http://www.google.com](http://www.google.com)

**bold** [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) **bold**

*italic* [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) *italic*

`code` [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) `code`

`verbatim` [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) `verbatim`

*underline*  [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) *underline*

~~strikethrough~~ [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) ~~strikethrough~~

[http://www.bing.com](http://www.bing.com) [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) [http://www.bing.com](http://www.bing.com)

[http://www.google.com](http://www.google.com) [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) [http://www.google.com](http://www.google.com)

[helpful text link](http://www.xkcd.com) [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) [helpful text link](http://www.xkcd.com)

[http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg)

![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png) [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png)

[http://www.google.com](http://www.google.com) [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) [http://www.google.com](http://www.google.com)

**bold** ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png) **bold**

*italic* ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png) *italic*

`code` ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png) `code`

`verbatim` ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png) `verbatim`

*underline*  ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png) *underline*

~~strikethrough~~ ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png) ~~strikethrough~~

[http://www.bing.com](http://www.bing.com) ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png) [http://www.bing.com](http://www.bing.com)

[http://www.google.com](http://www.google.com) ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png) [http://www.google.com](http://www.google.com)

[helpful text link](http://www.xkcd.com) ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png) [helpful text link](http://www.xkcd.com)

[http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png) [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg)

![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png) ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png) ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png)

[http://www.google.com](http://www.google.com) ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png) [http://www.google.com](http://www.google.com)

**bold** [http://www.google.com](http://www.google.com) **bold**

*italic* [http://www.google.com](http://www.google.com) *italic*

`code` [http://www.google.com](http://www.google.com) `code`

`verbatim` [http://www.google.com](http://www.google.com) `verbatim`

*underline*  [http://www.google.com](http://www.google.com) *underline*

~~strikethrough~~ [http://www.google.com](http://www.google.com) ~~strikethrough~~

[http://www.bing.com](http://www.bing.com) [http://www.google.com](http://www.google.com) [http://www.bing.com](http://www.bing.com)

[http://www.google.com](http://www.google.com) [http://www.google.com](http://www.google.com) [http://www.google.com](http://www.google.com)

[helpful text link](http://www.xkcd.com) [http://www.google.com](http://www.google.com) [helpful text link](http://www.xkcd.com)

[http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) [http://www.google.com](http://www.google.com) [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg)

![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png) [http://www.google.com](http://www.google.com) ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png)

[http://www.google.com](http://www.google.com) [http://www.google.com](http://www.google.com) [http://www.google.com](http://www.google.com)

## Together within a table

| **bold** **bold**                                                        | *italic* **bold**                                                        | `code` **bold**                                                        | `verbatim` **bold**                                                        | *underline*  **bold**                                                        | ~~strikethrough~~ **bold**                                                        | [http://www.bing.com](http://www.bing.com) **bold**                                                        | [http://www.google.com](http://www.google.com) **bold**                                                        | [helpful text link](http://www.xkcd.com) **bold**                                                        | [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) **bold**                                                        | ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png) **bold**                                                        | [http://www.google.com](http://www.google.com) **bold**                                                        |
| **bold** *italic*                                                      | *italic* *italic*                                                      | `code` *italic*                                                      | `verbatim` *italic*                                                      | *underline*  *italic*                                                      | ~~strikethrough~~ *italic*                                                      | [http://www.bing.com](http://www.bing.com) *italic*                                                      | [http://www.google.com](http://www.google.com) *italic*                                                      | [helpful text link](http://www.xkcd.com) *italic*                                                      | [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) *italic*                                                      | ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png) *italic*                                                      | [http://www.google.com](http://www.google.com) *italic*                                                      |
| **bold** `code`                                                        | *italic* `code`                                                        | `code` `code`                                                        | `verbatim` `code`                                                        | *underline*  `code`                                                        | ~~strikethrough~~ `code`                                                        | [http://www.bing.com](http://www.bing.com) `code`                                                        | [http://www.google.com](http://www.google.com) `code`                                                        | [helpful text link](http://www.xkcd.com) `code`                                                        | [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) `code`                                                        | ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png) `code`                                                        | [http://www.google.com](http://www.google.com) `code`                                                        |
| **bold** `verbatim`                                                    | *italic* `verbatim`                                                    | `code` `verbatim`                                                    | `verbatim` `verbatim`                                                    | *underline*  `verbatim`                                                    | ~~strikethrough~~ `verbatim`                                                    | [http://www.bing.com](http://www.bing.com) `verbatim`                                                    | [http://www.google.com](http://www.google.com) `verbatim`                                                    | [helpful text link](http://www.xkcd.com) `verbatim`                                                    | [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) `verbatim`                                                    | ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png) `verbatim`                                                    | [http://www.google.com](http://www.google.com) `verbatim`                                                    |
| **bold** *underline*                                                   | *italic* *underline*                                                   | `code` *underline*                                                   | `verbatim` *underline*                                                   | *underline*  *underline*                                                   | ~~strikethrough~~ *underline*                                                   | [http://www.bing.com](http://www.bing.com) *underline*                                                   | [http://www.google.com](http://www.google.com) *underline*                                                   | [helpful text link](http://www.xkcd.com) *underline*                                                   | [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) *underline*                                                   | ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png) *underline*                                                   | [http://www.google.com](http://www.google.com) *underline*                                                   |
| **bold** ~~strikethrough~~                                               | *italic* ~~strikethrough~~                                               | `code` ~~strikethrough~~                                               | `verbatim` ~~strikethrough~~                                               | *underline*  ~~strikethrough~~                                               | ~~strikethrough~~ ~~strikethrough~~                                               | [http://www.bing.com](http://www.bing.com) ~~strikethrough~~                                               | [http://www.google.com](http://www.google.com) ~~strikethrough~~                                               | [helpful text link](http://www.xkcd.com) ~~strikethrough~~                                               | [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) ~~strikethrough~~                                               | ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png) ~~strikethrough~~                                               | [http://www.google.com](http://www.google.com) ~~strikethrough~~                                               |
| **bold** [http://www.bing.com](http://www.bing.com)                                           | *italic* [http://www.bing.com](http://www.bing.com)                                           | `code` [http://www.bing.com](http://www.bing.com)                                           | `verbatim` [http://www.bing.com](http://www.bing.com)                                           | *underline*  [http://www.bing.com](http://www.bing.com)                                           | ~~strikethrough~~ [http://www.bing.com](http://www.bing.com)                                           | [http://www.bing.com](http://www.bing.com) [http://www.bing.com](http://www.bing.com)                                           | [http://www.google.com](http://www.google.com) [http://www.bing.com](http://www.bing.com)                                           | [helpful text link](http://www.xkcd.com) [http://www.bing.com](http://www.bing.com)                                           | [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) [http://www.bing.com](http://www.bing.com)                                           | ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png) [http://www.bing.com](http://www.bing.com)                                           | [http://www.google.com](http://www.google.com) [http://www.bing.com](http://www.bing.com)                                           |
| **bold** [http://www.google.com](http://www.google.com)                                         | *italic* [http://www.google.com](http://www.google.com)                                         | `code` [http://www.google.com](http://www.google.com)                                         | `verbatim` [http://www.google.com](http://www.google.com)                                         | *underline*  [http://www.google.com](http://www.google.com)                                         | ~~strikethrough~~ [http://www.google.com](http://www.google.com)                                         | [http://www.bing.com](http://www.bing.com) [http://www.google.com](http://www.google.com)                                         | [http://www.google.com](http://www.google.com) [http://www.google.com](http://www.google.com)                                         | [helpful text link](http://www.xkcd.com) [http://www.google.com](http://www.google.com)                                         | [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) [http://www.google.com](http://www.google.com)                                         | ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png) [http://www.google.com](http://www.google.com)                                         | [http://www.google.com](http://www.google.com) [http://www.google.com](http://www.google.com)                                         |
| **bold** [helpful text link](http://www.xkcd.com)                                             | *italic* [helpful text link](http://www.xkcd.com)                                             | `code` [helpful text link](http://www.xkcd.com)                                             | `verbatim` [helpful text link](http://www.xkcd.com)                                             | *underline*  [helpful text link](http://www.xkcd.com)                                             | ~~strikethrough~~ [helpful text link](http://www.xkcd.com)                                             | [http://www.bing.com](http://www.bing.com) [helpful text link](http://www.xkcd.com)                                             | [http://www.google.com](http://www.google.com) [helpful text link](http://www.xkcd.com)                                             | [helpful text link](http://www.xkcd.com) [helpful text link](http://www.xkcd.com)                                             | [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) [helpful text link](http://www.xkcd.com)                                             | ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png) [helpful text link](http://www.xkcd.com)                                             | [http://www.google.com](http://www.google.com) [helpful text link](http://www.xkcd.com)                                             |
| **bold** [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) | *italic* [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) | `code` [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) | `verbatim` [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) | *underline*  [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) | ~~strikethrough~~ [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) | [http://www.bing.com](http://www.bing.com) [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) | [http://www.google.com](http://www.google.com) [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) | [helpful text link](http://www.xkcd.com) [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) | [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) | ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png) [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) | [http://www.google.com](http://www.google.com) [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) |
| **bold** ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png)                       | *italic* ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png)                       | `code` ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png)                       | `verbatim` ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png)                       | *underline*  ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png)                       | ~~strikethrough~~ ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png)                       | [http://www.bing.com](http://www.bing.com) ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png)                       | [http://www.google.com](http://www.google.com) ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png)                       | [helpful text link](http://www.xkcd.com) ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png)                       | [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png)                       | ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png) ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png)                       | [http://www.google.com](http://www.google.com) ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png)                       |
| **bold** [http://www.google.com](http://www.google.com)                                       | *italic* [http://www.google.com](http://www.google.com)                                       | `code` [http://www.google.com](http://www.google.com)                                       | `verbatim` [http://www.google.com](http://www.google.com)                                       | *underline*  [http://www.google.com](http://www.google.com)                                       | ~~strikethrough~~ [http://www.google.com](http://www.google.com)                                       | [http://www.bing.com](http://www.bing.com) [http://www.google.com](http://www.google.com)                                       | [http://www.google.com](http://www.google.com) [http://www.google.com](http://www.google.com)                                       | [helpful text link](http://www.xkcd.com) [http://www.google.com](http://www.google.com)                                       | [http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg](http://farm7.static.flickr.com/6078/6084185195_552aa270b2.jpg) [http://www.google.com](http://www.google.com)                                       | ![http://imgs.xkcd.com/comics/t_cells.png](http://imgs.xkcd.com/comics/t_cells.png) [http://www.google.com](http://www.google.com)                                       | [http://www.google.com](http://www.google.com) [http://www.google.com](http://www.google.com)                                       |
