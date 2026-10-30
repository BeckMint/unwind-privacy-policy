# 官方站点同步发布

源目录：`release_materials/github_pages_privacy_deploy/`。目标仓库：`BeckMint/unwind-privacy-policy`，main分支GitHub Pages。

1. 在独立临时目录克隆发布仓库，保留远端历史文件。
2. 核对App版本、versionCode、渠道与实际签名APK。计算文件大小、SHA-256，更新releases.html、RELEASES.md与latest.json。
3. 仅复制需要发布的文档、页面与APK；不复制工程凭证、临时日志或未审核素材。
4. 审查git diff后提交、推送。确认Pages部署成功，检查发布页、主题页、隐私页和latest.json，下载APK后校验SHA-256。
5. 文档修订不自动改变隐私条款的法律生效日期；历史版本、历史渠道APK不删除。

当前通用包1.0.7（1007），vivo历史专属包1.0.4（1004）。
