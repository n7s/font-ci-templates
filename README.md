# font-ci-templates

Just a few basic CI (Continuous Integration) templates for open font projects using [smith](https://github.com/silnrsi/smith) and an open font workflow. (More details on [SIL Font Development Best Practises](http://silnrsi.github.io/FDBP) and [SIL Font Development Notes](https://silnrsi.github.io/silfontdev)).

So far: Travis, Bitbucket, GitLab, GitHub Actions...

When applicable rename .dot to . and drop at the root of your project folder.
(Or in the expected workflow subfolder).  Adjust internal variables as necessary.

There are surely ways to improve the toolchain installation phase, and make things faster with pre-build profiles (docker containers or similar), caching, etc.
More on that later on.

Enjoy.
