# gobujang
[![](https://jitpack.io/v/gobujang/gobujang.svg)](https://jitpack.io/#gobujang/gobujang)

## 1. Gradle
**Add it in your root build.gradle(project).**
```gradle
allprojects {
    repositories {
        ...
        maven { url 'https://jitpack.io' }
    }
}
```
<p>
<img src="images/a.png" width="700">
</p>

**Add the dependency build.gradle(module).**
```gradle
dependencies {
    ...
    implementation 'com.github.gobujang:gobujang:0.0.1'
}
```
<p>
<img src="images/b.png" width="700">
</p>
 
## 2. Build aar file
**Copy and Paste the aar file to your project's libs folder.**     
**Implementation '[package name]: [file name]: [version code] @aar' build.gradle.**
```gradle
repositories {
    flatDir {
        dirs 'libs'
    }
}

dependencies {
    ...
    implementation 'com.gbj.module.gobujang:gobujang:0.1@aar'
}
```
<p>
<img src="images/c.png" width="700">
</p>    

[Download aar file](download/gobujang_aar.zip)

## 3. Build jar file
**Copy and Paste the jar file to your project's libs folder.**    
**Right-click on the jar file and click the Add As Library... menu.**
<p>
<img src="images/e.png" width="">
</p>

[Download jar file](download/gobujang_jar.zip)

## 4. Referencing a Library Project
**Download gobujang.zip**

[Download gobujang file](download/gobujang.zip)

**Add library module to settings.gradle.**    
**Confirm that the library has been added to the project list.**
```gradle
include ':app',':gobujang'
project(':gobujang').projectDir = new File('downloaded file location')
```
<p>
<img src="images/f.png" width="700">
</p>    

**Compile the library in build.gradle.**
```gradle
dependencies {
    ...
    implementation project(':gobujang')
}
```
<p>
<img src="images/g.png" width="700">
</p>
 
## Usage
**Then** *GobujangManager.init()* **it in onCreate() Method of application class :**
```java
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        GobujangManager.init(context, "appcode");
    }
```
<p>
<img src="images/usage.PNG" width="">
</p>
 
**This method** *GobujangManager.init()* **is used to communicate**     
**between the library's broadcast receiver and the gobujang server application's broadcast receiver.**

## Processing according to result value.
**1. in case of 0 result value, please play the game normally.**   
**this case is the user using our APP without hacking or something.**   
**2. in case of -1 or -2 and no response from server result value, the text dialogue "Play the game in the gobujang application" appears.**   
**if the user click "OK" at this dialogue, gobujang web page will pop up.**   
incase of KOREAN game, popup message or website is KOREAN, JAPAN case popup with japanease. ( please check it )    

**KOREAN**
*"고부장닷컴 앱에서 게임을 실행해주세요."*     
website(KO) https://www.gobujang.com/     

**JAPANESE**
*"GO部長ドットコムのアプリでゲームを実行してください。"*    
website(JP) https://www.gobucho.jp/   

## After the build process
**After the build package is uploaded somewhere (for example, Google Drive), let us know the upload link on our CP page.**
