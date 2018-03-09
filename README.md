Name
====

lua-resty-unicode - This library provides the mutual conversion of Unicode and UTF-8.

Table of Contents
=================

* [Name](#name)
* [Status](#status)
* [Synopsis](#synopsis)
* [Require](#require)

Status
======

This library is production ready.

Require
=======
* bit library
1. Download from [LuaBitOp](http://bitop.luajit.org/download.html) and compile.
2. Or you can use the 'bit.so' provided by the library itself 

Synopsis
========
```lua
local unicode = require "unicode"

-- unicode to utf-8
print(unicode.decode('\\u0041'))    -- A

-- support url-encode: '%u'
print(unicode.decode('%u0041'))     -- A

-- support mixing
print(unicode.decode('s\\u0065l\\u0065ct * fr%u006fm'))  -- select * from

-- A variety of encoding text
print(unicode.decode('%u0045%u006e%u0067%u006c%u0069%u0073%u0068'))
print(unicode.encode('English'))

print(unicode.decode('\\u6c49\\u5b57'))
print(unicode.encode('??'))
print(unicode.decode('\\u6f22\\u5b57'))
print(unicode.encode('??'))

print(unicode.decode('\\u0440\\u0443\\u0441\\u0441\\u043a\\u0438\\u0439\\u0020\\u0020\\u0442\\u0435\\u043a\\u0441\\u0442'))
print(unicode.encode('???????  ?????'))

print(unicode.decode('\\u0628\\u0627\\u0644\\u0639\\u0631\\u0628\\u064a\\u0629'))
print(unicode.encode('????????'))
```

```bash
A
A
select * from
English
\u0045\u006e\u0067\u006c\u0069\u0073\u0068
??
\u6c49\u5b57
??
\u6f22\u5b57
???????  ?????
\u0440\u0443\u0441\u0441\u043a\u0438\u0439\u0020\u0020\u0442\u0435\u043a\u0441\u0442
????????
\u0628\u0627\u0644\u0639\u0631\u0628\u064a\u0629
```