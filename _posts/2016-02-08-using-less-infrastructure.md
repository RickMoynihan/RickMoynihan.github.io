---
layout: post
title: Less infrastructure
---

When making decisions that introduce new infrastructure or services,
you should always stop for a moment to reconsider.  It's tempting to
believe you should adopt something new and shiny to solve your
problem, because it's "the right tool for the job, and Twitter used it
to scale!".

Infrastructure however, comes with an inevitable cost of
ownership, and as a developer infrastructure dependencies are some of
the hardest to manage.  You have to keep the services running on your
laptop, or remember to launch them on demand to test your app; and if
you frequently work on different projects context switching between
environments can become very wasteful of your time.  Not to mention,
in production, you need new scripts to deploy, monitor and manage that
service; and lets not forget the tedium that goes with editing
opaque configuration files.

Whenever you're tempted to add a new piece of infrastructure resist
the urge for a moment, and think about the pain developers will go
through trying to setup their development or production environments.

It's important to remember that external services and infrastructure
no-matter how stateless and cool they claim to be, always introduce
incidental mutable state in the form of their availability, their
configuration and their version.  A symptom which leads to developers
wasting time wondering why their tests are failing, because they
misconfigured a service, forgot to start it, or need to upgrade it to
a newer (or older) version.

Think about the pain of new logs to parse for errors, and new service
boundaries and error conditions to handle and ask yourself if there is
a way you can live without it?  Will your already underutilised
database not be able to back your job queue, and do you really need
that queueing service at all?

Software developers love taking the axe to their code; and appreciate
the value of deleting code, as no code has no maintainance cost, or
zero defects.  However it's less common to hear about people removing
infrastructure entirely.  Much of this is just the self affirming
nature of the hackernews echo chamber, where everyone wants to be an
expert in something new but *if* you can replace the need for a piece
of infrastructure with a sufficiently small amount of code the
tradeoff might well be worth it.

In applying this maxim you need to remember that using less
infrastructure isn't a virtue in its own right, as you're always best
using the right amount of something; not too much and not too little.
Maxim's might help guide your judgement, but good design is always
about considering the trade offs behind our decisions; and no maxim
should ever substitute thinking entirely.

With this caveat in mind however, all other things being equal, the
principles of parsimony, mean less infrastructure is better than more.
