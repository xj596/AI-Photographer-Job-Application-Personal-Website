# 个人求职作品集网站

刘楚江的求职作品集：摄影师 / AI 视频生成师 / 剪辑师 / 网站搭建者，纯静态页面，推送到 Git 后即可直接部署上线。

## 当前状态

- ✅ 简历信息已填写：姓名、电话、邮箱、年龄、经验、工作经历、教育经历均已填入（求职意向按需求设为「线上视频生成与剪辑工作」）。
- ✅ 联系方式已填：电话 15842823831、邮箱 15842823831@163.com。微信号暂不填写，「联系方式」中已暂时移除微信行；以后需要时在 `index.html` 联系区加回一行即可：`<div><dt>微信</dt><dd>你的微信号</dd></div>`
- ✅ 11 个视频已嵌入线上链接（6 个 AI 视频 + 5 个实拍视频，托管于 `video.aultras-tea.com`），打开页面即可播放。
- ✅ 播放不了的视频会**自动隐藏整个展示位**（不显示占位提示），能播放的正常展示。
- ✅ 2 个网站展示位已链接到 `xiangfengtea.com` 与 `aultras-tea.com`。
- ⬜ 网站首页截图暂不填写：放入 `assets/sites/site-01.png`、`site-02.png` 后会自动展示（未放置时显示占位提示）。

## 目录结构

```
portfolio-site/
├── index.html          # 网站主页（单文件，含全部样式与脚本）
├── assets/
│   ├── videos/         # 本地视频回退目录（当前全部使用线上链接，可留空）
│   │   ├── ai-01.mp4 ~ ai-06.mp4       # 6 个 AI 视频展示位的本地回退
│   │   └── shoot-01.mp4 ~ shoot-05.mp4 # 5 个实拍视频展示位的本地回退
│   └── sites/          # 网站截图放这里
│       ├── site-01.png                 # 湘丰茶业官网首页截图
│       └── site-02.png                 # Aultras Tea 官网首页截图
├── _shared/            # 预留的公共 JS/字体目录（当前未使用）
└── README.md
```

## 视频链接说明

所有视频均通过 `<source src="https://video.aultras-tea.com/...">` 直接引用线上地址，无需下载到仓库。其中 2 个为 MOV 原片（已省略类型声明，让浏览器自行尝试解码）：能播放则正常展示，播放不了则该展示位会自动隐藏，不影响页面其余部分。

修改或替换视频：编辑 `index.html` 中对应 `<figure class="slot">` 内的 `src` 即可。

## 网站截图

将两个网站首页截图命名为 `site-01.png`、`site-02.png` 放入 `assets/sites/`，页面会自动展示；文件不存在时显示占位提示，不影响其余部分。

## 推送到 Git 并上线（GitHub Pages）

```bash
# 1. 在 GitHub 新建一个仓库（如 portfolio-site），然后在本目录执行：
git init
git add .
git commit -m "feat: 个人求职作品集网站"

git branch -M main
git remote add origin https://github.com/<你的用户名>/portfolio-site.git
git push -u origin main
```

然后在 GitHub 仓库页面：**Settings → Pages → Source 选择 `main` 分支、`/ (root)` → Save**。

等待约 1 分钟，网站地址为：`https://<你的用户名>.github.io/portfolio-site/`

### 其他平台

- **Gitee / GitLab**：推送方式相同，开启各自的 Pages 服务即可。
- **Vercel / Netlify**：导入仓库后零配置自动部署。

## 本地预览

直接双击 `index.html` 用浏览器打开即可；或在目录下运行：

```bash
python3 -m http.server 8000
# 浏览器访问 http://localhost:8000
```
