# Shared Libraries

In Jenkins, a shared library is a way to store commonly used code(reusable code), such as scripts or functions, that can be used by different 
Jenkins pipelines. 

Instead of writing the same code again and again in multiple pipelines, you can create a shared library and use it in all the pipelines
that need it. This can make your code more organized and easier to maintain. 

Think of it like a library of books, Instead of buying the same book over and over again, you can borrow it from the library whenever you need it.

## Advantages

- Standarization of Pipelines
- Reduce duplication of code
- Easy onboarding of new applications, projects or teams
- One place to fix issues with the shared or common code
- Code Maintainence 
- Reduce the risk of errors

![Screenshot 2023-05-02 at 9 47 24 PM](https://user-images.githubusercontent.com/43399466/235724851-90a5cad6-ac0d-428b-9944-93fffea55180.png)

## How to setup for Shared Library

- Configure Jenkins Global Pipeline Library
Go to Jenkins UI:

- Navigate to Manage Jenkins > Configure System.
Add the Shared Library:

- Scroll down to the Global Pipeline Libraries section.
Click Add to add a new library.
- Configure the Library:

Name: Enter the name of your library (e.g., my-jenkins-library).
Source Code Management: Select Git.
Repository URL: Enter the URL of your Git repository, like https://github.com/anumcait/devops-learning-journey.git.
Credentials: If the repository is private, select or add credentials (e.g., GitHub personal access token or SSH key).
Branch: Set the branch name (e.g., main).

**Note **
If any one create a sub folder for jenkins library (like me), you will get error while building.

I googled and found solution. Below is the solution

![image](https://github.com/user-attachments/assets/c577b1a2-933c-47f4-bd9e-53f7c55e230c)
![image](https://github.com/user-attachments/assets/e3d71188-8507-4be7-af26-740d436c7795)

- Mention sub folder in the Library path at the bottom of the Global Trusted Pipeline Libraries. (default ./ will be existed, change to ./<<your_custom_folder>>
- Ex: ./jenkins

Finally your folder structure look like this:
devops-learning-journey/
├── jenkins/
│   └── vars/
│       └── myVar.groovy  <-- Your Groovy file here
