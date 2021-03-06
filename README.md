Samsung Extended Autotools Project Template
===========================================

Brief
-----
SEAPT is a feature rich set of Autotools configuration files and scripts targetting C/C++ projects, with built-in Doxygen and Google Testing Framework. It works only on UNIX systems and casual build does not depend on anything but Shell interpreter and GNU make. SEAPT is [Eclipse CDT](http://www.eclipse.org/cdt/) friendly.

Features
--------
SEAPT is designed entirely on the basis of Autotools stack: aclocal, autoconf, autoheader, automake and libtool. It is much similar to "classic" open source build system (e.g., needs "configure" to be run), but extends it with a Doxygen documentation and Google Test Framework support out of the box, as well as supplies the necessary Eclipse CDT Autotools Project files. SEAPT suggests a development workflow in which Eclipse is used to write the code and the actual build process is completely independent of any IDE. Though Eclipse is not required at all, it enables deep integration with Autotools and is recommended.

Like cmake, SEAPT provides a nicely formatted colored output. It supports building subdirectories in parallel, compiler version checking and much more.

Setup
-----

1. Clone this GitHub project.
2. Execute

```
./init <your desired project name>
```

This script applies the project name to the templates, wipes out the existing Git repository and initializes a new one, with a single initial commit. The project is now completely ready for development. It is merely a skeleton.
3. Configure it only for the first time:

```
./autogen.sh <build directory>
```

OR just import the project into Eclipse CDT with Autotools plugin installed: select File -> Import..., then General -> Existing Projects into Workspace, then set the root directory to the directory where you've just cloned SEAPT and click Finish.
4. Build it:

```
cd build && make -j8
```

OR click the "Hammer" Eclipse button. That's it.

Configuration
-------------
Adding new files, directories, etc. is standard: you must edit Makefile.am-s and configure.ac. The only difference is that one should replace SUBDIRS with PARALLEL_SUBDIRS to enable parallel subdirectories processing. You can refer to [automake](http://www.gnu.org/software/automake/manual/automake.html) and [libtool](http://www.gnu.org/software/libtool/manual/libtool.html) documentation for details. Some frequent use cases will be included in future versions of this README.

You may add custom configuration options. To see the list of predefined options, execute

```
configure --help
```

Doxygen
-------
Documentation is generated by default; disable it with
```
configure --disable-doxygen
```
To change the settings, edit docs/Doxyfile.in and then run ```make``` OR just build in Eclipse.

Currently, there is no way to trigger documentation rebuild on source files' changes except appending dependencies by hand to "doxyfile.stamp" rule in docs/Makefile.am.

Test suite
----------
SEAPT is shipped with it's own embedded copy of Google Testing Framework in tests/google. It is slightly stripped, but can always be synchronized with upstream using the following commands:
```
cd tests/google/src
svn update
cd ../gtest
svn update
```

To run your tests, execute
```
make tests
```
or
```
make check
```
in the root build directory. Each test is allowed to run no longer than 10 seconds. You can override this value by setting TIMEOUT variable during make invocation. SEAPT automatically measures memory consumption and saves the XML results obtained from gtest.

Eclipse
-------
It is recommended to install [ANSI Console](http://www.mihai-nita.net/eclipse/) plugin to see colored build output (anyway, it can be turned off with ```configure --disable-colors```).

SEAPT is released under the Simplified BSD License.
Copyright 2012,2013 Samsung R&D Institute Russia.
