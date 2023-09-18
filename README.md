# DIL Analytics Manual

Repository featuring DIL Analytics Manual and its associated documents. To access the manual, go to [devinnovationlab.github.io/guides/](https://devinnovationlab.github.io/guides/).

## How to contribute

To make a suggestion, create an [issue](https://github.com/DevInnovationLab/guides/issues). To make direct contributions, create a fork, make your edits to the `gh-pages` branch, and open a pull request.

## Internal vs. External Documents

Everything that is on the gh-pages branch is on the website and thus external. From there we link to internal documents (on the DIL git) if necessary.

# File Structure

Proposed file structure to host all DIL "educational documents" and important example code from past DIL projects.

```
gh-pages branch       # DIL Analytics Manual
├── Principles of Analytics
├── Coding Guides # Detailed articles with general code snippets
│   |── Power calculations/ 	#
│   │   ├── Covariates
│   │   ├── ICC      	
│   │   ├── Panel RCT
│   │   ├── stratification
│   │   ├── Multiple Hypotheses Testing
├── DIL templates
├── External resources

main branch           # Root directory for lab guides
├── power_calc/       	# High-level document summarizing power calculations @ DIL (including step-by-step guidlines for project specific notebooks)
│   ├── shiny/       	# An interactive app that showcases all essential examples
│   ├── examples/     	# Example documents with replication that showcase power calculations from past DIL projects
│   ├── presentations/  # Slides for presentations on power calculations
│   ├── topics/         # Detailed articles are linked in the main power_calc document and are stored in this folder (all as Notebooks)
│   │   ├── covariates/ 	#
│   │	│   ├── examples/   	# Example notebooks for ICC estimation from prior projects and datasets
│   │   ├── ICC/        	#
│   │	│   ├── examples/   	# Example notebooks for ICC estimation from prior projects and datasets
│   │   ├── panel_RCT/      #
│   │	│   ├── examples/   	# Example code that illustrates power calculations 
│   │   ├── stratification/ #
│   │	│   ├── examples/   	# Example code stratification / matching
│   │   ├── multip_testing/ # MHT corrections
│   │	│   ├── examples/   	# Example code MHT
├── spatial/			# GIS @ DIL (in progress)

```
