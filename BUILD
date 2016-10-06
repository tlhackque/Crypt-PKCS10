To build a distribution kit:

Clone the git repository & cd to it

Make any changes.

Make sure any executables are marked properly in the index:
  git update-index --chmod +x file

Commit any changes.

Install Dist::Zilla from CPAN (has many dependencies, takes a LONG time)
Install Dist::Zilla::Plugin::CopyFilesFromBuild
Install Dist::Zilla::Plugin::MetaProvides::Package
Install Dist::Zilla::Plugin::MinimumPerl
Install Dist::Zilla::Plugin::Run
Install Dist::Zilla::Plugin::Signature # If you plan to sign your distributions.
                                       # Otherwise, comment-out the [Signature] in dist.ini
Install Pod::Readme

Update the version number in lib/PKCS10.pm
Make any README changes in lib/PKCS10.pm
Update copyrights.

Update Changes

Update dist.ini [Encoding] if any new binary file types are packaged.

Run build:
  dzil build

The output is Crypt-PKCS10-<version>/ and .tar.gz
README, Commitlog, LICENSE, Makefile.PL, MANIFEST, META.* are auto-generated by the build.

Test the distribution:
  dzil test

Check to make sure that no extra files were included - update dist.ini if so.
  tar -tzf <dist>.tgz | less
  Note that build doesn't empty the build directory (a Dist::Zilla bug)

To Release
 dzil release --trial
or
 dzil release

This will make a few changes, including updating the README and in META updating the release type.

Commit those changes as "Release version ..."

Tag that commit.

Note that the Commitlog (file) in the distribution is never committed to git.
