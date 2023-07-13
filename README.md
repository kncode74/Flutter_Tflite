# old
# เรียนเชื่อม Tensorflow lite with Flutter
- เริ่มทำ วันที่ 12 /7 /2566
- ทำได้ วันที่ 13/7/2566 เวลา 2.15
## ปัญหาที่พบก็คือ เยอะมาก
1. API Pub dev :tflite: ^1.1.2
   - error : ![image](https://github.com/kncode74/Flutter_Tflite/assets/69451462/34861471-c96f-49ca-a20b-8bed96962131)
   - solution : E:\flutter.pub-cache\hosted\pub.dartlang.org\tflite-1.1.2\android\build.gradle There change the dependencies at the end to

            dependencies {
                implementation 'org.tensorflow:tensorflow-lite:+'
                implementation 'org.tensorflow:tensorflow-lite-gpu:+'
            }

2. edit build gradle :

      android {
   
          compileSdkVersion 33
          ndkVersion flutter.ndkVersion
          androidResources {
              noCompress 'tflite'
          }
          compileOptions {
              sourceCompatibility JavaVersion.VERSION_1_8
              targetCompatibility JavaVersion.VERSION_1_8
          }
      
          kotlinOptions {
              jvmTarget = '1.8'
          }
      
          sourceSets {
              main.java.srcDirs += 'src/main/kotlin'
          }
          aaptOptions {
              noCompress 'tflite'
              noCompress 'lite'
          }
      
          defaultConfig {
              // TODO: Specify your own unique Application ID (https://developer.android.com/studio/build/application-id.html).
              applicationId "com.example.old"
              // You can update the following values to match your application needs.
              // For more information, see: https://docs.flutter.dev/deployment/android#reviewing-the-build-configuration.
              minSdkVersion 19
              targetSdkVersion 30
              versionCode flutterVersionCode.toInteger()
              versionName flutterVersionName
              multiDexEnabled true
          }

![image](https://github.com/kncode74/Flutter_Tflite/assets/69451462/a4824854-a7df-4580-873e-4ef659810a62)
