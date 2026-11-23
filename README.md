# Guide to attach cluade code app to GitHub
This repo gives a guide to attaching cluade code to your git repo

## Connecting Claude Code to GitHub

Follow these steps to install the Claude GitHub App and enable automated workflows (such as `@claude` mentions in issues and pull requests) for this repository.

### Prerequisites
* **Repository Admin Access:** You must be an admin of this GitHub repository.
* **Claude Account:** An active Claude Pro, Max, or Anthropic API account.
* **Claude Code CLI:** Installed locally on your machine.
* **GitHub CLI (`gh`):** Installed and authenticated (`gh auth login`).

### Step-by-Step Setup

1. **Open your project in the terminal**
   Navigate to the root folder of your local repository and launch Claude Code:
   ```bash
   cd /path/to/your-repo
   claude
   ```

2. **Run the GitHub App installer command**
   Inside the Claude Code interactive prompt, type the following slash command and press **Enter**:
   ```text
   /install-github-app
   ```

3. **Install and authorize on GitHub**
   * Claude Code will open your default web browser to the [Claude GitHub App](https://github.com/apps/claude) page.
   * Click **Install** (or **Configure**).
   * Select your GitHub account or organization.
   * Under **Repository access**, select **Only select repositories** and choose this repository from the dropdown.
   * Click **Install & Authorize**.

4. **Configure workflows and authentication**
   * Return to your terminal and press **Enter** to continue.
   * Select the GitHub Actions workflows you want to install (e.g., responding to `@claude` mentions and automated PR reviews) and press **Enter**.
   * Choose your authentication method:
     * **Claude Pro/Max Subscription:** Select the option to generate a long-lived OAuth token (`CLAUDE_CODE_OAUTH_TOKEN`) and complete the browser login prompt.
     * **Anthropic API:** Enter your `ANTHROPIC_API_KEY` when prompted.
   * Claude Code will automatically add the required secret to your repository's GitHub Actions settings.

5. **Merge the setup Pull Request**
   * Claude Code will generate a pull request containing the new `.github/workflows/` YAML configuration files.
   * Open the PR link provided in your terminal, review the workflow files, and click **Merge pull request** on GitHub.

### Usage
Once merged, you can tag `@claude` in any GitHub issue or pull request comment to ask questions, request code changes, or trigger automated reviews.
