# Introduction #

To ensure a consistent user experience, it is important to have a clear process for releasing new versions, and also ensure that the expectations of users are in line with the intentions of the developers.
We've therefore created this version policy to ensure that this process can be as transparent as possible

# Details #

## Version Numbering ##

The initial release number was v1.0.0.  We will follow the convention of using Version.Release.Update - i.e. the first release was Version 1, Release 0, Update 0.

**Update**
  * Bug-fixes, minor enhancements
  * Backward compatibility with the previous release will be maintained
  * Increments by 1 each update (no "even-stable, odd-unstable" strategy)

**Release**
  * Minor version update - new features and enhancements
  * Backward compatibility with the previous release will be maintained where possible
    * No functions removed, but output may change slightly
    * Existing functions may require additional parameters
  * No further updates to the previous Release once this is available

**Version**
  * Major version update - i.e. re-write using a different logic, total change of strategy etc.
  * Backward compatibility is not guaranteed
  * Previous Version will continue to be maintained for a period after a new Version is released

## Branching and Releasing ##

The SVN release process from http://ariejan.net/2006/11/21/svn-how-to-release-software-properly will be roughly followed.

**Release Branches** should be named RB-Version.Release.Update, e.g. RB-1.0.0

**Release Tags** should be named REL-Version.Release.Update, e.g. REL-1.0.0

The SVN bug-fixing process from http://ariejan.net/2006/11/22/svn-how-to-fix-bugs-properly will also be roughly followed.

Bugs should be initially fixed on the appropriate Release Branch, then Merged to HEAD.

**Updates** should start from the Release Branch for the appropriate Release (i.e. RB-1.0.1 would start from RB-1.0.0).

**Releases** should start from the Trunk (i.e. RB-1.1.0 would start from Trunk, not from RB-1.0.x)