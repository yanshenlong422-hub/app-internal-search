# 应用内搜索工具

一个轻量级多应用快速搜索解决方案，通过URL Scheme协议直接调用各类应用执行搜索操作，支持自定义应用添加和主题切换。

![应用内搜索工具预览](https://picsum.photos/800/400?random=1)
*应用界面预览（示意图）*

## 功能特性

- **多应用快速跳转**：一键调用指定应用并执行搜索，无需手动打开应用再搜索
- **自定义应用支持**：灵活添加任意应用的搜索链接，满足个性化需求
- **双主题模式**：内置明亮/暗黑主题，自动适应系统设置或手动切换
- **网页版备选**：当应用无法打开时，自动提供网页版搜索选项
- **本地存储**：用户配置和自定义应用信息保存在本地，无需服务器
- **响应式设计**：完美适配手机、平板和桌面设备

## 支持的应用（示例）

默认提供以下应用的搜索模板，用户可直接使用或参考格式添加更多应用：

| 应用名称 | URL Scheme |
|---------|------------|
| 美团 | `imeituan://www.meituan.com/search?q={query}` |
| 大众点评 | `dianping://searchshoplist?keyword={query}` |
| 天猫 | `tmall://page.tm/search?q={query}` |
| 京东 | `openapp.jdmobile://virtual?params={"des":"productList","keyWord":"{query}","from":"search","category":"jump"}` |
| 小红书 | `xhsdiscover://search/result?keyword={query}` |
| 哔哩哔哩 | `bilibili://search?keyword={query}` |
| 抖音 | `snssdk1128://search/result?keyword={query}` |
| 淘宝 | `taobao://s.taobao.com/search?q={query}` |

> 完整应用列表可在项目描述中查看，所有模板均使用`{query}`作为搜索关键词占位符

## 使用方法

1. **基础搜索**：
   - 在搜索框输入关键词
   - 从下拉菜单选择目标应用
   - 点击"搜索"按钮或按下回车

2. **添加自定义应用**：
   - 点击界面右下角的设置图标 ⚙️
   - 在弹出的设置面板中点击"添加应用"
   - 填写应用名称和URL Scheme（需包含`{query}`作为关键词占位符）
   - 点击"保存"完成添加

3. **切换主题**：
   - 点击顶部导航栏的月亮/太阳图标 🌙/☀️
   - 或在设置面板中勾选"跟随系统主题"

4. **使用网页版**：
   - 当应用无法打开时，界面会自动显示"打开网页版"选项
   - 点击即可跳转到对应应用的网页版搜索结果页

## 技术实现

- **前端框架**：HTML5 + Vanilla JavaScript
- **样式系统**：Tailwind CSS v3
- **图标资源**：Font Awesome
- **数据存储**：localStorage（用户配置和自定义应用）
- **核心原理**：通过URL Scheme协议唤起外部应用，使用`{query}`占位符动态替换搜索关键词

## 本地部署

1. 克隆本仓库：
   ```bash
   git clone https://github.com/你的用户名/app-internal-search.git
   ```

2. 进入项目目录：
   ```bash
   cd app-internal-search
   ```

3. 直接打开`index.html`文件即可使用，无需额外依赖

## 注意事项

- URL Scheme调用功能依赖于设备和应用的支持，部分应用可能需要特定版本
- 不同平台（iOS/Android）的同一应用可能使用不同的URL Scheme格式
- 自定义应用添加时，请确保URL格式正确并包含`{query}`占位符
- 隐私说明：所有数据均存储在本地设备，不会上传至任何服务器

## 许可证

本项目采用MIT许可证开源 - 详见[LICENSE](LICENSE)文件

## 贡献指南

欢迎提交Issue或Pull Request改进本项目：
1. Fork本仓库
2. 创建特性分支 (`git checkout -b feature/amazing-feature`)
3. 提交更改 (`git commit -m 'Add some amazing feature'`)
4. 推送到分支 (`git push origin feature/amazing-feature`)
5. 打开Pull Request
