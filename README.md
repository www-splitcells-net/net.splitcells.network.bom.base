# Bill of Material for Dependencies
All used external Java via Maven dependencies are listed here.
External dependencies for Java via Maven are only allowed to be imported over this repository and
without overriding the given version, if reasonable possible.

This BOM makes it easier to update dependencies for all projects and
also makes it easier to understand what external dependencies are present.

It also avoids most commits in the main code repos,
that are needed to update all dependencies.
Thereby it reduces the noise in the program code repos.