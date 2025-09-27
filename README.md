# Bill of Material Base for Dependencies
All used external Java via Maven dependencies are listed here.
External dependencies for Java via Maven are only allowed to be imported over this repository and
without overriding the given version, if reasonable possible.

This BOM makes it easier to update dependencies for all projects and
also makes it easier to understand what external dependencies are present.

It also avoids most commits in the main code repos,
that are needed to update all dependencies.
Thereby it reduces the noise in the program code repos.
# Migration to Maven 4

The packaging type BOM is not used, as it is discouraged by Maven for internal project
\[[1](https://maven.apache.org/whatsnewinmaven4.html#New_packaging_type.3A_bom)\]
\[[2](https://github.com/apache/maven/issues/10841)\].
BOM packaging could actually be used for that,
but the Maven community does not want to use it,
as [some errors in the BOM are more likely to happen this way than in other POMs](https://issues.apache.org/jira/browse/MNG-8009).
The problem seems to arise from the fact,
that BOMs are more likely than other POMs to not correctly state their Maven plugin dependencies,
as BOMs are most of the time the root POM for all other POMs of multi project modules.
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
This is a code duplication, which creates an additional maintenance burden,
because some are missed.
Furthermore, there were not so many dependencies present and
therefore not so many updates were needed.
The amount of update commits, was thus considered to be ok for the BOM repo at the moment.

Splitting the BOM repo into 2 is considered a good thing in of itself,
but as fo 2024-10-06 the cost were considered too high in relation to the benefits.
If this tradeoff is looked at differently in the future, it is encouraged to execute the split.
Note, that update commits can be removed from this repo,
without breaking the history.

This changed as of 2025-01-12, as it was found out, that the split was not as costly as previously thought.
Therefore, there are now the projects `net.splitcells.network.bom.base` and `net.splitcells.network.bom` (=log project).