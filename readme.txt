installation step by step:
1.install nvm
2.install nodejs > 9.0
3.npm install -g react-native-cli
4.project folder: yarn install
5.project folder: yarn add babel-plugin-transform-decorators-legacy
6.project folder: react-native link

run on simulator(android might be not work):
android:react-native run-android
ios:react-native run-ios

run on real device:

android:
1.adb reverse tcp:8081 tcp:8081
2.run app on androidstudio

ios:
1.change the project signature to the valid apple developer account
2.run app on xcode

package bundle for release:
react-native bundle --entry-file index.js --platform ios --dev false --bundle-output ios/main.jsbundle --assets-dest ios
react-native bundle --platform android --dev false --entry-file index.js --bundle-output android/app/src/main/assets/index.android.bundle --assets-dest android/app/src/main/res/

Release on IDE:
for ios:
1.change schema to "release"
2.AppDelegate.m: change jsCodeLocation to Production
3.build archive and export
for android:
1.setup sign cert file
2.gradle build