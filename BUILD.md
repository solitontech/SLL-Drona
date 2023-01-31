# VIPM Package Building
## Steps:
1. Open VI package build file "**Drona.vipb**" placed inside the folder BuildSpec under SLL Drona using VIPM
2. **Source Directory & Build Output Directory** - In Basic category, under Build Information give the SLL Drona Source folder path as the required path for Source Directory. For Build Output Directory give the path preferably having the built package inside a build folder. 
3. **Package version**  - Note that the package version is updated accordingly.
4. **Release Notes** - Mention the changes that are removed / added / optimized in this newer version.
![Build Information](Images/VIPB%20Build%20Info.png)
5. **Palette** - To edit the SLL Drona Palette, go to Palette category and right click on the Palette icon and choose "Edit Palette"
![Palette](Images/VIPB%20Palette.png)
6. **Package Dependencies** - Update if there are any new dependencies added or removed in SLL Drona
![Package Dependencies](Images/VIPB%20Package%20Depen.png)
7. **Package Filename** - Ensure the package name is proper with correct build version number
![Package Filename](Images/VIPB%20Package%20filename.png)
8. Click on "Build Package" to start building the SLL Drona package <br/>
![Build Package](Images/VIPB%20Build%20package%20icon.png)