#### Issue

In a kotlin multiplatform project, when two kotlin common classes have the same simple name 
but are in different packages, end having the same name when compiled to ObjC with the 
addition of underscores. 

```
For example:
com.example.first.View
com.example.second.View
com.example.third.View

will be compiled in ObjC to:
View
View_
View__
```

#### Steps to reproduce
- clone repo
- run: ```./gradlew linkDebugFrameworkIos```
- check the generated ```build/bin/ios/main/debug/framework/kn_objc_name_conflicts.framework/Headers/kn_objc_name_conflicts.h```

See a checked in version of the headers file [here](generated-headers.h).