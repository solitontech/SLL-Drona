# GitHub Release Package  

## Steps:  


1. On the right side of the window, under Releases, select 'Create a new release'.  

![GitHub Page](Images/GitHub%20Page.png)  

2. GitHub 'Create a new release' page has the following details that need to be filled.  

![GitHub Create Release](Images/GitHub%20Create%20Release.png)  

3. **Choose a Tag** - A new release tag needs to be set for every release. Create a new release tag with standards such as v0.1.0 or v1.2.4  

4. **Target** - The main branch is set as the default branch for target. It is always good to have the main branch as the target branch for the release.  

5. **Release Title** - Set the title for the release package. It is good to have the name of the software along with the release tag in the release title. e.g. SLL Drona v0.3.0 

6. **Description** - Mention the changes that are removed / added / optimized in this newer release.  

7. **Drop Package** - Add your release packages in the 'Attach binaries by dropping them here or selecting them'. For SLL Drona add the package that is built from VIPM. (For building the SLL Drona Package, you can refer [here](BUILD.md)).

8. **Pre-Release** - If the software production is not completely ready, then enable this 'pre-release' option. This results in displaying this release as pre-release state in the GitHub Release page.  

9. Sample GitHub Release Template for SLL Drona:  

![GitHub Release Template](Images/GitHub%20Release%20Template.png)  

10. **Publish Release** - Once all the required details are provided, then select the 'Publish Release' button to publish a new release.  

11. On the successful completion of package release, then the release will display under GitHub Release page.  

![GitHub Released Package](Images/GitHub%20Released%20Package.png) 
