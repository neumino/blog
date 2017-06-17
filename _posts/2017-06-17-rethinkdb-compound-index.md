---
layout: post
category : Geek
tags : [rethinkdb, index]
title: Fast select and ordering with RethinkDB
---
{% include JB/setup %}

I often get questions about [ReQL](https://github.com/rethinkdb/rethinkdb) on
how to select all the documents that match a given value and order them by
another.

### Solution with an example.

Suppose your schema for the table `user` is:
```js
{
  id: <string>,
  country: <string>,
  score: <number>
}
```

And that you want all the users in the `US` ordered by they score. The quick way to do it is
```js
r.table('user').indexCreate('country_score', function(user) {
  return [user('country'), user('score')]
})
```

```js
r.table('user').between(
  ['US', r.minval],
  ['US', r.maxval],
  {index: 'country_score'}
).orderBy({index: 'country_score'})
```


### Explanation

Let's start with a bit of background on what an index is. When you build an
index, you basically build a tree with the indexed value (and a pointer to your
document). For example, you may have the following tree

```
                 ['FR', 7]
               /           \
       ['FR', 2]           ['US', 8]
         /  \                 /  \
 ['CA', 2]  ['FR', 5]  ['US', 2] ['ZA', 8]
```

When you request `between(['US', r.minval], ['US', r.maxval], {index: 'country_score'}`,
you extract the subtree

```
     ['US', 8]
       /
['US', 2]
```

This subtree still represent a proper index on a subset of your table. If your
table had only these two documents, this would be the tree representing your
index. You can therefore reuse it to order your keys. Because you filtered the
elements to have country to be `US`, you basically just order by the second field, that is
to say `score.`

### Why you can't order by another index

I'm also asked why can't we just have
```
r.table('score').getAll('US', {index: 'country'}).orderBy({index: 'score'})
```

The main reason is that `getAll` would return you a subtree where all the keys
are `US`. Each node would also give you a pointer to the document saved in the
database. But then the index `score` is a whole different tree where the keys
are just the score, so you cannot extract a subtree with the retrieved documents
without scanning the whole index first, which is more or less equivalent to
selecting without an index.

Hopefully this helps a bit understanding what indexes are, how they are used
and what are their limitations.
