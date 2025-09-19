
 # An Innovative ISO-Based Computational Framework for Software Maintainability Assessment

The **QualCode** system combines ISO/IEC 25010 quality subcharacteristics with machine learning models to assess software maintainability across dimensions such as modularity, testability, reusability, analyzability, and modifiability. This repository provides tools and data for exploring and reproducing the visual and analytical components of our system.

# Repository Structure

├── docs/images/ # UI screenshots and figures used in the paper (Section 6)  
├── data/ # Benchmark datasets used for training and evaluation  
├── results/ # Output results, processed metrics, and analysis outputs  
└── README.md # This file


# QualCode Visualization

This repository contains the visual interface elements and screenshots of our research paper entitled "An Innovative ISO-Based Computational Framework for Software Maintainability Assessment". These visuals demonstrate the analysis and visualization capabilities of the **QualCode** system.
The QualCode system offers diverse perspectives on the status of software components. The provided analysis details and impactful metrics for each subcharacteristic are viewable in suitable chart formats within the QualCode system. (Figure 1). The version analysis page provides an initial overview of the status of the five primary subcharacteristics, offering insights into the project's overall condition. In the sidebar tab, users can access detailed analysis information for each of these subcharacteristics.

# User Guide and Practical Usage Scenario

Below, we provide a textual summary of the most important operations, focusing on project analysis.

**Creating a New Project**
To create a new project, go to the main dashboard and click on the Projects menu item to access the project list page. This page displays all projects in which you are an owner or have a role. Click the “New Project” button in the top-right corner to open the project creation window.There are three ways to create a new project:
Manual creation: Enter the project title manually.
GitLab import: Provide the GitLab platform URL, project ID, and access token obtained from GitLab.
GitHub import: Enter the project URL. Unlike GitLab, no project ID is required.

**Project Profile**
Clicking on a project from the list opens its profile page, showing project details along with visualizations of the overall version and project status. Additional metrics for each version are displayed as timeline charts, including lines of code, number of classes, and number of packages. All charts can be exported in common formats (image, Excel, SVG).

**Uploading a Version**
Project files are uploaded to QualCode by version. To manage versions, click on the desired project to open its profile page, then go to the Versions tab. The list of existing versions will be displayed. To create a new version, click “New Version”. Similar to project creation, there are three ways to add a version:

- **Manual:** Enter the version identifiers (Major, Minor, Patch), upload the version files, and click Create Version.  
- **GitLab import:** If no token was provided during project creation, enter it in the project settings under access settings. Then complete the version identifiers, select the branch and commit, and click Create Version.  
- **GitHub import:** Follows the same procedure as GitLab, but only the project URL is required.  

**Analyzing a Version**
To analyze a version, go to the project’s Versions page, select the desired version, and click Analyze from the operations menu. Analysis time depends on project size and may range from a few seconds to several hours. Each version can have four statuses:

- **Not Analyzed:** Version uploaded but not yet analyzed.  
- **Analyzing:** Version is currently being analyzed.  
- **View Analysis:** Analysis completed and results are available.  
- **Analysis Failed:** An error occurred during analysis.  

**Viewing Analysis Results**
If a version’s status is View Analysis, click the corresponding button or select View Analysis from the operations menu to see the results. The analysis page first presents a summary of the five main subcharacteristics, showing the overall project status (Figure 1). Detailed results for each subcharacteristic are available in the sidebar tab.

![Figure 1](./docs/images/callgraph.png)
**Figure 1: Call graph of project classes**

**Modularity:** Regarding modularity, QualCode provides a visual representation of component call graphs, fostering in-depth exploration through interactive features such as clicking on graph nodes (illustrated in Figure 2). 

![Figure 2](./docs/images/callgraph-click.png)
**Figure 2: Call graph of project classes**

Furthermore, the system employs heatmaps to visually depict subcharacteristic values, which can be traced down to the class level. Each mosaic in this heatmap represents a class or package. Notably, these heatmaps offer the capability to reveal influential metric values through a simple hover-over interaction (refer to Figures 3 to 6). For instance, in Fig.9, hovering the mouse pointer over a mosaic displays the testability metrics associated with that mosaic. Additionally, the color of each section indicates the quality score for testability in that section.



**Testability:** Displays the project’s class call graph. Each node represents a class, and each edge represents a relationship between two classes.

![Figure 3](./docs/images/testability-heatmap.png)
**Figure 3: Testability heatmap and display of its metrics down to the class level**

![Figure 4](./docs/images/reusability-heatmap.png)
**Figure 4: Reusability heatmap and display of its metrics down to the class level**

**Modifiability:** Shows a tree-heatmap visualization for files and packages. Each tile represents a class or package, and hovering over a tile displays its associated modifiability metrics. The color indicates the quality score of that component.
Clicking on a tile (if it represents a package) drills down to show the classes and sub-packages within it. This drill-down approach is available for all metrics, enabling detailed exploration of results.

![Figure 5](./docs/images/modifiability-heatmap.png)
**Figure 5: Modifiability heatmap and display of its metrics down to the class level**

![Figure 6](./docs/images/analyzability-heatmap.png)
**Figure 6: Analyzability heatmap and display of its metrics down to the class level**

Lastly, QualCode enhances the understanding of software quality by presenting detailed tables showcasing modifiability and analyzability metrics, further aiding users in their assessment and decision-making processes (demonstrated in Figures 7 and 8).

![Figure 7](./docs/images/modifiability-details.png)
**Figure 7: Details of modifiability**

![Fig 8](./docs/images/analyzability-details.png)
**Figure 8: Details of analyzability**


#  Datasets

You can find the datasets used for model training and evaluation in the [`data/`](data/) directory. 

#  Results
The [`results/`](results/)  directory contains extended results that complement the findings reported in the paper. This includes detailed evaluation scores, benchmark comparisons (e.g., against SonarQube and UND), project-level results summarized in the main text, as well as the full user acceptance test (UAT) documentation for the QualCode user interface.
