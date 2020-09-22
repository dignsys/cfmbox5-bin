# CFMBOX5 Binary : cfmbox5-bin
CFMBOX5 System &amp; Application Binary
릴리즈 된 날짜를 기준으로 별도 Branch로 관리 합니다.
예를 들어 2020년 9월 22일 릴리즈 된 버전은 dev_ds9100_android_20200922 branch를 사용합니다.
DS9100은 CFMBOX5에서 사용하는 메인보드 이름입니다.

## Directory Image-rk3399_box : System image
OTA 방법 방법은 업데이트 파일, 
예를 들어 https://github.com/dignsys/cfmbox5-bin/tree/dev_ds9100_android_20200922/Image-rk3399_box/rk3399_box-ota-100150.zip 을  이동식 USB 저장 장치에 update.zip으로 이름을 변경 하여 저장 합니다.  
그리고 CFMBOX5(DS9100) USB 포트에 물리면 잠시 후에 안내창이 나옵니다.

## Directory apk : Application Binary
APK 파일을 다운로드 하여 USB 메모리 또는 서버에서 업데이트 가능합니다.

## 다양한 DS9100 Android 펌웨어 업데이트 방식  
1. System Imahe Update : update.img, system.img, kerne.img ... *.img
   가) Debug USB OTG, upgrade_tool 사용.

2. System Image Update : OTA  
   가)  adb push ota_XXX.zip /sdcard/update.zip && adb shell sync 하면 OTA 설치 안내 Dialog 나옴  
   나)  이동식 USB 저장 장치에 update.zip을 복사 하고 USB 포트에 결합 하면 OTA 설치 안내 Dialog 나옴  
   다)  We-Manager 에서 원격으로 업데이트  

3. App Apk파일  
   가) adb push app.apk /sdcard/Download/. && adb shell sync && adb shell pm install -r -g  /sdcard/Download/app.apk  
   나) We-Manager 에서 원격으로 업데이트  
   다) 이동식 USB 저장 장치의 루트 디렉토리에 "ds9100_emergency-release.apk" 을 복사 하여  
       &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;USB 포트에 결합 하면 즉시 APK 자동 설치 및 App 재시작  
   라) 이동식 USB 저장 장치의 루트 디렉토리에 "ds9100_XXXX.apk"  을 복사 하여 USB 포트에 결합 하고,  
       &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;OSD MENU- > 고객 지원 -> SW 업데이트 검사 메뉴를 이용하여 업데이트  

위에 3. 나) 다) 라) 방식을 사용 할 때 "com.dignsys.dsdsp" 패키지 이름으로 유효 APK 검증 합니다.
