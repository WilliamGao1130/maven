# Maven Repository

本仓库作为 Maven 仓库使用，通过 **GitHub Pages 从 `main` 分支根目录**对外提供，
采用标准 Maven 目录结构：

```
com/easytier/easytier-jni/
├── 2.6.4/
│   ├── easytier-jni-2.6.4.aar
│   └── easytier-jni-2.6.4.pom
└── maven-metadata.xml
```

## 配置

1. Settings → Pages → **Deploy from a branch** → `main` / `/`（根目录）。
2. 仓库 URL：`https://williamgao1130.github.io/maven`

根目录已包含 `index.html`（Pages 首页）；GitHub Pages 在没有 `index.html` 时
会以 `README.md` 作为首页，两者都保留一份。

## 内容从哪来

内容由 [easytier-jni](https://github.com/WilliamGao1130/easytier-jni) 仓库的
GitHub Actions（`Build & Publish easytier-jni`）在检测到 EasyTier 官方新版本后
构建并提交到本仓库 `main` 分支，无需在本仓库配置任何 workflow。

## 使用

```kotlin
maven { url = uri("https://williamgao1130.github.io/maven") }

implementation("com.easytier:easytier-jni:2.6.4")
```
