# Xcode 11.4 Regression LibTool
When building this Lib with Archiving in Xcode there is a regression with libtool.

Error from build log:
```
/Applications/Xcode-beta.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/bin/libtool: object: /Users/mariuslandwehr/Library/Developer/Xcode/DerivedData/Networking-bigwxlvidtfvckeysbasqxuzfojq/Build/Intermediates.noindex/ArchiveIntermediates/Networking/BuildProductsPath/Release/CGRPCZlib.o malformed object (string table at offset 0 with a size of 8, overlaps Mach-O headers at offset 0 with a size of 160)
/Applications/Xcode-beta.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/bin/libtool: object: /Users/mariuslandwehr/Library/Developer/Xcode/DerivedData/Networking-bigwxlvidtfvckeysbasqxuzfojq/Build/Intermediates.noindex/ArchiveIntermediates/Networking/BuildProductsPath/Release/CNIOLinux.o malformed object (string table at offset 0 with a size of 8, overlaps Mach-O headers at offset 0 with a size of 160)
/Applications/Xcode-beta.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/bin/libtool: object: /Users/mariuslandwehr/Library/Developer/Xcode/DerivedData/Networking-bigwxlvidtfvckeysbasqxuzfojq/Build/Intermediates.noindex/ArchiveIntermediates/Networking/BuildProductsPath/Release/CGRPCZlib.o malformed object (string table at offset 0 with a size of 8, overlaps Mach-O headers at offset 0 with a size of 160)
/Applications/Xcode-beta.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/bin/libtool: object: /Users/mariuslandwehr/Library/Developer/Xcode/DerivedData/Networking-bigwxlvidtfvckeysbasqxuzfojq/Build/Intermediates.noindex/ArchiveIntermediates/Networking/BuildProductsPath/Release/CNIOLinux.o malformed object (string table at offset 0 with a size of 8, overlaps Mach-O headers at offset 0 with a size of 160)
Command Libtool failed with a nonzero exit code
```

## Steps to Reproduce
1. Clone the repository
2. Open the Networking.xcodeproj
3. Archive the static library
4. Build Error on linking libNetworking.a

## Expected Behaviour
1. Archive the static library
2. Build Succeeded

## Additional Notes
This is also failing on Xcode Beta 11.5 Beta 2
