# patch-base

这里保存的是 `xime-flush-bottom.patch` **生成时所依据的上游原始文件**
（即 ximeiorg/Xime@main 的 `XimeInputMethodService.kt` / `KeyboardLayout.kt` 改动前版本）。

构建工作流 `.github/workflows/build-patched.yml` 会用它们做三方合并：

    git merge-file  上游最新文件  patch-base/原版  (补丁作用在原版上得到的目标版本)

这样上游在别处改了代码也能自动把我们的改动搬过去，而不是逐行匹配失败。

⚠ 更新补丁时，**补丁和这两个基准文件必须一起重新生成**，否则第一步
「补丁作用在 base 上」就会失败（工作流会明确报错）。
