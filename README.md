# Setting Up a Development Environment for the PFX Pipeline

This guide provides comprehensive instructions for setting up a development environment tailored to the PFX Pipeline. It includes installing necessary software, creating virtual environments, configuring tools, and organizing your workspace to ensure efficient development and integration with the PFX Pipeline infrastructure.

## Install Required Software

To begin, you'll need tools for version control, an IDE for Python development, and the appropriate Python versions. Follow these steps to install and configure the required software.

1. **Git Client (e.g., SourceTree)**
   
   - **SourceTree**: A user-friendly Git client with a graphical interface for managing repositories.
   
   - [Download SourceTree](https://www.sourcetreeapp.com/) and follow the installation instructions.
     
     > Alternatively, you can use other Git tools or the Git command-line interface if preferred.

2. **PyCharm**
   
   - **PyCharm** is a powerful IDE tailored for Python development, offering features like debugging, code navigation, and virtual environment management.
   - [Download PyCharm](https://www.jetbrains.com/pycharm/)
   - Install and follow the installation instructions.

3. **Required Python Versions**
   
   - Visit [Python's official website](https://www.python.org/downloads/) and download the required versions: 3.7, 3.9, 3.10, and 3.11.
   - Ensure you download the correct version for your operating system (Windows 64-bit).
   - Install each Python version one by one. During installation:
     - Choose the **Customize installation** option.
     - Set the installation path to `C:\PythonXX` (e.g., `C:\Python37` for Python 3.7).
     - For all versions, uncheck the "Add Python to PATH" option during installation.

## Setting Up the Development Folder and Connect Repositories

1. **Create Personal Development Folder**
   
   - Navigate to the `R` drive and locate the `prod` folder.
   
   - Copy the `prod` folder and paste it in the root of the `R` drive.
   
   - Rename the copied folder using a three-letter abbreviation of your name (e.g., `jdo` for John Doe).
     
     This will serve as your isolated development environment.

2. **To-Do: SSH Setup**

3. **Setting Up Repositories in SourceTree**
   
    To start working with the repositories within the copied folder, you need to add them to your Git client (e.g., SourceTree) and ensure they are properly linked with GitLab and GitHub.
   
    Below is the list of repositories that are part of the `prod` folder:
   
   - **GitLab (https://github.com/pfxtv):**
     
     - `R:\jdo\wind`
   
   - **GitHub (https://gitlab.com/currentpipe):**
     
     - `R:\jdo\studio\studio_library`
     - `R:\jdo\studio\sc`
     - `R:\jdo\studio\blender`
     - `R:\jdo\studio\clarisse`
     - `R:\jdo\studio\equalizer`
     - `R:\jdo\studio\hiero`
     - `R:\jdo\studio\houdini`
     - `R:\jdo\studio\max`
     - `R:\jdo\studio\maya`
     - `R:\jdo\studio\nuke`
     - `R:\jdo\studio\painter`
     - `R:\jdo\studio\resolve`

4. **Add Repositories to SourceTree**
   
   For each repository in the list:
   
   - Open SourceTree and click **Add**.
   
   - Point SourceTree to its local directory in your development folder and click **Add**
     
     ![source_tree_1.png](https://raw.githubusercontent.com/jenglichPFX/install_doc/refs/heads/main/doc/source_tree_1.png)
   
   - Navigate to **Repository > Repository Settings > Add** 
   
   - Add the corresponding GitLab/GitHub URL to the Remote details and click **OK**.
     
     ![source_tree_2.png](https://raw.githubusercontent.com/jenglichPFX/install_doc/refs/heads/main/doc/source_tree_2.png)

5. **Pull the Latest Changes**
   
   - For each repository added to SourceTree, select the repository and click **Pull** to fetch the latest updates from the remote origin.

## Create a PyCharm Project and Interpreters

1. **Create a PyCharm Project**
   
   - Launch PyCharm and select **New Project** from the welcome screen. If PyCharm is already open, go to **File > New Project**.
   - In the **New Project** dialog, set the project location to: `C:\Users\john.doe\pipeline_dev`

2. **Create a New Virtual Environment**
   
   - Under the **Python Interpreter** section, select **Custom Environment**.
   
   - Choose **Generate New > Type: Virtualenv**.
   
   - For **Base Python** choose `C:\Python37\python.exe`.
   
   - Set the **Environment Location** to: `C:\Users\<YourName>\pipeline_dev\.venv\python37`.
   
   - Ensure the **Inherit global site-packages** option is unchecked for a clean environment.
     
     ![pycharm_1.png](https://raw.githubusercontent.com/jenglichPFX/install_doc/refs/heads/main/doc/pycharm_1.png)

3. **Complete Project Setup**
   
   - Click **Create** to initialize the project and virtual environment. PyCharm will set up the environment and link it to the project.

4. **Open Interpreter Settings**
   
   - Navigate to **File > Settings > Project: [pipeline_dev] > Python Interpreter**.
   
   - Click **Add interpreter** next to the Python Interpreter and select **Add Local Interpreter**.
   
   - Create a virtual environment with the above settings adjusted for Python 3.9, 3.10, and 3.11.
     
     ![pycharm_2.png](https://raw.githubusercontent.com/jenglichPFX/install_doc/refs/heads/main/doc/pycharm_2.png)

5. **Creating a Python 2.7 Virtual Environment Manually**
   
   - Due to compatibility issues, PyCharm may encounter errors when attempting to create a virtual environment for Python 2.7. To address this, you can manually create the virtual environment and then configure PyCharm to use it.
   
   - Create a virtual environment named `python27` by running:
     
     ```
     C:\Python27\python.exe -m virtualenv C:\Users\john.doe\pipeline_dev\.venv\python27
     ```
   
   - Add `C:\Users\<YourName>\pipeline_dev\.venv\python27\Scripts\python.exe` to your PyCharm interpreters by choosing **Add interpreter > Select Existing**.

>  You should now have a virtual environment for each required Python version added as an interpreter in your PyCharm project. This setup ensures that you can seamlessly switch between different Python versions as needed.

![pycharm_3.png](https://raw.githubusercontent.com/jenglichPFX/install_doc/refs/heads/main/doc/pycharm_3.png)

## Attach Folders to PyCharm Project

1. **Attach Development Folder**
   
   - Navigate to **File > Open...**.
   - In the dialog that appears, browse to the `R` drive and select your development folder (e.g., `R:\jdo`).
   - When asked how you would like to open the project, choose **Attach**.

2. **Do the Same for `R:\DEADLINE10_REPO\custom`**
   
   ![pycharm_4.png](https://raw.githubusercontent.com/jenglichPFX/install_doc/refs/heads/main/doc/pycharm_4.png)

## Mark Folders

1. **Open Project Structure Settings**
   
   - Navigate to **File > Settings > Project: [pipeline_dev] > Project Structure**.

2. **Mark `pipeline_dev` Subfolders**
   
   - Mark the `pipeline_dev` folder itself as **Excluded**.
     
     ![pycharm_5.png](https://raw.githubusercontent.com/jenglichPFX/install_doc/refs/heads/main/doc/pycharm_5.png)
   
   **Mark Deadline Subfolders**
   
   - Mark the `pipeline_dev` folder itself as **Excluded**.
     
     ![pycharm_6.png](https://raw.githubusercontent.com/jenglichPFX/install_doc/refs/heads/main/doc/pycharm_6.png)

3. **Mark `jdo` Subfolders**
   
   - Mark `studio` and `wind` as **Sources**.
   
   - Mark `vendor`, `vendor_lin`, `vendor3`, and `vendor3_lin` as **Excluded**.
     
     ![pycharm_7.png](https://raw.githubusercontent.com/jenglichPFX/install_doc/refs/heads/main/doc/pycharm_7.png)

## Add Vendor Folders to Interpreters

1. **Open Interpreter Settings**
   
   - Navigate to **File > Settings > Project: [pipeline_dev] > Python Interpreter > Python Interpreter > Show All**.
     
     ![pycharm_8.png](https://raw.githubusercontent.com/jenglichPFX/install_doc/refs/heads/main/doc/pycharm_8.png)

2. **Add Vendor or Vendor3 to Interpreters**
   
   - For each virtual environment interpreter we created, open up the **Interpreter Paths** by clicking on the **File Tree Icon** above the interpreter list.
   
   - Depending on the Python version being 2 or 3, add `R:\jdo\vendor` or `R:\jdo\vendor3` to the path list and click OK.
     
     ![pycharm_9.png](https://raw.githubusercontent.com/jenglichPFX/install_doc/refs/heads/main/doc/pycharm_9.png)

## Additional: Setting Python Interpreters

1. **Open Interpreter Settings**
   
   - Navigate to **File > Settings > Project: [pipeline_dev] > Python Interpreter**.
   
   - For `Deadline` and `pipeline_dev`, choose **No Interpreter**.
     
     ![pycharm_10.png](https://raw.githubusercontent.com/jenglichPFX/install_doc/refs/heads/main/doc/pycharm_10.png)

> At this stage, your PyCharm project should be configured to display only your development folder in the **Project** window. You can easily switch between different Python interpreters by clicking on the interpreter name located in the bottom-right corner of the PyCharm window. Upon changing the interpreter, PyCharm will automatically load the corresponding environment and its associated vendor packages.

## Conclusion

By following this guide, you’ve successfully set up your development environment for the PFX Pipeline. With all necessary tools installed, repositories configured, and virtual environments created.
Remember to regularly update your repositories and adhere to best practices for version control.

Happy coding, and welcome to the PFX team! 🎉
