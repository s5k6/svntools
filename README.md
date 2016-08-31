
SVN Tools
=========

During my time as a university teacher, we have successfully used
[Subversion](http://stefan-klinger.de/www.subversion.apache.org) as
one means to distribute lecture material and, more importantly,
collect student exercise submissions.  A complete description of this
approach is described in [a German language
talk](http://stefan-klinger.de/files/svn_15w.pdf) I've presented for
my fellow lecturers in 2016:

  * In this presentation I demonstrate the use of the SCM software
    Subversion as a tool to manage lectures, and student exercise
    submissions. Based on several years of teaching experience, the
    benefits and caveats are discussed. After a short review of the
    student's expected knowledge, we review the individual workflows
    taking on the perspectives of a student, a tutor, and a
    teacher. This Talk was presented in February 2016.


This git repository contains a collection of three different tools
provided to facilitate routine tasks that came up every semester.


Untangling permissions of a multi-repo server
---------------------------------------------

The Subversion server was set up using svn version 1.6.17, by the
university datacenter staff, and attached to the local authentication
service.  Unfortunately, our group had to maintain access rights for
*all* repositories (10–15) in a single file.  The [`mkaccess`
script](./mkaccess/) is used to facilitate this task and help
around some of themajor pitfalls.


Backup
------

A [backaup strategy](./freezeRepos/) for old SVN repositories cast
into a simple to use shell script.  It stores a dump, the latest
revision and access rights, and a hardcopy of the repo directory.


A pre-commit hook
-----------------

To limit the file types, sizes, and naming conventions students were
allowed to commit, and also privilege some users based on user id or
repositury path, see [`pre-commit` hook](./hooks/)
