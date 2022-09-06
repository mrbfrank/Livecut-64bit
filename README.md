# Livecut 64-bit

Livecut 64-bit community builds.

Original 32-bit code open sourced by [mdsp](https://github.com/mdsp/Livecut) &amp; updated to 64-bit by fellow Livecutters around the globe.

The purpose of this project is to build, test, & provide 64-bit releases of Livecut.

<!-- Do not submit plugin bugs/issues here. Any bugs/issues should be submitted to the fork of Livecut you are using. Feel free to discuss JUCE & VST_SDK build issues here. -->

### Project structure

Right now all dependencies are manually installed @ `./third_party` & `./vendor`. This will probably change if/when I decide between using git submodules, subtrees, or [subrepo](https://github.com/ingydotnet/git-subrepo)s.

### Livecut 64-bit forks

Install Livecut 64-bit forks @ these paths:

[./third_party/eventual_recluse/Livecut-GUI](https://github.com/eventual-recluse/Livecut-GUI)

[./third_party/scheffle/Livecut](https://github.com/scheffle/Livecut)

### Vendor dependencies

Install JUCE & VST SDK @ these paths:

[./vendor/JUCE 7.0.2](https://github.com/juce-framework/JUCE/releases/tag/7.0.2)

[./vendor/JUCE 6.1.6](https://github.com/juce-framework/JUCE/releases/tag/6.1.6)

[./vendor/VST_SDK](https://www.steinberg.net/vst3sdk)

### Build eventual-recluse/Livecut-GUI AU

```
open ./vendor/JUCE\ 7.0.2/Projucer.app
```

Click sign-in & enable GPL mode

Open `./third_party/eventual_recluse/Livecut-GUI/Livecut.juicer`

Add Xcode exporter

Click "Save and open in IDE"

Configue build for Debug or Release @ menu `Product > Scheme > Edit Scheme... > Run > Info > Build Configuration`

Configure build for Universal Binary 2 @ menu `Product > Destination > Build > Any Mac (Apple Silicon, Intel)`

Click ▶ to start build

Click heels 3x whilst chanting "There's no place like Cornwall"

Immerse yourself in [early 2000's Texas rave culture](https://www.ravemedia.net/texas-rave-pictures/)

Share `./third_party/eventual-recluse/Livecut-GUI/Builds/MacOSX/build/Release/Livecut.component` with your friends

Throw a party in a field near your town

### Build scheffle/Livecut VST3

```
rm -rf ./third_party/scheffle/Livecut/build
mkdir ./third_party/scheffle/Livecut/build
cd ./third_party/scheffle/Livecut/build
cmake -DCMAKE_BUILD_TYPE=RELEASE -Dvst3sdk_SOURCE_DIR=../../../../vendor/VST_SDK/vst3sdk ../VST3/
echo "BNDL????" > "VST3/RELEASE/Livecut.vst3/Contents/PkgInfo"
cmake --build . --config Release
lipo -archs ./VST3/RELEASE/Livecut.vst3/Contents/MacOS/Livecut
```
