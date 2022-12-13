---
layout: default
title: Data visualization
parent: Data work guides
nav_order: 3
---

# Data visualization guide
{: .no_toc }

1. TOC
{:toc}

---

## Saving visualizations

### Export visualizations in a reproducible manner

### Choosing file formats

**You should probably save your data visualizations in one of three formats: PDF, SVG, or PNG.** In general, it's preferable to start with a high-resolution image and compress it so the file is not as heavy, since recovering image quality from a compressed file is much harder, if not impossible.

The three most commonly used formats to save images are PNG, JPG, and PDF. PNG and JPG are raster or bitmap formats, which means they store images as a collection of pixels in assigned coordinates. PNG files will maintain the quality of the image and its original file size, while JPG files compress images, reducing file size, but also image quality. JPG is a great format for pictures, but not as much for graphs, where it is important to visualize sharp edges in features (for example, to see lines clearly). Since data visualizations will typically not contain as much detail as pictures, PNG files should be preferred over JPG. If you need a lighter version of a file, for example to share it over a bad internet connection, there are easily accessible tools to convert PNG to JPG.

PDF files (and SVG, EPS), on the other hand, store images as vectors. So it will process your visualizations as a set of separate geometric figures. The main advantage of vector over raster formats is that they are resolution-independent, meaning zooming in will not result in loss of detail. Vector formats are great if you have a small set of geometric figures, for example line graphs, bar charts, or maps with a limited number of data points. However, these formats can result in larger file sizes and longer rendering times if there is a large number of elements to load -- think of a heatmap or scatter plot with many data points. Additionally, using custom fonts can create issues with vector images, since the fonts need to be available in each software or computer used to render the image to be displayed as intended. PDF is the most widely used vector format, and it is optimized for printing, while SVG creates smaller files, and is ideal for web images.

**In short, PDF files are best suited to save graphs for printing, SVG to save them for web use, and high-resolution PNG to save graphs with many different elements.** If you are using git to version control images, however, there are additional considerations to make. Raster images are saved as binary files. This means they are not tracked as efficiently as plain-text files. However, GitHub has a [neat feature](https://github.blog/2011-03-21-behold-image-view-modes/) that allows users to view changes in raster images. SVG files can also be tracked, but changes will be viewed in git as changes to the underlying XML file (a plain-text file), and not the image itself. Finally, changes in PDF will not be visible. Instead, git will only indicate whether changes were made to the file or not.