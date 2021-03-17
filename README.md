# How-to-Check-Static-and-Dynamic-Framework
One simple command to check whether the compiled framework is static or Dynamic (Precompiled Frameworks)


Source :- https://stackoverflow.com/a/61027434/10422074

### Steps:- 

It is simple determine when a file extension is explicit

.a - static library
.dylib - dynamic library

you can use file command.

```
file /some_path/<framework_name>.framework/<framework_name>

//possible results
current ar archive random library //static library
dynamically linked shared library //dynamic library
```

For Example :-

1. Open Terminal where yor all precompiled framework are.

2. I am Checking for "FBSDKCoreKit.framework" 

3. I will write below command in termial 

```
file FBSDKCoreKit.framework/FBSDKCoreKit
```
4. The result would comeout like this

```
FBSDKCoreKit.framework/FBSDKCoreKit: Mach-O universal binary with 4 architectures: [i386:Mach-O dynamically linked shared library i386] [x86_64] [arm_v7] [arm64]
FBSDKCoreKit.framework/FBSDKCoreKit (for architecture i386):	Mach-O dynamically linked shared library i386
FBSDKCoreKit.framework/FBSDKCoreKit (for architecture x86_64):	Mach-O 64-bit dynamically linked shared library x86_64
FBSDKCoreKit.framework/FBSDKCoreKit (for architecture armv7):	Mach-O dynamically linked shared library arm_v7
FBSDKCoreKit.framework/FBSDKCoreKit (for architecture arm64):	Mach-O 64-bit dynamically linked shared library arm64

```

5. This indicates that above Framework is Dynamic.

#### Note :- If you find any static precompiled framework then don't "embed & sign" it in "Framweworks,Libraries & Embedded Content" general tab or your project . 
