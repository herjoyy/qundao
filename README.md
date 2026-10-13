# 群岛榜单 · 部署包

这个文件夹就是一个完整的静态网站，不需要安装任何依赖、也不需要构建。
上传到任意静态网站托管服务，就能得到一个可以分享的公开网址。

```
qundao-site/
├── index.html        App 本体（所有代码都在这一个文件里）
├── share-cover.png   分享封面图
└── README.md         本说明
```

## 方式一：Netlify Drop（最快，约 1 分钟，无需写代码）

1. 打开 https://app.netlify.com/drop
2. 把整个 `qundao-site` 文件夹拖进页面
3. 几秒后得到一个网址，形如 `https://xxxx.netlify.app`
4. 注册并登录后可以在 Site settings 里把网址改成好记的名字

国内访问可能较慢，发给朋友前先用国内网络自己试一次。

## 方式二：GitHub Pages（免费、长期、方便以后更新）

1. 在 GitHub 新建一个公开仓库，例如 `qundao`
2. 把 `index.html` 和 `share-cover.png` 上传到仓库根目录
3. 进入仓库 Settings → Pages，Source 选 `Deploy from a branch`，分支选 `main`，目录选 `/ (root)`，保存
4. 约 1 分钟后得到网址：`https://<你的用户名>.github.io/qundao/`

以后改了 App，只要重新上传 `index.html`，网址不变。

## 方式三：Vercel 或 Cloudflare Pages

- Vercel：https://vercel.com/new ，选择上传文件夹或连接 GitHub 仓库，框架选 Other，直接部署。
- Cloudflare Pages：https://pages.cloudflare.com ，Create a project → Direct Upload，上传文件夹。

## 方式四：国内静态网站托管（朋友主要在国内时推荐）

腾讯云、阿里云等都有静态网站托管 / 对象存储静态网站功能，需要实名认证。
上传 `index.html` 和 `share-cover.png` 并把默认首页设为 `index.html` 即可。具体步骤以官方文档为准。

## 本地预览

在 `qundao-site` 文件夹里打开终端，运行：

```
python3 -m http.server 8000
```

然后在浏览器打开 http://localhost:8000 。同一 Wi-Fi 下的手机可以用 `http://<电脑的局域网 IP>:8000` 访问。

## 说明

- 这是演示原型：验证码为模拟，资料和上传的作品只保存在访问者自己的浏览器里，访问者之间看不到彼此的数据。
- 页面使用手机系统自带字体，不依赖谷歌字体，国内打开更快。
- 要让所有人在同一片群岛上合作，需要后续接入共享数据库。
