## Introduction ##
This is a fork of [original repository for AssimpNet](https://bitbucket.org/Starnick/assimpnet/), the cross-platform .NET wrapper for the Open Asset Import Library (otherwise known as [Assimp](https://github.com/assimp/assimp)), which is a 3D model import-export library. The primary motivation is for this library to power (offline) content pipelines to import and process 3D models into your game engine's internal format, although the wrapper can be used at runtime to enable your users to import custom content. Please see the Assimp website for a full list of supported formats and features. Each version of the managed wrapper tries to maintain parity with the features of the native version.

The fork contains some personal changes that is convenient for my personal purposes.

### Low level ###

* Native methods are exposed via the AssimpLibrary singleton.
* Structures corresponding to unmanaged structures are prefixed with the name **Ai** and generally contain IntPtrs to the unmanaged data.
* Located in the *Assimp.Unmanaged* namespace.

### High level ###

* Replicates the native library's C++ API, but in a way that is more familiar to C# developers.
* Marshaling to and from managed memory handled automatically, all you need to worry about is processing your data.
* Located in the *Assimp* namespace.

## Supported Frameworks ##

The library runs on **.NET Core**.

## Supported Platforms ##

The NuGet package supports the following Operating Systems and Architectures out of the box (located in the *runtimes* folder, under [RID](https://docs.microsoft.com/en-us/dotnet/core/rid-catalog)-specific folders):

* **Windows** 
	* x86, x64 (Tested on Windows 10)
* **Linux**
	* x64 (Tested on Ubuntu 18.04 Bionic Beaver)
* **MacOS**
	* x64 (Tested on MacOS 10.13 High Sierra)

You may have to build and provide your own native binaries for a target platform that is not listed. If the library does not support a platform you are targeting, please let us know or contribute an implementation! The logic to dynamically load the native library is abstracted, so new platform implementations can easily be added.

## Licensing ##

The library is licensed under the [MIT](https://opensource.org/licenses/MIT) license. This means you're free to modify the source and use the library in whatever way you want, as long as you attribute the original authors. The native library is licensed under the [3-Clause BSD](https://opensource.org/licenses/BSD-3-Clause) license. Please be kind enough to include the licensing text file (it contains both licenses).
