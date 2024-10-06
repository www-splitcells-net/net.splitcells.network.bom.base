# Bill of Material for Dependencies
All used external Java via Maven dependencies are listed here.
External dependencies for Java via Maven are only allowed to be imported over this repository and
without overriding the given version, if reasonable possible.

This BOM makes it easier to update dependencies for all projects and
also makes it easier to understand what external dependencies are present.

It also avoids most commits in the main code repos,
that are needed to update all dependencies.
Thereby it reduces the noise in the program code repos.
# No BOM Log as of 2024-10-06
It was attempted to split this BOM repo, but this attempt was aborted.
The base BOM repo was supposed to have all dependencies and
would only contain commits, that change, which dependencies are used.
The log BOM repo would only contain commits,
that update the versions.

The structure was as following:
The base BOM repo, was a standard BOM repo.
The log BOM repo had the base repo as a parent

In general, it would have worked,
but the fundamental problem found during the attempt was,
that every dependency etc. has to be placed in the base BOM and the log BOM project.
This is a code duplication, which creates an additional maintenance burden.
Furthermore, there were not so many dependencies present and
therefore not so many updates were needed.
The amount of update commits, was thus considered to be ok for the BOM repo at the moment.

Splitting the BOM repo into 2 is considered a good thing in of itself,
but as fo 2024-10-06 the cost were considered too high in relation to the benefits.
If this tradeoff is looked at differently in the future, it is encouraged to execute the split.
Note, that update commits can be removed from this repo,
without breaking the history.