
### Visualise CSE Results
#### Visualise CSE overlayed on original image

### Commands to run stuff
#### Visualization Command
python apply_net_amogh.py show <config_file> <ckpts_path> <input> dp_vertex -v --output_dir <path_to_output_dir>
python apply_net_amogh.py show configs/cse/densepose_rcnn_R_101_FPN_DL_soft_s1x.yaml checkpoints/human_cse_R_101_FPN_DL_s1x.pkl data/qif_images/ dp_vertex -v --output_dir outputs

#### Dump Results Command
 python apply_net_amogh.py dump configs/cse/densepose_rcnn_R_101_FPN_DL_soft_s1x.yaml checkpoints/human_cse_R_101_FPN_DL_s1x.pkl data/qif_images/ --output_dir outputs

### Commands to change how visualization looks
#### To get just the CSE result, without the underlying image
- Use the same commands as written above to run the scripts. However, make the following changes
- In ```densepose/vis/base.py``` file, add ```self.alpha = 1``` towards the end of ```visualize()``` function of ```MatrixVisualizer``` class. Roughly, before line 54
- In ```densepose/vis/densepose_outputs_vertex.py``` file, add ```image_bgr = np.zeros_like(image_bgr)``` towards the end of ```visualize()``` function of ```DensePoseOutputsVertexVisualizer``` class. Roughly, before line 93


