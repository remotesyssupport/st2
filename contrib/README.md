Contrib
=======

* st2/contrib/core -> Location of St2 contents that will be shipped with the product.  These contents will be copied over to /opt/stackstorm on install and then auto-registered.  Users are expected to be able to edit these contents post install.

* st2/contrib/examples -> Location of St2 samples that may be of interest to the users.  These samples will be shipped with the product but will not be auto-registered.

* st2/contrib/sandbox -> Location of contents that are still in development but not shipped with the product.

* st2/contrib/sandbox/packages/<SomePackageName> -> Location of self contained packages that are in development but not shipped with the product. The <SomePackageName> is a directory with an arbitrary name given to the package (i.e. st2/contrib/sandbox/packages/correlation). File system structure for each package should the same as a normal repo structure with sensors, rules, and actions directories.
