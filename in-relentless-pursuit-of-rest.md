# In Relentless Pursuit of REST

## Abstract

"That's not very RESTful." As a Rails developer you've probably heard or even
spoken that proclamation before, but what does it really mean? What's so great
about being RESTful anyway?

RESTful architecture can narrow the responsibilities of your Rails controllers
and make follow-on refactorings more natural. In this talk, you'll learn to
refactor code to follow RESTful principles and to identify the positive
impact those changes have throughout your application stack.

## Details

REST is an architecture for the web that encourages modeling your application as
a collection of resources upon which actions can be performed. Rails developers
too-frequently conflate the resources spoken of by REST and the ActiveRecord
models in their application.

There's a noticeable jump in the quality of a Rails developer's work when they
come to understand that a their controllers do not have to map one-to-one to
their models. You are free to present a resource in your application that is
derived from several models or even derived from none of them. Similarly, the
same ActiveRecord model can be presented in different ways, exposing different
actions, as differently-named resources.

In this talk we'll discuss this idea and see through examples how pursuing it
aggressively can simplify our applications. For example, by taking the leap from
`post "orders#cancel"` to `post "orders/cancellation#create"`, we will better
follow a RESTful architecture, have routes that more succinctly and clearly
define what our application does, and even be left with a logical place to move
our cancellation business logic. This is better RESTful design leading logically
to better object-oriented design as well.

## Pitch

There are a good number of developers who hear, "That's not very RESTful" and
aren't really sure what that means in their code. I've taught teams to
aggressively pursue RESTful Rails applications and watched as follow-on
refactorings become clear and the language of their application improves.
