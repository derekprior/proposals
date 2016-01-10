# Up And Down Again: A Migration's Tale

## Abstract

You run `rake db:migrate` and `rake db:schema:load` regularly, but what do they
*actually* do? How does `rake db:rollback` automatically reverse migrations and
why can't it reverse all of them? How can you teach these tasks new tricks to
support additional database constructs?

We'll answer all of this and more as we explore the world of schema management
in Rails through the lens of Scenic, a gem that brings database view support to
Rails.

You will leave this talk with a deep understanding of how Rails manages schema,
a better idea of its pitfalls, and ready to bend it to your will.

## Details

Rails schema management was designed 10 years ago to support a tiny subset of
SQL constructs that were widely supported across relational databases and has
changed little since then. Databases are far more powerful than ActiveRecord
lets on, and for those familiar with SQL it's not long before we yearn to wield
that power.

We'll learn to add methods to migrations, make those migration methods
reversible, and make new SQL objects survive a round trip to and from
`schema.rb`. This process is undocumented but in this talk, you'll discover what
it takes as together we walk through each of those steps and discuss the design
decisions they entail.

You will also learn the dangers in extending schema in this manner. The process
remains undocumented because it is technically considered private API, despite
the fact that gems that extend schema generation are quite popular.

We'll close by considering why so many SQL constructs remain officially
unsupported, how we can improve that story, and what a public API for schema
extensions might look like.

An Early Outline:

* Limitations of Rails’ migration and schema systems. This is frustrating when
  developers know that the database supports a feature but can't easily use it
  with Rails.
* Tour of migrations, recording, schema dumping, and schema loading and how
  Scenic hooks into them.
* Discuss reasons these database features haven't been supported by Rails
  yet, and what that means for developers whose primary experience with
  databases is through Rails.

## Pitch

The internals of Rails migrations are convoluted but we're fresh from digging
into this for Scenic. We know the secrets and the pitfalls and have even worked
with the Rails team to expose more public APIs in this area.

Our experiences as maintainers of several gems that extend Rails functionality
also gives us insight into what a truly supported and maintainable schema
extension API might may look like in the future of Rails.
