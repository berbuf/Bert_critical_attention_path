# Bert_critical_attention_path

With a technique called critical data routing path [Interpret Neural Networks by Identifying Critical Data Routing Paths](http://openaccess.thecvf.com/content_cvpr_2018/papers/Wang_Interpret_Neural_Networks_CVPR_2018_paper.pdf), we prune non-effective attention heads one inference at a time with masked language modeling on Bert Base.

### Critical attention path with gate control
![Alt text](./resources/schema_mlm.png?raw=true "Title")

Results tells that from first to last layers there is a correlation between magnitude of gates (a), entropy (b) and distance to the token most attended (c):

### A) Mean magnitude of activated gates by layers
![Alt text](./resources/magnitude.png?raw=true "Title")
### B) Mean entropy multiplied with mean gate magnitude by layers
![Alt text](./resources/entropy.png?raw=true "Title")
### C) Mean distance to most attended token multiplied with mean gate magnitude by layers
![Alt text](./resources/distance.png?raw=true "Title")

This network also tends to focus more and more on content words:

### Growth of attention for content words through the network 
![Alt text](./resources/content.png?raw=true "Title")

### Global visualization
![Alt text](./resources/viz.png?raw=true "Title")

The last image can be generated from any sentence input inside the notebook [visualization](./visualization.ipynb).

