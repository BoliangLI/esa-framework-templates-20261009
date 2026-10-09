# ESA Pages 官方框架模板检测样本

初始化日期：2026-10-09。各子目录是独立项目，导入 Pages 时请选择对应根目录。

| 目录 | 官方初始化方式 | 说明 |
| --- | --- | --- |
| scully | Angular CLI 15 `ng new`，然后 `ng add @scullyio/init` | Scully 2.1.41 |
| blitz | `blitz new blitz` | Pages Router Minimal，Blitz 3.0.2 |
| nuxtjs | `npm create nuxt@latest -- --template v4` | Nuxt 4.6.0，默认 SSR |
| nuxtjs-ssg | 同上，build 改为 `nuxt generate` | 静态生成 |
| remix | `npx remix@latest new remix` | Remix 3.0.0，需要 Node >=24.3，无 build 命令 |
| remix-ssg | `create-remix@2.16.8` + 官方同版本 SPA 模板 | Remix 2 SPA 静态部署，不是多路由 SSG |
| ionic-angular | `ionic start ionic-angular blank --type angular-standalone` | 官方空白模板 |
| ionic-react | `ionic start ionic-react blank --type react` | 官方空白模板 |
| zola | `zola init zola` | Zola 0.23.6，默认 zola.toml |

文档来源：
- https://scully.io/docs/learn/getting-started/installation/
- https://blitzjs.com/docs/get-started
- https://nuxt.com/docs/4.x/getting-started/installation
- https://remix.run/
- https://v2.remix.run/docs/guides/spa-mode/
- https://ionicframework.com/docs/angular/quickstart
- https://ionicframework.com/docs/react/quickstart
- https://www.getzola.org/documentation/getting-started/cli-usage/

不提交依赖目录、构建产物或本地环境文件。模板保留官方依赖版本，不代表已通过生产安全审计或部署验证。

初始化兼容处理：Scully 的官方 schematic 需要 `src/polyfills.ts`，因此为 Angular 15 补齐该入口后，以 Puppeteer renderer 完成初始化。跳过了旧 Puppeteer 的 Chromium 下载。Remix 2 的主分支模板已移除，先获取官方 `remix@2.16.8` 标签，再用 `create-remix@2.16.8 --template <本地官方模板目录>` 生成。
