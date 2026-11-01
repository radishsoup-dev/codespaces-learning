# codespaces-learning
My learning notes and experiments with GitHub Codespaces

安全、可配置、专属、托管在云端，向仓库提交配置文件，可重复的。
基于 Ubuntu Host VM。
可通过浏览器、VS Code 或使用 CLI 连接 Codespaces。
对外部 Linux VM 访问权限有限。

可以从模板、从分支、从提交中创建 Codespace。在组织中创建 CS 
提供付款信息设置支出限制，自定义 CS 选配工具，可为用户创建一个或多个配置。
提供默认镜像，建议使用 Dotfiles 仓库。
可以保留自己的偏好，会执行脚本。
VS Code 配置可以同步。
未配置付款限制将阻止过度消费，添加了付款信息可以预算设置，按月计费。

仓库可以在setting中启用 Template Repository 功能。
有一节的内容是从模板仓库创建 CS，连接到转发端口，将 CS 发布到新仓库，使用 Settings Sync（设置同步）
看看 Codespace 的 features。可以专门配置开发环境，每个贡献者会有相同环境，本地计算机的环境保持不变。提供充足的算力或存储空间。
多设备与协同：只需要一个浏览器，可在多个设备或地点工作。可选多个编辑器，多个项目多个分支，搭载 Live Share。
可以转发端口，有模板。生命周期始于创建一个 CS，终止删除它，可以中断重连。

可以停止重启而不丢失项目所做的更改。可以创建短寿命也可以创建长寿命的。短期的记得push，长期的记得pull
可创建和可运行的是有限的。可以开启预构建，web 客户端默认会自动保存，记将 push 和发布。
 会超时，单次最长是12个小时。重建代码空间。停止 CS 时，保存的修改是有效的，终端记录可查，关闭不会导致停止。
停止后会产生存储成本，未推送仓库就删除CS会有提示。可手动拉出到新分支。已停止且不活动将在 30 天（可改）后删除。

可以从模板或模板仓库开始一个新项目。
从分支中、从 PR 中、从某个 Commit 中，

使用 VSC，使用 GitHub CLI，使用 Web 创建。


# Quickstart for GitHub Codespaces
从模板仓库创建一个 codespace，将使用浏览器版的 Visual Studio Code，可以更改默认编辑器。
连接到转发端口、发布到新仓库，以及使用扩展来个性化。
要暂存更改，文件旁边的 + 按钮，或者，想全部暂存，则点击“更改”旁边的 + 按钮。
# What are GitHub Codespaces?
托管在云端的开发环境。向仓库提交配置文件创建可重复使用的配置。
由 GitHub 托管在 Docker 容器中，运行在虚拟机上。你可以从多种虚拟机类型中选择，
范围从 2 核、8 GB RAM、32 GB 存储，到 32 核、128 GB RAM、128 GB 存储。

默认情况下，开发环境是基于 Ubuntu Linux 镜像创建的，
可以通过浏览器、Visual Studio Code 或使用 GitHub CLI 连接到代码空间。
连接后，你将进入 Docker 容器内。你对外部 Linux 虚拟机主机的访问权限有限。

可以从模板或仓库中的任何分支或提交创建代码空间。
从模板创建代码空间时，您可以从空白模板开始，也可以选择适合您当前工作的模板。

通过提供付款信息并设置支出限制。

可以为仓库创建一个或多个开发容器配置。定义多种不同的开发环境供选择，以适应人们在仓库中的工作需求。

从没有任何开发容器配置的仓库创建CS，会将您的仓库克隆到默认开发容器镜像的环境中。
如果您从模板创建代码空间，可能会在默认镜像的基础上获得一些初始配置。

您可以通过使用公共的 dotfiles 仓库来个性化代码空间环境的某些方面。
您可以使用 dotfiles 设置 shell 别名和首选项，或安装您喜欢使用的工具。
如果您在浏览器或 Visual Studio Code 中使用 GitHub Codespaces，
可以使用设置同步（Settings Sync）让代码空间编辑器拥有与本地安装的 Visual Studio Code 相同的设置、键盘快捷键、代码片段和扩展。

Codespaces 的费用始终按月计费。

# GitHub Codespaces features
- Preconfigured development environments 环境将包含所需的所有工具、语言和配置。每个在该 codespace 中工作的人都将拥有相同的环境。减少了发生与环境相关的问题且难以调试的可能性。每个代码仓库都可以拥有相关设置，为贡献者提供一个即用型、适合用途的环境，而你本地计算机上的环境将保持不变。
- Access the resources you need 本地可能不具备处理项目所需的算力或存储空间。
- Work anywhere 只需要一个网页浏览器。可以在自己的电脑、朋友的笔记本电脑或平板电脑上使用 codespace 进行工作。便可以从另一台设备上中断的地方继续工作。
- Choose your editor
- Work on multiple projects 使用多个 CS 来处理不同的项目，或者处理同一仓库的不同分支，将工作相互隔离，以避免为一项工作所做的更改意外影响到你正在进行的其他工作。
- Pair program with a teammate Live Share
- Publish your web app from a codespace 转发端口，然后共享 URL，以便您的队友在您提交拉取请求之前，能够试用您对应用程序所做的更改。
- Try out a framework 只需从其中一个快速入门模板创建一个代码空间即可。

# Understanding the codespace lifecycle
始于您创建 codespace，终于您将其删除。
您可以断开连接并重新连接到活动状态的 codespace，而不会影响其正在运行的进程。
您可以停止并重新启动 codespace，而不会丢失对项目所做的更改。

可以创建的代码空间数量以及可以同时运行的代码空间数量存在限制。
如果你选择每次处理项目时都创建新的代码空间，应定期推送更改，以便任何新提交都位于 GitHub 上。
如果选择为项目使用长时间运行的代码空间，则每次开始在代码空间中工作时，都应从仓库的默认分支拉取。

为了加快代码空间的创建速度，仓库管理员可以为仓库启用 GitHub Codespaces 预构建。

通过 Web 连接到 codespace 时，Web 编辑器会自动启用自动保存。
Visual Studio Code 连接到 codespace 时，必须启用自动保存。

可以关闭并停止一个 codespace，稍后再回到已保存的工作。codespace 被删除，那么你的工作也将被删除。
要持久保存你的工作，你需要提交更改并将其推送到远程仓库，或者发布到新的远程仓库。

在没有任何交互的情况下让 codespace 保持运行，或者在退出 codespace 时没有显式停止它，
将在一段不活动期后超时并停止运行。默认在不活动 30 分钟后会超时，但你可以自定义超时时长。

无论您的空闲超时策略或设置如何，代码空间的最长生存期均为 12 小时。即使您正在主动使用代码空间，此限制也同样适用。

Rebuilding a codespace以应用对开发容器配置所做的更改。
当然可以重建一个新的。
在 /workspaces 目录外所做的更改将被清除。在 /workspaces 目录内所做的更改会在重建后保留。

只有运行中的代码空间会产生 CPU 费用。已停止的代码空间仅产生存储成本。
可能需要停止并重新启动代码空间以应用更改。例如，如果您更改了代码空间使用的机器类型，则需要停止并重新启动它才能使更改生效。

可以为特定任务创建一个 codespace，然后在将更改推送到远程分支后安全地删除该 codespace。
已停止且在指定时间内保持不活动的 codespace 将自动删除。默认情况下会在 30 天后删除，但您可以自定义 codespace 的保留期限。

# Deep dive into GitHub Codespaces
即时的、基于云的开发环境，使用容器为你提供常用的语言、工具和开发实用程序。
GitHub Codespaces 也是可配置的，允许你为项目创建自定义的开发环境。通过为项目配置自定义开发环境，你可以为项目的所有用户提供一个可重复的 codespace 配置。

有多种入口可以创建代码空间：
- From a GitHub template or any template repository on GitHub to start a new project
- From a branch in your repository for new feature work
- From an open pull request to explore work-in-progress
- From a commit in a repository's history to investigate a bug at a specific point in time

创建一个 codespace 时，后台会执行各种步骤。
Step 1: VM and storage are assigned to your codespace
使用 VM 主机镜像的稳定版或公共预览版来创建虚拟机 (VM)。主机镜像定义了 VM 所使用的 Linux 版本。该虚拟机是专用的且对你私有的。拥有专用虚拟机可确保你拥有该机器的全部计算资源。如有必要，这也允许你对容器拥有完全的根访问权限。然后会对你的仓库（或者，如果你是从模板创建 codespace，则对模板仓库）进行浅克隆。这会被克隆到 VM 的 /workspaces 目录中，随后挂载到开发容器中。
Step 2: Dev container is created
 Codespaces 使用 Docker 容器作为开发环境。该容器基于您可以在 devcontainer.json 文件中定义的配置创建，还可以选择使用 Dockerfile。如果您从 GitHub 的空白模板创建代码空间，或者从没有 devcontainer.json 文件的仓库创建代码空间，GitHub Codespaces 会使用默认镜像，其中包含许多语言和运行时。
Step 3: Connecting to the codespace
Step 4: Post-creation setup
连接到代码空间后，基于 devcontainer.json 文件中指定的配置，自动化设置可能会继续构建。你可能会看到 postCreateCommand 和 postAttachCommand 在运行。

如果你想在代码空间中使用 Git 钩子，请使用 devcontainer.json 生命周期脚本有用于 GitHub Codespaces 的公共 dotfiles 仓库，可以启用它以供新的代码空间使用。启用后，你的 dotfiles 将被克隆到容器中，并调用安装脚本。如果是从仓库创建代码空间，则会通过完整克隆下载该仓库的整个历史记录。编辑器中的文件更改和终端输出被视为活动，因此如果终端输出持续进行，您的代码空间不会超时。

type Codespaces: stop

当在 GitHub Codespaces 中运行的应用程序向控制台输出端口时，会检测到 localhost URL 模式并自动转发该端口。
默认情况下，GitHub Codespaces 使用 HTTP 转发端口。

默认情况下，所有端口都是私有的，但您可以手动将端口设置为对您的组织可用或公开，然后通过 URL 共享访问权限。

如果你对某个仓库只有读取权限，只要允许你 Fork（派生）该仓库，你仍然可以为其创建 Codespace。

当你在 Codespace 中创建提交（Commit），或者推送一个新分支时，GitHub Codespaces 会自动为你创建该仓库的 Fork；如果你此前已经为上游仓库（Upstream Repository）创建过 Fork，则会将当前 Codespace 关联到已有的 Fork。

除 /tmp 目录外，/workspaces 之外的其他目录都与容器的生命周期绑定。
清理 /workspaces 之外的目录，有助于确保重新构建后的容器能够恢复到与新创建的 Codespace 相同的初始状态。
通过修改配置来调整开发环境。此时，如果重新构建容器以应用这些配置更改，你就可以确信：使用相同配置创建的其他用户 Codespace，也能够获得一致的运行环境。

换句话说，这种机制有助于保证开发环境的可重复性（Reproducibility）。
如果你希望对 Codespace 所做的配置能够经受容器重新构建，并且在不同 Codespace 之间保持一致，可以采用以下几种方式。
方式一：通过 Dev Container 配置安装软件

如果你希望从某个代码仓库创建的所有 Codespace 都自动安装指定的软件和工具，可以在 Dev Container 配置中使用生命周期命令属性（Lifecycle Command Properties）。

例如：
- postCreateCommand：在容器创建完成后执行自定义安装命令。
- Features：使用预先编写好的安装配置，为开发容器添加软件和工具。

方式二：使用 Dotfiles 仓库

如果你希望在自己创建的每一个 Codespace 中都安装特定工具，或者自定义开发环境，例如配置 Bash Shell 的用户配置文件，可以将 GitHub Codespaces 与 Dotfiles 仓库关联起来。

Dotfiles 仓库同样会被克隆到持久化目录 /workspaces 中。

方式三：使用符号链接保留指定文件

如果你只希望在容器重新构建后保留某些特定文件，可以通过 devcontainer.json 创建符号链接（Symbolic Link），将这些文件关联到 /workspaces 中的持久化目录。

这样，即使容器重新构建，原本存放在容器非持久化目录中的配置文件，也能够通过持久化目录得到保留。
 
