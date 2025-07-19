# 技术栈与构建系统

## 核心技术栈
- **框架**: uniapp + Vue 3.4+ (Composition API)
- **语言**: TypeScript 5.7+
- **构建工具**: Vite 5.2+ 
- **包管理器**: pnpm 10.10+ (必须使用，项目配置了 preinstall 检查)
- **样式方案**: UnoCSS + SCSS
- **状态管理**: Pinia 2.0+ (支持持久化)
- **HTTP 请求**: Alova 3.3+ (支持多平台适配)
- **UI 组件库**: 
  - sard-uniapp 1.22+ (主要 UI 库)
  - wot-design-uni 1.10+ (辅助 UI 库)
  - z-paging 2.8+ (分页组件)

## 开发环境要求
- Node.js >= 18
- pnpm >= 7.30
- Vue Official 插件 >= 2.1.10 (VSCode)
- TypeScript >= 5.0

## 常用开发命令

### 开发模式
```bash
# H5 开发
pnpm dev
pnpm dev:h5

# 小程序开发
pnpm dev:mp          # 微信小程序
pnpm dev:mp-weixin   # 微信小程序
pnpm dev:mp-alipay   # 支付宝小程序
pnpm dev:mp-baidu    # 百度小程序

# App 开发
pnpm dev:app
pnpm dev:app-android
pnpm dev:app-ios
```

### 生产构建
```bash
# H5 构建
pnpm build
pnpm build:h5

# 小程序构建
pnpm build:mp
pnpm build:mp-weixin

# App 构建
pnpm build:app
```

### 代码质量
```bash
# 类型检查
pnpm type-check

# 代码检查
pnpm lint

# 代码修复
pnpm lint:fix

# API 类型生成
pnpm openapi-ts-request
```

### 版本管理
```bash
# 升级 uni-app 版本
pnpm uvm

# 清理升级缓存
pnpm uvm-rm
```

## 构建配置特点
- 支持多平台条件编译
- 自动导入 Vue 和 uni-app API
- 组件自动注册
- 约定式路由自动生成
- 支持 SSR (H5)
- 内置代码分割和优化
- 支持环境变量配置