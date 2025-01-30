<hgroup>
<h1>GraphQL Notes</h1>
<p>by <a href="http://reiver.link/">Charles Iliya Krempeaux</a></p>
</hgroup>

---

* Isn't GraphQL more or less just SQL exposed through HTTP? — which is an old idea.
  * <a href="http://reiver.link/"><abbr title="Charles Iliya Krempeaux">Me</abbr></a> and someone else at Electronic Arts (EA) did this back in the year 2013.
  * and <a href="http://reiver.link/"><abbr title="Charles Iliya Krempeaux">I</abbr></a> (also) did this back in 2004.
  * I doubt we were the only ones.
* Could the GraphQL _query_ have been encoded into the URL rather than the HTTP body? — to take advantage of different HTTP features.

---

**GraphQL** is often compared to **REST**.

It is important to point out that when the vast majority of people talk about **REST**, they are **not** talking about what was originally described as "**REST**".

**REST** became a label for most **HTTP APIs**.
Sometimes with the restriction of, requiring that URLs be **nouns**.

Most **HTTP APIs** that were called "REST" were _not_ compliant with the original description.

Therefore, it is disingenuous to compare GraphQL to the original definition of REST, since most people didn't seem to be doing that.

---

* [GraphQL: The Documentary](https://youtu.be/783ccP__No8)

---

* Can GraphQL take advantage of HTTP caching?

---

* [What is GraphQL?](https://hygraph.com/learn/graphql)

---

From [What is GraphQL?](https://hygraph.com/learn/graphql):

> When using REST, you’ll always be returned complete "datasets".

That is **not** acurate.

You can pick-and-choose what you want using regular HTTP APIs.

For example:

`https://api.example.com/v1/users/12345?select=id,name,when_created`

The `select=id,name,when_created` part specifies that only the `id`, `name`, and `when_created` fields should be returned.

---

From [What is GraphQL?](https://hygraph.com/learn/graphql):

>  When using REST [...] If you wanted to request information from x objects, you’d need to perform x REST API requests.

That is **not** accurate.

You can get multiple objects from a single request of a regular HTTP API.

For example:

`https://api.example.com/v1/users?id=12,345,6789`

And just return the objects in the result.

---

You can even combine the two forms mentioned with regular HTTP APIs:

`https://api.example.com/v1/users?id=12,345,6789&select=id,name,when_created`
