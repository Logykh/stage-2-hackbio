**Authors:** Logy Khaled (@Logy), Alaa Hewela (@Alaa253), Rahma mamdouh Mohammed (@Rahmamam2000), Melvin Khakabo (@MELmostly), Tawfek Ahmed Tawfek (@Tawfekahmed25)

**GithubRepo:**

https://github.com/Logykh/hackbio-cancer-internship

**Goal**

This analysis aimed to visualize differential gene expression in a glioblastoma dataset using heatmaps and interpreting functional enrichment analysis results to identify the top biological pathways associated with this cancer.

.  
**Visualization of the data**

At first, we made a heatmap in R using the function (heatmap.2) of the package (gplots) that had clustered columns, since the columns represent the samples, this was done to identify the pattern of gene expression and know how to group the samples together.

**Heatmap with diverging color palette**   
\!\[1\](https://github.com/user-attachments/assets/61e72bb3-7d66-476d-a999-a858b6562bd8)

**Diverging color palettes** highlight extremes of expression using two colors, allowing us to identify samples with similar gene expression patterns for grouping. This aids in calculating fold change and p-values. The heatmap indicates which genes are upregulated or downregulated in each sample, with red representing highly expressed genes.

**Heatmap using sequential color palette**

\!\[2\](https://github.com/user-attachments/assets/07cf7d8e-bccd-4ce6-9fe8-caebeecb7d1d)

**Sequential color palette** visualizes continuous value gradients, ideal for representing data from low to high without a clear midpoint. This aids in understanding the magnitude of changes in gene expression.

**Using the diverging color palette is more significant in visualizing this dataset.**

**Variants of the heatmap:**

**With clustering of rows (genes)**

\!\[3\](https://github.com/user-attachments/assets/ec2752a2-9a2e-4a78-a7c6-6f027182af29)

**With clustering of columns (samples)**

\!\[Rplot\](https://github.com/user-attachments/assets/89c90e94-1eac-4f2d-aaf9-3ca01f5e56aa)

**With clustering of rows and columns**

\!\[5\](https://github.com/user-attachments/assets/fee0fcee-bfcb-43e7-b1c3-2233ecae96d6)

**Functional enrichment analysis**

After grouping the samples, we calculated the fold change and p-values, then plotted them to determine the cutoffs.

\!\[6\](https://github.com/user-attachments/assets/da23d1cb-1162-4714-9c2f-9016dc0d1335)

Since there is a clear distinction between positive and negative, we set the log2 fold change cutoff to 1 and the p-value cutoff to 2 to include all genes for better results.  
**Upregulated genes** have **a positive log2 fold change** and **a significant p-value**.

**Downregulated genes** have **a negative log2 fold change** and **a significant p-value**.  
After subsetting the upregulated and downregulated genes, we ran functional enrichment analysis using ShinyGo to identify the top pathways involved.

**The results were then plotted as lollipop plot **  

\!\[7\](https://github.com/user-attachments/assets/54ce9d17-1fda-44f8-bf89-90ea0fa3c8cf)

**The top 5 enriched pathways of upregulated genes includes:**   

Cytokine-cytokine receptor interaction, IL-17 signaling pathway, Viral protein interaction with cytokine and cytokine receptor, JAK-STAT signaling pathway, Malaria

Cytokine signaling is crucial for immune regulation and tumor progression. The IL-17 pathway promotes inflammation and immune cell recruitment, contributing to tumor growth and poor prognosis. The viral protein interaction pathway suggests potential viral influences that may alter immune responses. Dysregulation of these pathways supports a tumor microenvironment that facilitates immune evasion and progression in glioblastoma, highlighting the complex interplay between immune signaling and tumor biology.