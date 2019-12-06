# ansible-azcli-docker-dev-env
Development environment with Ansible and Azure CLI

# Developing Ansible-Azure inside a Container

We are going to use a Docker container as a full-featured development environment. It allows you to open any folder inside (or mounted into) a container and take advantage of Visual Studio Code's full feature set.

Workspace files are mounted from the local file system into the container. Extensions are installed and run inside the container, where they have full access to the tools, platform, and file system. This means that you can seamlessly switch your entire development environment just by connecting to a container.

<IMG  src="https://code.visualstudio.com/assets/docs/remote/containers/architecture-containers.png"  alt="Container Architecture"/>

This lets VS Code provide a local-quality development experience — including full IntelliSense (completions), code navigation, and debugging — regardless of where your tools (or code) are located.

# Installation

To get started, follow these steps:

1. Install and configure [Docker](https://www.docker.com/get-started) for your operating system.

    **Windows / macOS:**
    1. Install [Docker Desktop for Windows/Mac](https://www.docker.com/products/docker-desktop).
    2. Right-click on the Docker taskbar item and update **Settings / Preferences > Shared Drives / File Sharing** with any source code locations you want to open in a container. If you run into trouble, see [Docker Desktop for Windows tips](https://code.visualstudio.com/docs/remote/troubleshooting#_docker-desktop-for-windows-tips) on avoiding common problems with sharing.

    **Linux:**
    1. Follow the [official install instructions for Docker CE/EE for your distribution](https://docs.docker.com/install/#supported-platforms). If you are using Docker Compose, follow the [Docker Compose directions](https://docs.docker.com/compose/install/) as well.
    2- Add your user to the `docker` group by using a terminal to run: `sudo usermod -aG docker $USER`
    3- Sign out and back in again so your changes take effect.

2. Install [Visual Studio Code](https://code.visualstudio.com/)
3. Install the [Remote Development extension pack](https://aka.ms/vscode-remote/download/extension).

**Tips with Git**
- If you are working with the same repository both locally in Windows and inside a container, be sure to set up consistent line endings. See [tips and tricks](https://code.visualstudio.com/docs/remote/troubleshooting#_resolving-git-line-ending-issues-in-containers-resulting-in-many-modified-files) for details.
- If you clone using a Git credential manager, your container should already have access to your credentials! If you use SSH keys, you can also opt in to sharing them. See [Sharing Git credentials with your container](https://code.visualstudio.com/docs/remote/containers#_sharing-git-credentials-with-your-container) for details.

# Quick start development:
Let's start by cloning this project to try things out.

1. Clone this repository.

    `git clone https://github.com/vortegon/ansible-azcli-docker-dev-env.git`

2. Start VS Code and click on the quick actions Status Bar item in the lower left corner of the window.

    <IMG  src="https://code.visualstudio.com/assets/docs/remote/common/remote-dev-status-bar.png"  alt="Quick actions Status bar item"/>

3. Select **Remote-Containers: Open Folder in Container...** from the command list that appears, and open the root folder of the project you just cloned.

4. The window will then reload, but since the container does not exist yet, VS Code will create one. This may take some time, and a progress notification will provide status updates. Fortunately, this step isn't necessary the next time you open the folder since the container will already exist.

   <IMG  src="https://code.visualstudio.com/assets/docs/remote/containers/dev-container-progress.png"  alt="Dev Container Progress Notification"/>

5. After the container is built, VS Code automatically connects to it and maps the project folder from your local file system into the container.

6. Open the terminal in vscode, you can notice now that you are working directly inside the container and you have available **Ansible** and the **Azure CLI**.

    <IMG  src="https://raw.githubusercontent.com/vortegon/ansible-azcli-docker-dev-env/master/doc/assets/6.png"  alt="Container connection successfull"/>

7. Now you can try an Azure deployment by running an Ansible Playbook.

    <IMG  src="https://raw.githubusercontent.com/vortegon/ansible-azcli-docker-dev-env/master/doc/assets/7.png"  alt="Container connection successfull"/>

8. Star this github repo :smile:

-------------

Enjoy!
I'm always happy to hear your feedback.
