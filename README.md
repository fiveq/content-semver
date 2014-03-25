In the beginning, there was regular Semantic Versioning. But it included a
whole bunch of stuff about public APIs that a great many projects we work on at
our agency do not have. Left with a choice of making a pinky swear with each
new developer we hired, or simply wordsmithing Tom Preston-Warner's great idea
into something we could reference internally, we went the latter route.

Benefits to writing things down:

  1. Reference for old salts
  2. Reference for new hires
  3. Reference to settle drinking bets
  4. Sanity in versioning complex content-based projects

Downsides to writing things down:

  1. Now there's a *right way* to do it :(
  2. No more B/S'ing your way through an off-schedule production deployment
  3. More reading

But seriously, the biggest change to this document from version 2.0.0 of
[semver](http://github.com/mojombo/semver) is that we distinguish the reasons
for minor and major iterations using atomic or non-atomic feature additions to
the content and URL structure of the project.

Exampli gratia
--------------

You're at v1.2.10 of a website's codebase. The client asks you to allow the
donation form to accept payments via Stripe instead of Auth.net. 

This would be part of a v1.3 release.

It qualifies as a substantial feature addition, but is atomic, i.e. does not
change ay other aspect of the site or the URL patterns.

----------------------------------------------------------------------------

The current site, v1.1.30 targets Django v1.4, but we are quickly leaving the
maintenance period of this release. Your work to bring the site up to date with
the latest Django release will likely touch a number of components and require
updating 3rd-party library versions as well.

This would be part of a v2.0.0 release.

The changes introduced by the upgrade are non-atmoic, i.e. they touch many
parts of the codebase and could lead to functional changes, as newer version of
Django may deprecate things like generic function-based views.

----------------------------------------------------------------------------

You're at v1.4.0 and the client notes that the registration form you just added
as part of v1.4 isn't working as expected. People try to sign up for the free
sundae party and are instead being cross-registered for the hot dog eating
contest.

This would be part of a v1.4.1 release.

Hopefully you'd have a few more patches to wrap up in that release but if
that's the only one, that's okay too.