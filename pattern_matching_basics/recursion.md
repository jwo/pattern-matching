---
# This section is used to configure this lesson on Newline.
# `token` can not be changed; however, the rest of the
# information can be edited as needed. Changes you make
# here will overwrite the existing content on Newline
# when you push to the master branch of this path's GitHub repo.

# Begin the body of the lesson below the final `---`.

token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJjb250ZW50X2lkIjoxNzgyOSwiY29udGVudF90eXBlIjoiTGVzc29uIn0.XA1EmXef-KfNPYSxF_SiNlGQfXpsy6IBddOV6KPF3co

# Everything below this line can be edited.
title: >-
  Recursion, ion, n
description: >-
  recursion, recursion
---

### Pattern Matching helps with recursion.

The example below uses recursion to add up items in a list. (And yes, you
_could_ use iteration or `inject` or a number of tools to do so).

But if you do recursion in Ruby, you generally have to consider things like the
state which continues to recurse (?) and the state that stops the recursion.

It can lead to difficult to read code.

```ruby
#meta: runnable
def add_things_up_like_inject(numbers, total)
  if numbers.length == 0
    return total
  else
    x = numbers.shift
    return add_things_up_like_inject(numbers, x+total)
  end

end

my_numbers = [1,2,3,4,5]
sum = 0

puts add_things_up_like_inject(my_numbers, sum)
```

[callout-warning]
`add_things_up_like_inject` has to care about both when it's empty (and shouldn't recurse anymore), AND when it's not
[/callout-warning]


### But first, let's talk about head | tail

Head / Tail is a functional programming concept, but you might have used it in
Bash. `head` gives you the top of a "file", `tail` gives you the end.

In functional concepts, head is the first item in a list, and tail is the rest.

```ruby
#meta: runnable
numbers = [1,2,3]
head = numbers.shift
tail = numbers

puts "head: #{head}"
puts "tail: #{tail}"
```

### When it's empty, head is nil, tail is **empty array**

```ruby
#meta: runnable
numbers = []
head = numbers.shift
tail = numbers

puts "head: #{head}"
puts "tail: #{tail}"
```

### If we apply both concepts (pattern matching AND head/tail) we could end up here:

!exercise 109

[callout-cool]
It matches `def sum_list([head | tail], accumulator)` where there's a head/tail and matches `sum_list([], accumulator)` where the first arg is an empty array.
[/callout-cool]


### There are really two functions then, both names `sum_list` but with different signatures.
