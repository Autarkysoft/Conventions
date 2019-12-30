# Versioning convention
The versioning convention is a modified form of Semantic Versioning 2.0.0 found [here](https://semver.org/).

Versions consist of 4 numbers `Major.Minor.Build.Revision`. 
Depending on the complete version, each number could be treated differently.

### A quick note about Revision
All compiled releases will be published always with only 3 first numbers set and the last (Revision) set to `0`.  
The first change made in source code after the release will change Revision to `1` and it will remain non-zero until 
the next release that will change it back to zero again before compiling. Note that there is no need to continue 
incrementing Revision.  
The point is that when the source code at the head of master branch is compiled the result could give an easy indication 
that it is a user compiled code not an official released version.  
Example: Autarkysoft.Cryptocurrency.dll  
Released version `3.1.5.0`  
First change `3.1.5.1`  
Continue development without release `3.1.6.1`  
Released version `3.1.6.0`  


## Explanation of each version
### 0.0.0.0 <= Version < 0.1.0.0
Version 0 is the pre-release or preview version of the code. 
If the code is released to public but it is not ready for use the version starts from `0.0.0.0`. 
* Major and Minor both remain 0 during this stage.
* Since there is no releases there is no need to increment the version with each change. But only Build could be incremented 
to indicate big changes.
* In this stage everything can change and there will be no backward compatibility in most cases. 
* No compiled version of the code will be released during this time.  

### 0.1.0.0 <= Version < 1.0.0.0
Version `0.1.0.0` marks the first beta release of the code. 
And it means code is stable enough for use but may contain some bugs, lack some less important features 
and future releases may not be backward compatible.
* Major version will remain 0.
* Minor version is incremented each time a big change is made (may or may not be backward compatible).
* Build version is incremented each time there is a small change such as bug fix.
* Revision version is as explained on top.
* During beta backward compatibility may or may not be kept.
* Most things can change
  * Names of: namespaces, classes, methods, properties,...
  * Location of classes,...
  * Storage formats (example: a different serialization for wallet file stored on disk)

### Version >= 1.0.0.0
Version `1.0.0.0` marks the first stable release. 
From this point forward there will be an extra focus on keeping backward compatibility even when a new Major version is released.
* Major version is incremented when "major" structural changes are made that may or may not break compatibility. 
* If compatibility with old versions is broken an explicit warning must be given to users.
* Minor version is incremented when a functionality is added in a backwards compatible manner,
* Build version is incremented each time there is a small change such as bug fix.
* Revision version is as explained on top.
