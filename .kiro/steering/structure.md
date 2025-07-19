# 项目结构与组织规范

## 目录结构
```
src/
├── api/                    # API 接口定义
│   ├── types/             # API 类型定义
│   ├── foo.ts             # 示例 API
│   └── login.ts           # 登录相关 API
├── components/            # 全局组件
├── hooks/                 # 自定义 Hooks
│   ├── usePageAuth.ts     # 页面权限
│   ├── useRequest.ts      # 请求封装
│   └── useUpload.ts       # 文件上传
├── http/                  # HTTP 请求配置
│   ├── request/           # 请求相关
│   ├── http.ts            # HTTP 实例
│   └── interceptor.ts     # 请求拦截器
├── layouts/               # 布局组件
│   ├── fg-tabbar/         # 底部导航配置
│   ├── default.vue        # 默认布局
│   └── tabbar.vue         # 底部导航布局
├── pages/                 # 主包页面
│   ├── index/             # 首页
│   ├── about/             # 关于页面
│   ├── test/              # 测试页面
│   └── waterfall/         # 瀑布流示例
├── pages-sub/             # 分包页面
│   └── demo/              # 示例分包
├── router/                # 路由配置
│   └── interceptor.ts     # 路由拦截器
├── service/               # 业务服务层
├── static/                # 静态资源
│   ├── app/               # App 相关资源
│   ├── images/            # 图片资源
│   ├── tabbar/            # 底部导航图标
│   └── logo.svg           # Logo
├── store/                 # 状态管理
│   ├── index.ts           # Store 入口
│   └── user.ts            # 用户状态
├── style/                 # 全局样式
│   ├── index.scss         # 样式入口
│   └── iconfont.css       # 图标字体
├── types/                 # 类型定义
│   ├── auto-import.d.ts   # 自动导入类型
│   ├── uni-pages.d.ts     # 页面路由类型
│   └── async-*.d.ts       # 异步组件类型
├── uni_modules/           # uni_modules 插件
├── utils/                 # 工具函数
│   ├── index.ts           # 工具入口
│   ├── platform.ts        # 平台判断
│   ├── request.ts         # 请求工具
│   ├── toast.ts           # 提示工具
│   └── uploadFile.ts      # 文件上传
├── App.vue                # 应用入口
├── main.ts                # 主入口文件
├── pages.json             # 页面配置
└── manifest.json          # 应用配置
```

## 文件命名规范
- **页面文件**: 使用 kebab-case，如 `user-profile.vue`
- **组件文件**: 使用 PascalCase，如 `UserCard.vue`
- **工具文件**: 使用 camelCase，如 `formatDate.ts`
- **常量文件**: 使用 UPPER_SNAKE_CASE，如 `API_CONSTANTS.ts`

## 页面组织规范
- **主包页面**: 放在 `src/pages/` 下，按功能模块分文件夹
- **分包页面**: 放在 `src/pages-sub/` 下，每个分包一个文件夹
- **页面路由**: 使用约定式路由，通过 `<route>` 块配置页面属性

## 组件组织规范
- **全局组件**: 放在 `src/components/` 下，使用 `fg-` 前缀
- **页面组件**: 与页面文件放在同一目录下
- **组件自动注册**: 支持 `fg-*`、`wd-*`、`sar-*`、`z-paging*` 前缀自动注册

## API 组织规范
- **接口定义**: 放在 `src/api/` 下，按业务模块分文件
- **类型定义**: 放在 `src/api/types/` 下
- **请求封装**: 使用 Alova 进行统一封装

## 样式组织规范
- **全局样式**: 放在 `src/style/` 下
- **组件样式**: 使用 `<style lang="scss" scoped>`
- **原子样式**: 优先使用 UnoCSS 类名
- **自定义样式**: 使用 SCSS 编写

## 路径别名配置
- `@/`: 指向 `src/` 目录
- `@img/`: 指向 `src/static/` 目录

## 环境配置
- 环境变量文件放在 `env/` 目录下
- 使用 `VITE_` 前缀的环境变量
- 支持 `.env.development` 和 `.env.production`