## Introduction

This document provides a comprehensive guide for developing and deploying the WordPress site for our client using custom themes and AWS LightSail. The goal is to ensure that anyone new to the project can follow the workflow and successfully contribute to the development and deployment processes.

## Summary of Tools Used

- **CMS**: WordPress
- **Documentation and Team Management**: Trello, Miro
- **Communication**: Discord, WhatsApp,Slack
- **Local Environments & IDE**: Visual Studio Code
- **Version Control**: GitHub

### Trello
Trello is a web-based task management tool that we used to track tasks and project progress. New members can join the board using the link: [Trello Board](https://trello.com/invite/b/668f679767732ecb39846fc4/ATTI59095d56f35e912d7102f69c276dc8802A62BE6D/cp3402-cms-assignment-2-baizonn-learning-center). All tasks, both completed and pending, are listed here.

### Miro
Miro is an online collaborative whiteboard platform used to keep track of meetings and work progress. Join the board using the link: [Miro Board](https://miro.com/app/board/uXjVKuCLVeA=/?share_link_id=123745175472).

### Discord
Discord is used for team communication. It supports text, voice communication, file sharing, and link uploads, which are essential for staying updated on project developments.

### WhatsApp
WhatsApp is used for quick, on-the-go communication. It supports text, voice calls, file sharing, and screen-sharing, making it convenient for immediate updates and collaboration.

### Slack
Slack is another communication tool used for this project. It offers a platform for organized conversations, file sharing, and integration with other tools we use.

### Local Environments & IDE
- **Visual Studio Code**: Preferred IDE for editing PHP, CSS, and other code files.

### Version Control
- **GitHub**: Version control and collaboration platform. We use multiple branches: Main, Staging, and Development. Changes are made in new branches, reviewed, and then merged.

## Environment Setup

### Setting Up Local Environment
1. **Set Up WordPress**: Install WordPress
3. **Visual Studio Code**: Download and install Visual Studio Code from [VS Code](https://code.visualstudio.com/).

### Setting Up Version Control
1. **GitHub Repository**: Create or join the GitHub repository.
2. **Clone Repository**: Clone the repository to your local machine.
    ```bash
    git clone https://github.com/cp3402-students/project-group-c-work-buster.git
    ```
3. **Set Up Local Git**: Connect your local repository with GitHub.

## Development Workflow

1. **Create a New Branch**: Start by creating a new branch for your changes.
    ```bash
    git checkout -b feature-branch
    ```
2. **Make Changes**: Develop and test your changes locally.
3. **Commit Changes**: Commit your changes with a descriptive message.
    ```bash
    git add .
    git commit -m "Description of changes"
    ```
4. **Push to GitHub**: Push your branch to GitHub.
    ```bash
    git push origin feature-branch
    ```
5. **Pull Request**: Create a pull request to merge your changes into the Development branch. Have other team members review it.

## Deployment Workflow

### AWS LightSail Setup
1. **Create LightSail Instance**: 
    - Go to AWS LightSail and create a new instance.
    - Select Singapore as the location.
    - Choose WordPress as the platform.
    - Select the 2GB RAM plan.
2. **Set Up Static IP**: Allocate and attach a static IP to the instance.
3. **Retrieve Password**: Get the application password.
    ```bash
    cat bitnami_application_password
    ```
4. **Access WordPress**: Log in to the WordPress admin panel using the static IP and password.

### Deploying Changes
1. **Merge to Staging**: Merge the changes from the Development branch to the Staging branch for testing.
2. **Test on Staging**: Verify all changes on the staging environment.
3. **Merge to Main**: Once verified, merge the Staging branch into the Main branch.
4. **Deploy to Production**: Pull the latest changes on the production server.

    ```bash
    ssh user@your-server-ip
    cd /path/to/your/project
    git pull origin main
    ```

## Verification

- **Check Site**: Verify the site is live and functioning as expected.
- **Logs**: Check server and application logs for errors.
- **Functionality**: Ensure all features and plugins are working correctly.

## Rollback Procedure

1. **Revert Changes**: If an issue arises, revert to the previous stable commit.
    ```bash
    git revert <commit-id>
    ```
2. **Redeploy**: Deploy the reverted changes to the production server.
    ```bash
    git push origin main
    ```

## Troubleshooting

- **Logs**: Check logs for errors and warnings.
- **Environment Variables**: Ensure all environment variables are correctly set.
- **Database**: Verify database connections and integrity
