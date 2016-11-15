---
# This section is used to configure this lesson on Newline.
# `token` can not be changed; however, the rest of the
# information can be edited as needed. Changes you make
# here will overwrite the existing content on Newline
# when you push to the master branch of this path's GitHub repo.

# Begin the body of the lesson below the final `---`.

token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJjb250ZW50X2lkIjoxNzgyNywiY29udGVudF90eXBlIjoiTGVzc29uIn0.ZW2W49s2pJpHVa_PNVn_InG0OD24TWEYILHoEU1qw_0

# Everything below this line can be edited.
title: >-
  Assignment becomes Matching
description: >-
  Matching
---

### The concept of assignment is generally one of the first things we learn in programming

[callout-info]
Take whatever is on the right of the assignment operator `=` and assign to the left
[/callout-info]

```ruby
#meta: runnable
x = 5
x = x + 1
puts x
```

### In Elixir, the `=` is known instead as the "matching" operator

[callout-info]
So we can assign what an operation returns to its result **if** it matches
[/callout-info]

!exercise 107

[callout-warning]
Try changing `{:ok, number} = {:ok, 5}` to `{:ok, number} = {:error, 5}`.
[/callout-warning]

### Only `number` is a variable, so it couldn't **match** on `:ok`  and `:error`
