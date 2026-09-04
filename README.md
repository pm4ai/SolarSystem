# 太阳系探索者 · Solar System Explorer

一个基于 Three.js 的太阳系 3D 动态演示单页应用。深空黑 + 霓虹蓝/紫/橙科技感视觉。

![screenshot](https://img.shields.io/badge/Three.js-0.160-blue) ![license](https://img.shields.io/badge/textures-Solar%20System%20Scope-green)

## 功能

- **3D 太阳系全景**：太阳 + 八大行星 + 冥王星 + 月球，真实公转/自转（含金星、天王星逆行自转与轨道倾角）、小行星带（1600 块 GPU 自转的立体岩石）、银河系星空背景
- **8K 高清贴图**：来自 [Solar System Scope](https://www.solarsystemscope.com/textures/)（CC BY 4.0）
- **动态表面**：着色器驱动的太阳日面沸腾 + 日冕喷发、木星条带气流、地球云层漂移、金星厚云翻滚
- **飞船转移动画**：点击任意天体，相机以飞船视角飞往目标并钉住，进入特写聚焦模式（隐藏其他天体、柔和打光、赤道视角、光照随飞行平滑渐变）
- **信息面板**：每个天体的介绍、关键数据、冷知识，以及《國家地理》101科學教室系列 YouTube 视频（自定义无控件播放器，可放大到左侧大屏，带霓虹风格进度/音量控制栏）
- **控制**：时间流速（0–4×）、轨道线/标签开关、暂停、快捷导航

## 运行

需要一个静态服务器（ES Module + 贴图跨域限制，直接双击 file:// 打不开）：

```bash
npx -y serve -l 8642 .
```

然后访问 http://localhost:8642

## 技术栈

单文件 `index.html`，无构建步骤。Three.js 0.160（CDN importmap）、UnrealBloom 后期辉光、程序化 GLSL 着色器（FBM 噪声 UV 流动、菲涅尔大气、日冕喷发）、YouTube IFrame API。
