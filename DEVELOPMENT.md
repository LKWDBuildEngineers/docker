# Development

## Setup

Clone this repo

```bash
git clone git@github.com:game-ci/docker.git 
```

Change directory to clone directory

```bash
cd docker
```

Build the base image

```bash
docker build base -t base
```

Build hub

```bash
docker build hub -t hub
```

Build editor

```bash
docker build editor -t editor
```

Remote into image:
```bash
docker run -it --rm -v "/Users/kishan.ambasana/Perforce/kishan.ambasana_NOT-LAP-MBP-01088_3504/AvakinLife/Feature_Branches/LifeClient_Upgrade_2019.4":"/project" editor:latest bash

```

Run Project:
```bash
cd /project
unity-editor \
  -nographics \
  -logfile /dev/stdout \
  -quit \
  -projectPath . \
  -buildTarget "android" \
  -executeMethod ExternalBuildProcess.BuildAndroid
  -buildVersion "$VERSION" \
  -androidVersionCode "$ANDROID_VERSION_CODE" \
  -androidKeystoreName "$ANDROID_KEYSTORE_NAME" \
  -androidKeystorePass "$ANDROID_KEYSTORE_PASS" \
  -androidKeyaliasName "$ANDROID_KEYALIAS_NAME" \
  -androidKeyaliasPass "$ANDROID_KEYALIAS_PASS" \
  $CUSTOM_PARAMETERS

```
