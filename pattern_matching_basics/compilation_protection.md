---
# This section is used to configure this lesson on Newline.
# `token` can not be changed; however, the rest of the
# information can be edited as needed. Changes you make
# here will overwrite the existing content on Newline
# when you push to the master branch of this path's GitHub repo.

# Begin the body of the lesson below the final `---`.

token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJjb250ZW50X2lkIjoxNzgzMCwiY29udGVudF90eXBlIjoiTGVzc29uIn0.IymEQc_-peEDFy7WegQ_g0TI6uXfKETw76RxRufcn-Y

# Everything below this line can be edited.
title: >-
  Compilation Protection
description: >-
  No more forgetting about a particuluar path
---

### Most of my code isn't recursion though, so how is this used in REALLIFE™

!exercise 106

[callout-error]
What if we remove the `handle({:error, message_text})` definition and ran it? It wouldn't _even_ compile
[/callout-error]

### This can mean that if you try and use a path that doesn't exist, it won't compile

```elixir
def create(conn, params) do
  case create_your_cool_model(params) do
    {:ok, route} ->
      conn
      |> put_status(201)
      |> render(:show, data: route)
    {:error, changeset} ->
      conn
      |> put_status(422)
      |> render(:errors, data: changeset)
  end
end
```


### Another REALWORLD™ example

Below[^1] will call `check` and see if it is OK to continue the 'content'. Think of it like saying, a contest cannot be cancelled, cannot be finalized, and we cannot currently be past-deadline.

```elixir
defmodule ContestStatus do
  defstruct cancelled: false, finalized: false, past_deadline: false

  def check(%ContestStatus{ cancelled: true }),
    do: :contest_cancelled
  def check(%ContestStatus{ finalized: true }),
    do: :contest_finalized
  def check(%ContestStatus{ past_deadline: true }),
    do: :past_deadline
  def check(%ContestStatus{}), do: :ok

  def past_deadline(nil), do: false
  def past_deadline(date), do: Ecto.DateTime.local > date

  def check(contest) do
    check(%ContestStatus{
      cancelled: contest.cancelled || false,
      finalized: contest.finalized || false,
      past_deadline: past_deadline(contest.picks_deadline)
    })
  end
end
```

[callout-warning]
We've all written the above with nested if/else statments
[/callout-warning]

[^1]: Example taken from [LearningWithJB.com](http://learningwithjb.com/posts/elixir-is-just-cool-an-example-with-pattern-matching-and-structs) which is super-great on getting starting with elixir.
