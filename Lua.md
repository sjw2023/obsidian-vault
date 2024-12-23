# Syntax
## 
# String
- Immutable
## Declare
``` lua
someString = [[ .... sting will be placed here ... ]]
stringAllocation = " string can be plced in the double quote"
stringSinglequote = 'string can be placed in the single quote'
```

## Auto convert
``` lua
print("10" + 1) ---> 11
print("Hello" + 1) ---> ERROR
print("10"*"2") ---> 20
```

## Concatenation
``` lua
print(10 .. 20) ---> 1020
```

## Becareful
``` lua
10 == "10" ---> false
```
Even if the Lua automatically converts the string to integer vice versa above statement will always result in false. 

## Converting number string
``` lua
n = tonumber(line)
if n == nil then
	print( line .. " is not valid number")
end
```

If you try to convert none number string to number it will return nil.

## Convert number to string
``` lua
tostring(10)
10 + ""
```

# Tables
- Associative array
	- Can be indexed with not only number, but also with strings or any other value of the language.
- No fixed size
- Object such as dynamically allocated array

## Constructor expresssion
``` lua
a = {}
```
## Indexing
``` lua
k = 'x'
a[k] = 10
```
Put new element 10 into array with key of 'x'

## Reference
``` lua
a = {}
a["x"] = 10
b = a -- b refers to the same table as a
print(b["x"]) ---> 10
b["x"] = 20
print(a["x"]) ---> 20
a = nil -- now only be still refers to the table
b = nil -- there are no references left to the table
```
When there are no refereces to a table left, Lua memory  management will eventually delete the table and reuse its memory.

## Elements in table
- Each element can be indexed with different type.
## Table as record
- To represent record element in the table can be indexed with dot
``` lua
a.x = 10
```

## ipairs()
``` lua
ipairs(a)
```
- built in function of lua which iterates over the elements of the array.

## Indexing with auto converting
``` lua
i = 10 ; j = "10" ; k = "+10"
a[i] = "some value"
a[j] = "another value"
a[k] = "third value"
```
- all of the above are different


# Logical operator
- and
	- returns first argument if it is false
- or
	- returns first argument if it is not false
- not
	- always returns true or false
``` lua
x = x or v
```
equals
``` lua
if not x then x = v end
```

## Useful idiom
``` lua
(a and b) or c 

-- equals to

a and b or c 

-- since and has a higher precedence than or, and this is equavalent to 

a ? b : c
```

## Concatenation
``` lua
print("Hello" .. "World") ---> HelloWorld
print(1 .. 0) ---> 10
-- concatenation automatically converts the number to string
-- it always creates new string, without modifying to its operands
```

## Precedence
Lua has below priority among the operators.


```
^
not
* /
+ -
..
< > <= >= ~= ==
and
or
```

## Table Constructors
https://www.lua.org/pil/3.6.html

# Statements
## Assignment


``` lua
-- single assign

a = "Hello" .. "world"
t.n = 6.n + 1

-- swapping

a, b = 10, 2*x
x, y = y, x

-- discarding
a, b, c = 0, 1 ---> 0  1  nil
a, b = a+1, b+1, b+2 ---> b+2 is ignored

-- multiple returning function
a,b = f()
```
## Local Variables and Blocks
Except the global variables Lua has another type of variable, local variable.
``` lua
x = 10
local  i = 1 --   local to the chunk

while i <= x do 
	local x = i*2 -- local to the while body
	print(x)
	i = i + 1
end

if i > 20 then
	local x -- local to the then body
	x = 20
	print(x + 2)
else
	print(x) ---> 10 (the global one)
end

print(x) ---> 10 (the global one)
```
- local variable benefits user with its fast speed
``` lua
local foo = foo
```
The above is common statement in the Lua which creates local variable foo and initialize it with global variable foo's value. This is useful when the chunk needs to preserve the original  value of foo even after some other function mutate the value of global variable foo
``` lua
do
	local a2 = 2*a
	local b = 3
end
```
With above way you can limit the scope of local  in the do blocks

## Control Structures
``` lua
if condition then statement elseif condition then statement else statement end
while condition do statement end
repeat statement until condition

```

### Numeric for
``` lua

```

- [ ] https://www.lua.org/pil/4.3.4.htmljjkkjjjkkjkjkj




