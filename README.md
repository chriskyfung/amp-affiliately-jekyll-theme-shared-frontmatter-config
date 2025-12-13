# ⚙ Shared Front Matter CMS Configurations for AMP Affiliately Jekyll Theme


[![GitMCP](https://img.shields.io/endpoint?url=https://gitmcp.io/badge/chriskyfung/amp-affiliately-jekyll-theme-shared-frontmatter-config)](https://gitmcp.io/chriskyfung/amp-affiliately-jekyll-theme-shared-frontmatter-config) ![GitHub last commit](https://img.shields.io/github/last-commit/chriskyfung/amp-affiliately-jekyll-theme-shared-frontmatter-config)

This repository provides a standardized and shared set of Front Matter CMS configurations specifically designed for projects utilizing the [AMP Affiliately Jekyll Theme](https://chriskyfung.github.io/amp-affiliately-jekyll-theme/). By integrating this repository as a Git submodule, you can centralize your CMS settings, ensuring consistency and ease of management across multiple Jekyll sites.

## ✨ Features & Benefits

*   **Centralized Configuration:** Manage all your Front Matter CMS settings from a single source.
*   **Consistency Across Projects:** Ensure all your AMP Affiliately Jekyll Theme projects use the same CMS configurations.
*   **Simplified Updates:** Update configurations once in this repository, then easily sync across all linked projects.
*   **Improved Collaboration:** Streamline development workflows when multiple team members are working on different sites sharing the same structure.

## 🚀 Parent Project: AMP Affiliately Jekyll Theme

This shared configuration is built to complement the [AMP Affiliately Jekyll Theme](https://chriskyfung.github.io/amp-affiliately-jekyll-theme/). This theme is an AMP-ready Jekyll theme that prioritizes performance and mobile-friendliness, and can be easily installed as a remote theme. It offers deep integration with [Front Matter CMS](https://chriskyfung.github.io/amp-affiliately-jekyll-theme/front-matter-cms/) for a seamless editing experience within VS Code. 👨‍💻

*   [**Theme Website**](https://chriskyfung.github.io/amp-affiliately-jekyll-theme/)
*   [**Theme GitHub Repository**](https://github.com/chriskyfung/amp-affiliately-jekyll-theme)

## ⚡ What is AMP?

**AMP** (Accelerated Mobile Pages) is an open-source initiative designed to enable the creation of websites and ads that are consistently fast, beautiful, and high-performing across devices and distribution platforms. Learn more at the official [AMP Project website](https://www.ampproject.org/) ↗.

## 🛠️ Installation Guide

To integrate these shared configurations into your existing AMP Affiliately Jekyll Theme project, follow these steps:

### Prerequisites

Before proceeding, ensure you have:

*   An existing Jekyll project using the AMP Affiliately Jekyll Theme.
*   [Git](https://git-scm.com/) installed and configured.
*   Familiarity with [Git submodules](https://git-scm.com/book/en/v2/Git-Tools-Submodules).

### Step 1: Remove Existing Configurations (If Applicable)

If your existing project already contains a `.frontmatter/config` directory with local configurations, it is recommended to remove it before adding the shared submodule to avoid conflicts. This step effectively extracts your local `.frontmatter/config` into this shared submodule approach.

```bash
# Navigate to your original project repository
cd /path/to/your-original-project

# Remove the local configuration directory and commit the change
git rm -r .frontmatter/config
git commit -m "chore: extract .frontmatter/config to shared submodule"
git push
```

### Step 2: Add Shared Configuration as a Git Submodule

Add this repository as a Git submodule, ensuring it is mounted at the exact path `.frontmatter/config` where Front Matter CMS expects to find its configuration files.

```bash
# From your project root, add the submodule
git submodule add https://github.com/chriskyfung/amp-affiliately-jekyll-theme-shared-frontmatter-config.git .frontmatter/config

# Commit the submodule reference to your project
git commit -m "chore(frontmatter): add shared cms config as submodule"
git push
```

Upon successful execution, your project's `.gitmodules` file will be updated to reflect the new submodule:

```text
[submodule ".frontmatter/config"]
    path = .frontmatter/config
    url = https://github.com/chriskyfung/amp-affiliately-jekyll-theme-shared-frontmatter-config.git
```

### Step 3: (Optional) Bulk Migration Script

For managing multiple projects, you can automate the submodule integration using a script. This example demonstrates how to add the shared configuration to several projects:

```bash
for project in project-a project-b project-c; do
  cd $project
  git submodule add https://github.com/chriskyfung/amp-affiliately-jekyll-theme-shared-frontmatter-config.git .frontmatter/config
  git commit -m "chore(frontmatter): add shared cms config submodule"
  git push
  cd .. # Navigate back to the parent directory if iterating
done
```

**Result:** All specified projects will now reference the same configuration files via Git submodule pointers. To synchronize updates from this shared repository, simply run `git submodule update --remote` within each project.

### Step 4: Verify Installation

Confirm that the shared configurations are correctly detected by Front Matter CMS:

1.  **Clone with Submodules:** If cloning a fresh project that uses this submodule, ensure you initialize and update submodules:

    ```bash
    git clone --recurse-submodules https://github.com/your-org/project.git
    # OR, if cloned without --recurse-submodules:
    git submodule update --init --recursive
    ```
2.  **Open in VS Code:** Launch VS Code and open your project.
3.  **Check Front Matter Settings:** Within VS Code, open the Front Matter CMS extension and navigate to its settings. You should observe that the configurations from `.frontmatter/config` are now loaded and available.

## 📚 Usage & Front Matter Variables

For comprehensive guidance on using Front Matter variables for posts, pages, and other content types within the AMP Affiliately Jekyll Theme, please refer to the official [**Front Matter Guide**](https://chriskyfung.github.io/amp-affiliately-jekyll-theme/front-matter-guide/) ↗.

---

## 🤝 Contributing

We welcome contributions to enhance these shared configurations. Bug reports and pull requests are encouraged on [GitHub](https://github.com/chriskyfung/amp-affiliately-jekyll-theme-shared-frontmatter-config/) ↗. This project adheres to the [Contributor Covenant](http://contributor-covenant.org) ↗ code of conduct, fostering a safe and welcoming space for collaboration.

To submit a pull request:

1.  **Fork** and clone the repository.
2.  **Create a new branch** from `main` for your changes.
3.  **Develop** your features or bug fixes.
4.  **Open a pull request** on GitHub, providing a clear description of your changes.

## 💗 Support My Work

If you find this project helpful and would like to support the ongoing development of the AMP Affiliately Jekyll Theme and its related tools, consider buying me a coffee!

<a href="https://www.buymeacoffee.com/chrisfungky"><img src="https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png" alt="Buy Me A Coffee" style="height: 41px !important;width: 174px !important;box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;-webkit-box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;" target="_blank"></a>

## ⚖️ License

This project is open-source and available under the terms of the [MIT License](https://opensource.org/licenses/MIT) ↗. This aligns with the license of its [upstream parent theme](https://github.com/chriskyfung/amp-affiliately-jekyll-theme/blob/main/LICENSE).
