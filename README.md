# HolisticWare.DotNetNew.XamarinFormsProjectsStructureTemplate.SDKStyle


HolisticWare.DotNetNew.XamarinFormsProjectsStructureTemplate.SDKStyle




```
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