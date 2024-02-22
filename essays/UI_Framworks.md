---
layout: essay
type: essay
title: "UI Frameworks: Good or Bad?"
# All dates must be YYYY-MM-DD format!
date: 2024-02-22
published: true
labels:
  - Bootstrap5
  - HTML/CSS
  - Web Development
---

## Key differences between Bootstrap5 and raw HTML/CSS

Bootstrap5 and CSS are both languages used to style web pages developed with HTML. On the surface level, CSS is native to HTML and may be used without loading additional files unlike Bootstrap. However, their differences run much deeper than this simple feature of how they load. These key differences become apparent in their abstraction level, responsiveness, browser compatibility, and customization.

### Abstraction level

Bootstrap provides predesigned components such as navigation bars, buttons, forms, cards, modals, and more. These components come with predefined styles and behaviors, allowing developers to quickly build consistent and responsive user interfaces. On the other hand, CSS requires developers to define the styles for each element manually. While it offers more flexibility and control over the design, it also requires more time and effort to create and maintain stylesheets from scratch.

### Responsiveness

Bootstrap 5 is designed with mobile-first responsiveness in mind. Its grid system and components are built to adapt to different screen sizes and devices, ensuring a consistent user experience across desktops, tablets, and smartphones. While CSS can also be used to create responsive designs, developers need to write media queries and adjust stylesheets manually to achieve responsiveness.

### Browser compatability

Bootstrap 5 aims to provide consistent behavior and appearance across different web browsers and devices. It handles cross-browser compatibility and vendor-prefixing internally, reducing the need for developers to write browser-specific CSS. CSS requires developers to consider browser compatibility issues and write vendor prefixes for certain CSS properties to ensure consistent rendering across different browsers.

#### Bootstrap across Chrome and IE
##### Chrome

<img width="300px" class="rounded float-start pe-4" src="..img/frameworsk/colorlib_chrome.png">

##### IE

<img width="300px" class="rounded float-start pe-4" src="..img/frameworsk/colorlib_IE.png">

#### CSS across Chrome and IE



### Customization



## My experience

Stack Overflow is an excellent place for having your questions answered by seasoned professionals, but it can also be embarassing if you don't do your due diligence and follow the rules of asking a good question.
Here is an example of a good question, lets examine.

```
Q: Why don't DBMS's support ASSERTION? 

So I recently learned about ASSERTION in my databases course, and my prof noted that major databases don't support it,
even though it is in the SQL-92 standard. I tried googling to find out why, but there doesn't seem to be any discussion on the
topic.

So, why isn't ASSERTION supported by the vast majority of relational database packages? Is it soley a performance
issue or is there something intrinsically hard about it?

If you can, please note any database packages that implement it as well (example: if there's an academic/teaching DB).
Also, why is there so little discussion on the issue; it's not even mentioned in the Wikipedia page for SQL or SQL-92)
But answer the main question first, or answer in comments.

I'm not looking for how to implement it with triggers or anything else.
```
Firstly, the user asking the question titles his question with a clear question in the title which allows readers to easily understand the topic. They then proceed to describe the background for why they are asking the question and explain what they have done before to make sure that the answer has not yet been posted to the web. A couple of further clarifying questions are then posed. Lastly, they give specifics on what they do not want to find out. In short, the user provided directly answerable qustions with adequate background inforamtion and clarifying statements on what they hope to find out. This is clearly a good combination of information because this question got 7 hightly detailed answers.
Here is the top response:

```
There are four levels of constraint: column-level, row-level, table-level and schema-level.

A table-level could, for example, involve a target table other than the source table on which it was declared but only gets
checked when the source table changes. In theory a schema-level constraint would be checked for every change in every table
in the schema but in practise the optimizer would be able to detect changes in a more granular way; consequently, if your
DBMS had support for schema-level constraint then you wouldn't find much use for table-level constraints in practise.

No current SQL product supports schema-level constraints i.e. CREATE ASSERTION. Apparently Rdb did support it when it was
looked after by DEC but that is no longer the case. -- UPDATE: in a private message I was advised that Sybase's SQL Anywhere
supports CREATE ASSERTION but with serious errors that allow such constraints sometimes to be violated!

The only SQL-like product I've used that currently supports subqueries in CHECK constraints, which enables table-level
constraints, is the Access database engine (ACE, Jet, whatever). It has issues, though. First, there is not support for
SQL-92 functionality (or equivalent) to defer constraint checking. Second, table-level constraints are checked for each row
affected, rather than when the statement completes as required by the SQL-92 Standard. Needless to say, the workaround is
very clunky e.g. drop the constraint and in doing so lock the table, execute the update, recreate the constraint. Schema-level
constraints, arguably achievable by adding the same constraint to all the tables it involves, is virtually unworkable.

Possibly for these reasons, the Access Team have never publicized its CHECK constraint functionality at all beyond the initial
announcements for Jet 4.0 (it remains missing from the Access Help, for example). All that said, for intra-table constraints
(e.g. a sequenced key in a valid-state 'history' temporal table) the functionality works well, especially when you consider that
Access only got trigger-like functionality (not SQL based, though) last year.

SQL of course has UNIQUE constraints and referential integrity constraints that are of course table-level but these are special
cases. Therefore, all constraints you will encounter 'in the wild' will be either colum- or row-level.

Do be aware with MySQL that, although using CHECK() in SQL DDL will parse without error, it will have no effect. How users can
tolerate a SQL product with no CHECK constraints at all is beyond me! PostgreSQL has a excellent constraints model, hint hint :)

So why are inter-table constraints so rarely supported? One reason must be due to historical circumstances. As @gbn correctly
identifies (under the title Concurrency), the Sybase/SQL Server family of SQL implementations is based on a model that cannot
cope with inter-table constraint checking and that's not something that is likely to ever change.

Consider looking at this the other way around: if you were creating a SQL product today, would you include CREATE ASSERTION?
If you did, you would certainly have to also implement DEFERRABLE constraints (even though multiple assignment is arguably the
better model). But you would be able to draw on a lot more research and experience if you went down the route of building a
'traditional' optimizer. And perhaps you'd find there is no commercial demand for schema-level constraints (if MySQL can get
anyway without CHECK constraints...) If PostgreSQL doesn't do it, I don't think anyone ever will.

I think the real show stopper is that most industrial-strength products have already developed trigger functionality that allows
 users to write 'constraints' of arbitrary complexity (plus can a lot more e.g. send an email to tell something happened). Sure,
they are procedural rather than declarative, the coder has to do a lot of extra work that the system would take care of with true
constraints, and the performance tends to be not so great. But the fact is they existing in real products today and do provide a
'get out of jail free card' card for vendors. Why should they bother implementing worthy features if customers are not banging the
table for them?

As regards academic/teaching langauges, as @Damien_The_Unbeliever correctly identifies, a Tutorial D CONSTRAINT are always
'schema'-level, hence allow for global constraints of arbitrary conplexity by definition. If you are looking to design your own
DBMS(!!) with this kind of functionality, you should consider implementing the D specification while using an existing SQL DBMS
for storage, as Dataphor have done.

```
 
## A less intelligent question:

The following example shows a user with a very broad, non-specific title. They then proceed to describe a their code without giving any background information or explanation of their due dilligence. The rest of the question has a very entitled tone to it describing how they are sure things are not working for specific reasons instead of asking questions based around curiosity and humility. 

```
Q: “Illegal type synonym family application in instance” with functional dependency

I have a multi-parameter typeclass with a functional dependency:

class Multi a b | a -> b
I also have a simple, non-injective type synonym family:

type family Fam a
I want to write an instance of Multi that uses Fam in the second parameter, like this:

instance Multi (Maybe a) (Fam a)
However, this instance is not accepted. GHC complains with the following error message:

error:
  • Illegal type synonym family application in instance: Fam a
  • In the instance declaration for ‘Multi (Maybe a) (Fam a)’
Fortunately, there is a workaround. I can perform a usual trick for moving a type out of the instance head and into an
equality constraint:

instance (b ~ Fam a) => Multi (Maybe a) b
This instance is accepted! However, I got to thinking, and I started to wonder why this transformation could not be applied
to all instances of Multi. After all, doesn’t the functional dependency imply that there can only be one b per a, anyway? In
this situation, it seems like there is no reason that GHC should reject my first instance.

I found GHC Trac ticket #3485, which describes a similar situation, but that typeclass did not involve a functional dependency,
so the ticket was (rightfully) closed as invalid. In my situation, however, I think the functional dependency avoids the
problem described in the ticket. Is there anything I’m overlooking, or is this really an oversight/missing feature in GHC?
```
This question got no replies and it was asked over 6 years ago. An example of the reader's frustration can be seen in the following comment: 

```
It'd be nice to have a self-contained example to be able to explore hypotheses when trying to answer your question.
```

## Conclusion

Online forums are a blessing for those of us who are inexperienced and are generally stumped by a problem that exceeds our knowlege. This blessing comes at the generosity of other people's time and their willingness to support the broader community. As with any good thing, it can easily be lost when we are complacent and take advantage of the resource. So, for the benefit of everyone, take the time to research your problem extensively and then write a thoughtful, smart question if all else fails. It seems like the lesson in this is: when you put in the initial work yourself, others will be glad to help you get accross the finish line if you trip. 
