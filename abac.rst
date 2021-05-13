
ABAC Security rules
===================

.. contents:: The table of contents

General concepts
----------------

*ABAC* means attribute based access control. It is used to set certain rules to identify what objects are available to some user depending on his attributes. 

You can find more information about how you can set up rules in the documentation of a particular service

Default rules
-------------
* Only the authorized user can access the resource
* Only the project owner, members or administrators have access to this project

Syntax description
------------------

ABAC Syntax is pretty simple once you start working with it

Logical operators and grouping
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Resolving if *any*

::

    {
       or: [ {obj.owner: sbj.id}, {obj.type: "public"} ]
    }

Resolving if *all*

::

    {
       and: [ {sbj.role: "admin"}, {obj.type: "private"} ]
    }


**and is a default operator** so can be skipped in most cases:

::

  {
     sbj.role: "admin",
     obj.type: "private"
  }

Comparison operators
~~~~~~~~~~~~~~~~~~~~
Equality (default operator):

::

  {
     obj.type: "active"            # Mean  obj.type == "active"
  }

Not-Equality:

::

  {
     sbj.role: {not: "manager"}    # Mean  sbj.role != "manager"
  }

Lower & Greater:

::

  {
     ctx.total: {lt: 1000},        # Mean  ctx.total < 1000
     obj.ballance: {gt: 1000}      # Mean  obj.ballance > 1000
  }


In set / any of:

::

  {
     sbj.role: {in: ["supervisor", "reviewer"]}    # Mean  sbj.role ∈ {"supervisor", "reviewer"}
  }
