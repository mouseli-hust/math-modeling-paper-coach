# GitHub 首次上传指南（纯网页方式）

这套文件很小，不需要安装 Git、GitHub Desktop 或命令行工具。按下面步骤在浏览器中上传即可。

## 一、先准备文件

1. 找到压缩包 `math-modeling-paper-coach-v1.0.0.zip`。
2. 在 Windows 中右键压缩包，选择“全部解压缩”。
3. 打开解压后的 `math-modeling-paper-coach` 文件夹。
4. 确认最外层能直接看到 `README.md`、`SKILL.md`、`agents`、`assets`、`docs`、`examples`、`references`。

不要只把 ZIP 文件上传到 GitHub。GitHub 会把它当作一个普通压缩文件，不会自动展开仓库目录，也无法直接展示其中的 README。

## 二、创建 GitHub 仓库

1. 登录 [GitHub](https://github.com/)。
2. 打开 [新建仓库页面](https://github.com/new)。也可以点击页面右上角的 `+`，再点 `New repository`。
3. `Owner` 选择你自己的账号。
4. `Repository name` 填：

   ```text
   math-modeling-paper-coach
   ```

5. `Description` 建议填：

   ```text
   基于 2017–2023 年 278 篇优秀数模论文提炼的赛题分析、建模、验证与论文写作 Codex Skill
   ```

6. 选择可见性：

   - `Public`：任何人都能看到，适合分享；
   - `Private`：只有你和你授权的人能看到，适合先试用。

   第一次使用、尚未决定是否公开时，建议先选 `Private`，以后可以在仓库设置中改成 `Public`。

7. **不要勾选** `Add a README file`，也先不要添加 `.gitignore` 或 License。压缩包内已经有 README；创建空仓库能避免同名文件冲突。
8. 点击 `Create repository`。

GitHub 官方创建仓库说明：[Creating a new repository](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-new-repository)。

## 三、上传解压后的全部内容

创建空仓库后，会看到 `Quick setup` 页面。

1. 点击 `uploading an existing file`。如果已进入仓库主页，则点击 `Add file` → `Upload files`。
2. 回到 Windows 文件资源管理器，进入解压后的 `math-modeling-paper-coach` 文件夹。
3. 按 `Ctrl+A` 选中里面的**全部文件和子文件夹**，把它们一起拖到 GitHub 上传区域。
4. 等待文件列表全部出现。应看到顶层的 `README.md`、`SKILL.md` 以及多个文件夹。
5. 页面下方的提交说明填写：

   ```text
   Initial release of math-modeling-paper-coach
   ```

6. 保持 `Commit directly to the main branch`。
7. 点击 `Commit changes`。
8. 等待页面返回仓库主页。

GitHub 官方说明网页上传单个文件通常不能超过 25 MiB，并且一次最多上传 100 个文件；本包只有少量 Markdown/YAML 文件，远低于限制。官方说明：[Adding a file to a repository](https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository)。

## 四、检查是否上传成功

仓库主页应满足：

- 页面下方自动显示中文 README；
- 顶层可见 `SKILL.md`；
- 能进入 `references`、`docs`、`assets`、`examples` 和 `agents`；
- 打开 `docs/优秀论文分析总结.md` 能正常显示中文；
- 打开 `agents/openai.yaml` 没有乱码；
- 仓库里没有原始优秀论文 PDF。

如果 README 没显示，通常是因为上传了外层文件夹本身，导致仓库根目录又多了一层 `math-modeling-paper-coach`。最简单的修复办法是删掉仓库重新创建，再上传该文件夹**里面的内容**。

## 五、复制仓库网址

上传成功后，浏览器地址栏会类似：

```text
https://github.com/你的用户名/math-modeling-paper-coach
```

这个网址就是仓库链接。你可以保存或分享它；如果仓库是 Private，未授权的人打不开。

## 六、以后如何更新文件

少量文件更新可直接用网页：

1. 进入仓库；
2. 点击 `Add file` → `Upload files`；
3. 拖入更新后的同名文件；
4. GitHub 会识别替换内容；
5. 在提交说明中写清更新，例如 `Improve modeling validation guide`；
6. 点击 `Commit changes`。

也可以点开单个 Markdown 文件，点击铅笔图标在线编辑，预览后提交。

## 七、可选：发布版本 Release

首次上传完成后，可把压缩包作为 v1.0.0 附件发布：

1. 在仓库主页右侧找到 `Releases`，点击 `Create a new release`；
2. `Choose a tag` 输入 `v1.0.0`，选择创建新标签；
3. 标题填 `v1.0.0 - Initial release`；
4. 说明可写“首次发布：包含 Skill、语料分析、建模指南、写作指南、审查量表和论文模板”；
5. 将原始 ZIP 拖到附件区域；
6. 点击 `Publish release`。

Release 是可选步骤；仓库文件上传成功后已经可以使用。

## 八、关于 License

当前包没有替你选择开源许可证。仓库设为 Public 并不等于允许他人随意复制、修改和再发布。如果你希望明确允许复用，可在了解许可证差异后添加 MIT、Apache-2.0 等 License；不确定时可以暂时不添加，或先保持 Private。

## 九、安全提醒

- 不要上传密码、令牌、浏览器 Cookie、身份证明或竞赛未公开数据；
- 本包已经排除原始 PDF，只发布分析结果和自创文档；
- 提交前再检查文件列表，确认没有误选工作区中的其他资料；
- MFA 失败不影响你通过正常浏览器登录后使用网页上传；若登录本身受阻，应先用 GitHub 的账号恢复流程处理。
