# 🕵️‍♂️ Undetectable Fingerprint Browser  
**开源·模块化·可编程的反检测浏览器**

Undetectable Fingerprint Browser 是一款 **高度可定制、真实可还原、自动化友好** 的反检测浏览器，专为对抗现代网站复杂指纹识别系统而设计。无论你是进行 **反反爬研究、营销监测、多账号防关联**，还是需要构建一个**高度可控的自动化浏览器环境**，本项目都是你的不二之选。
下载[编译后二进制版本](https://github.com/itbrowser-net/undetectable-fingerprint-browser/releases/download/v1.0.0/fingerprint_browser_v1.0.7z) 
---

## 🚀 项目亮点

### 🧠 1. 全维度指纹伪装（Comprehensive Fingerprint Spoofing）

> 伪装不仅要广，还要“假得像真”，实现“全局一致”。

| 指纹类型        | 功能描述 |
|----------------|----------|
| **Canvas Fingerprint** | 支持精度伪装、随机噪声、自定义绘图返回值 |
| **WebGL & WebGL2** | 模拟显卡型号、绘图返回值、渲染字符串、抗锯齿特性等 |
| **AudioContext Fingerprint** | 改写音频处理行为，生成稳定音频指纹伪值 |
| **ClientRects / DOMRect** | 模拟不同浏览器在元素渲染位置上的偏移差异 |
| **Font Fingerprint** | 支持字体探测响应控制，避免字体探测器识别出真实系统字体 |
| **Timezone / Language** | 全局覆盖 navigator、Intl API、Date 输出等相关信息 |
| **Hardware Concurrency** | 自定义 CPU 核心数 |
| **Device Memory** | 控制设备内存显示值（navigator.deviceMemory） |
| **Screen Resolution & Color Depth** | 模拟不同的屏幕尺寸与颜色深度 |
| **Touch / Mobile Indicators** | 支持移动设备环境模拟：触摸特性、UA、MediaQuery 等 |

👉 **独家特性：一致性分析机制**，确保每个修改项不会相互冲突，从根源消除检测点。

---

### 🧩 2. 全面支持 & 内置自带（Modular & Extensible）

我们构建了完整的防泄露系统，以下都是自带无需额外安装的：

- ✅ 支持 WebRTC 防泄露插件  
- ✅ 支持 Canvas/WebGL 自动适配插件  
- ✅ 支持浏览器自动化控制模块（支持 Puppeteer / Playwright）  
- ✅ 支持网络代理自动注入（SOCKS5, HTTP, TLS proxy）  
- ✅ 支持 GPS 定位 / 传感器数据模拟  
- ✅ 支持本地 JS 脚本注入，绕过 CSP  



---

### 🤖 3. 自动化友好（Automation-Ready）

你可以将浏览器无缝集成至自动化系统，或通过编程方式控制每个细节。

#### 🤝 完整支持控制框架：
- 只需要在浏览器启动的时候加一个参数即可，无需其他额外操作，不需要改代码
- Puppeteer：通过自定义 Chromium 路径运行；
- Playwright：兼容 chromium 引擎调用；
- 支持 DevTools Protocol、WebSocket 控制接口；
- 提供 JS API 与 CLI 工具用于自定义调试与调控；

#### 🧪 预构建 API 示例：

```js
const browser = await launch({
  proxy: 'socks5://user1:password2@127.0.0.1:9050',
  itbrowser: 'chrome-114-win10-en-US.json',
  
});
```

---

## 🌍 真实世界应用场景

| 应用场景         | 说明 |
|------------------|------|
| ✅ 反爬虫环境构建 | 自动化脚本绕过人机验证、抗检测 |
| ✅ SEO & 广告验证 | 批量模拟不同地域设备访问行为 |
| ✅ 多账号登录环境 | 防止 Cookie / Storage / 指纹等被平台绑定识别 |
| ✅ 数据抓取研究   | 与各类网页指纹检测工具对抗，辅助开发爬虫策略 |
| ✅ 安全研究用途   | 用于安全研究、反识别机制验证、检测指纹漏洞 |

---

## 📊 与市面主流方案对比

| 功能/方案               | Puppeteer Stealth | Playwright Stealth | Undetectable-fingerprint-Browser |
|------------------------|-------------------|--------------------|--------------------------|
| 多维指纹模拟支持       | 部分支持          | 部分支持           | ✅ 全维度支持             |
| 插件机制               | ❌ 无              | ❌ 无               | ✅ 完整插件系统           |
| 与浏览器行为一致性     | ❌ 偶发冲突        | ❌ 偶发冲突         | ✅ 自适应一致性管理       |
| 自定义程度             | 中                | 中                 | ✅ 高度可配置             |
| 环境隔离性             | 中                | 中                 | ✅ 高度沙盒隔离           |
| 与控制框架集成         | ✅ 支持            | ✅ 支持             | ✅ 支持                   |

---

## 🔧 快速开始
# 安装预先编译版本
下载解压预先编译好的版本 [https://www.itbrowser.net](https://www.itbrowser.net)

```bash
# 克隆项目
# 启动浏览器
chrome --itbrowser=myfingerprint.json
```

**或使用 Puppeteer：**

```js
const puppeteer = require('puppeteer');
const browser = await puppeteer.launch({ headless: false,itbrowser:"myfingerprint.json" });
```

---

# 从源码编译项目
git clone https://github.com/itbrowser-net/undetectable-fingerprint-browser.git
合并源码到chromium源码


## ⚠️ 法律免责声明

本项目仅供合法合规用途，例如安全研究、自动化测试、开发环境伪装等。**禁止将本项目用于非法数据抓取、广告欺诈、账号盗用等违法行为。**

开发者不对滥用本项目所造成的后果承担任何责任。

---

## 📫 联系我们

- Github Issues 区欢迎提问或交流；
- 若需企业级支持或定制服务，可邮件联系：`javaflashproject@gmail.com`
- [https://discord.gg/AhW2RaHCs6](https://discord.gg/AhW2RaHCs6)

---

> ⭐ 如果你觉得本项目对你有帮助，值得启动，欢迎点个 Star 支持一下！我将逐步上传项目源码。

---
