![Stride](sources/data/images/Logo/stride-logo-readme.png)

Created with the latest stride repo to include a shortcut to access post processing effects in graphics compositor.

Building from source
Prerequisites
Latest Git with Large File Support selected in the setup on the components dialog.
Visual Studio 2022 with the following workloads:
.NET desktop development with .NET Framework 4.7.2 targeting pack
Desktop development with C++ with
Windows 10 SDK (10.0.18362.0) (it's currently enabled by default but it might change)
MSVC v143 - VS2022 C++ x64/x86 build tools (v14.30) or later version (should be enabled by default)
C++/CLI support for v143 build tools (v14.30) or later version (not enabled by default)
Optional (to target UWP): Universal Windows Platform development with
Windows 10 SDK (10.0.18362.0) or later version
MSVC v143 - VS2022 C++ ARM build tools (v14.30) or later version (not enabled by default)
Optional (to target iOS/Android): Mobile development with .NET and Android SDK setup (API level 27) individual component, then in Visual Studio go to Tools > Android > Android SDK Manager and install NDK (version 19+) from Tools tab.
FBX SDK 2019.0 VS2015
Build Stride
Open a command prompt, point it to a directory and clone Stride to it: git clone https://github.com/stride3d/stride.git
Open <StrideDir>\build\Stride.sln with Visual Studio 2022 and build Stride.GameStudio (it should be the default startup project) or run it from VS's toolbar.
Optionally, open and build Stride.Android.sln, Stride.iOS.sln, etc.
Build Stride without Visual Studio
Install Visual Studio Build Tools with the same prerequisites listed above
Add MSBuild's directory to your system's PATH (ex: C:\Program Files (x86)\Microsoft Visual Studio\2022\BuildTools\MSBuild\Current\Bin)
Open a command prompt, point it to a directory and clone Stride to it: git clone https://github.com/stride3d/stride.git
Navigate to /Build with the command prompt, input msbuild /t:Restore Stride.sln then compile.bat
If building failed:

If you skipped one of the Prerequisites thinking that you already have the latest version, update to the latest anyway just to be sure.
Visual Studio might have issues properly building if an anterior version is present alongside 2022. If you want to keep those version make sure that they are up to date and that you are building Stride through VS 2022.
Your system's PATH should not contain older versions of MSBuild (ex: ...\Microsoft Visual Studio\2019\BuildTools\MSBuild\Current\Bin should be removed)
Some changes might require a system reboot, try that if you haven't yet.
Make sure that Git, Git LFS and Visual Studio can access the internet.
Close VS, clear the nuget cache (in your cmd dotnet nuget locals all --clear), delete the hidden .vs folder inside \build and the files inside bin\packages, kill any msbuild and other vs processes, build the whole solution then build and run GameStudio.
Do note that test solutions might fail but it should not prevent you from building Stride.GameStudio.
