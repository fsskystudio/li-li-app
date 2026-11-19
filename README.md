# 狸哩 App

Lili （狸哩） Android 客户端原型：两个 10 秒动作视频循环播放，1.6 秒淡入淡出衔接。

## 结构

- `www/` — 网页：`index.html` + 两个视频（视频不在 git 里，见下）
- `capacitor.config.json` — 应用 ID `com.fsskystudio.lili`，横屏
- `.github/workflows/build-apk.yml` — GitHub Actions 打包

## 视频

两个视频是二进制文件，不进 git。构建时从我们自己的服务器下载：

- https://lili.fsskystudio.com/app/video1.mp4
- https://lili.fsskystudio.com/app/video2.mp4

## 打包

推送到 `main` 分支后，GitHub Actions 自动打包，在 Actions 页面的运行记录里下载 `lili-debug-apk`（debug 包，直接安装到手机上，不上架 Google Play）。

本地打包：

```bash
npm install
npx cap add android
npx cap sync android
./android/gradlew -p android assembleDebug
```
