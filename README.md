# HolisticWare.DotNetNew.XamarinFormsProjectsStructureTemplate.SDKStyle

HolisticWare.DotNetNew.XamarinFormsProjectsStructureTemplate.SDKStyle

SDK (short) Style template for Xamarin.Forms

## Clone and try

Paste this into terminal:

```bash
export BRANCH="main"
export URL="https://github.com/HolisticWare-Xamarin-Tools/HolisticWare.DotNetNew.XamarinFormsProjectsStructureTemplate.SDKStyle.git"
export DIR="DotNetNew.XamarinFormsProjectsStructureTemplate.SDKStyle"
[ ! -d $DIR ] \
    && \
    git clone \
        --recurse-submodules \
        -j8 \
        --branch $BRANCH \
        $URL \
        $DIR

cd DotNetNew.XamarinFormsProjectsStructureTemplate.SDKStyle
cd source 
dotnet build BuildAllXamarinForms.sln
```

## Status

*   iOS 

    *   does not build (see problems/issues below)

*   Android 

    *   builds

    *   runs

# Features

*   NuGet package source mapping

    *   Works

        *   [./source/NuGet.config](./source/NuGet.config)

    *   https://docs.microsoft.com/en-us/nuget/consume-packages/package-source-mapping



*   `Directory.packages.props` AKA NuGet central package management

    *   in-progress/not-implemented-yet

    *   https://devblogs.microsoft.com/nuget/introducing-central-package-management/

    *   AndroidX sample after merge

        *   https://github.com/xamarin/AndroidX/blob/improvements-20220706-samples-nuget-central-package-management/samples/dotnet/Directory.Packages.props

        *   https://github.com/xamarin/AndroidX/blob/improvements-20220706-samples-nuget-central-package-management/samples/dotnet/Directory.Packages.AX.props

        *   https://github.com/xamarin/AndroidX/blob/improvements-20220706-samples-nuget-central-package-management/samples/dotnet/Directory.Packages.samples.props

    *   TODO: add GPS-FB-MLKit sample after merge

    *   https://www.mytechramblings.com/posts/centrally-manage-nuget-versions/

    
## Problems/Issues

### The type or namespace name does not exist in the namespace `*.Android`

#### Problem

Error:

```
./source/BuildAllXamarinForms/BuildAllXamarinForms.Android/MainActivity.cs(120,120): 
Error CS0234: 
The type or namespace name 
    'Content' 
does not exist in the namespace 
    'BuildAllXamarinForms.Android' 
(are you missing an assembly reference?) (CS0234) (BuildAllXamarinForms.Android)
```

due to `.Android` suffix and convetional defaults in SDK style projects.

#### [Re]Solution / Workaround

Rename `.Android` project to `.XamarinAndroid`