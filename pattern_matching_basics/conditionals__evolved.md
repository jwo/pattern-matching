---
# This section is used to configure this lesson on Newline.
# `token` can not be changed; however, the rest of the
# information can be edited as needed. Changes you make
# here will overwrite the existing content on Newline
# when you push to the master branch of this path's GitHub repo.

# Begin the body of the lesson below the final `---`.

token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJjb250ZW50X2lkIjoxNzgyOCwiY29udGVudF90eXBlIjoiTGVzc29uIn0.M9_8gcwWhrN5CRGRSaalPuC97CzI0XQEGjf3rV3XbqM

# Everything below this line can be edited.
title: >-
  Conditionals, Evolved
description: >-
  Conditionals are over
---

### After assignment, we generally learn about "control-flow". And we generally learn about If/Else

```ruby
#meta: runnable

names = ["Joe", "Bob", "Henry"]
if names.length === 0
  puts "Empty"
else
  puts names.join(", ")
end

```

### With pattern matching, we can evolve out of conditionals

!exercise 108

[callout-cool]
What this gives us: we can direct out programs to run under certain conditions easier.
[/callout-cool]
