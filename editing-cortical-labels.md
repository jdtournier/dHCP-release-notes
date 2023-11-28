## Guidelines for editing cortical labels for surface generation (DrawEM v1.2)

### Software:
- [Workbench](https://www.humanconnectome.org/software/get-connectomeworkbench#download)
- [ITK-SNAP](http://www.itksnap.org/pmwiki/pmwiki.php?n=Downloads.SNAP3)

### Equipment:

- Wacom drawing tablet (provided)

---

### Loading the cortical surfaces:

Open Workbench (`wb_view`) → "Open Other..." → locate your case folder and go to the workbench folder
→ select file `native.wb.spec` → LOAD

[![loading cortical surfaces](assets/images/editing-cortical-labels/ctx-labels-000.png)](assets/images/editing-cortical-labels/ctx-labels-000.png)


---

### To visualise the T2:

Select the '(2) Volume' tab.

[![visualise T2](assets/images/editing-cortical-labels/ctx-labels-001.png)](assets/images/editing-cortical-labels/ctx-labels-001.png)

---

### To visualise the surfaces overlayed on the T2:

In the 'Overlay toolbox' → select ‘Vol/surf Outline’ tab → tick all 'lime' 'blue' options.

[![visualise surfaces](assets/images/editing-cortical-labels/ctx-labels-002.png)](assets/images/editing-cortical-labels/ctx-labels-002.png)

---

### Visualise cortical surfaces (workbench) and edit labels (ITK-SNAP) simultaneously.

Match the slice number (red circles):

[![visualise and edit](assets/images/editing-cortical-labels/ctx-labels-003.png)](assets/images/editing-cortical-labels/ctx-labels-003.png)

The inner and outer surface boundaries should run in parallel with no breaks.

---

## Regions of Interest

- Central sulcus
- Parieto-occipital sulcus
- Sylvian fissure
- Orbito-frontal cortex
- Other cortical areas (examples)

---

### Central sulcus

Common error: discontinuity in cortical surfaces due to white matter voxels mislabelled as cortex.

[![central sulcus error](assets/images/editing-cortical-labels/ctx-labels-004.png)](assets/images/editing-cortical-labels/ctx-labels-004.png)

Corrections needed: Label incorrect cortex voxels as white matter (label 3 over label 2)

[![central sulcus solution](assets/images/editing-cortical-labels/ctx-labels-005.png)](assets/images/editing-cortical-labels/ctx-labels-005.png)

---

### Parieto-occipital sulcus

Common error: discontinuity in cortical surfaces due to cortical complexity and partial volume. White matter and CSF voxels mislabelled as cortex.

[![parieto-occipital sulcus error](assets/images/editing-cortical-labels/ctx-labels-006.png)](assets/images/editing-cortical-labels/ctx-labels-006.png)


Corrections needed: best approach is to manually delineate the cortical ribbon.

1. In the slices requiring editing, convert all cortical voxels into white matter. (Label 3 over
label 2).
2. Manually delineate the cortical ribbon (Label 2 over label 3) (WM invisible option).
3. Label as CSF any voxels mislabelled as cortex or white matter (label 1 over all labels).

[![parieto-occipital sulcus solution](assets/images/editing-cortical-labels/ctx-labels-007.png)](assets/images/editing-cortical-labels/ctx-labels-007.png)

---

### Sylvian fissure

Common error: discontinuity in cortical surfaces due to cortical complexity and partial volume. White matter and CSF voxels mislabelled as cortex.

[![sylvian fissure error](assets/images/editing-cortical-labels/ctx-labels-008.png)](assets/images/editing-cortical-labels/ctx-labels-008.png)


Corrections:

1. Label as white matter any voxels mislabelled as cortex (label 3 over label 2).
2. Label as CSF any voxels mislabelled as cortex (label 1 over label 2).

[![sylvian fissure solution](assets/images/editing-cortical-labels/ctx-labels-009.png)](assets/images/editing-cortical-labels/ctx-labels-009.png)

---

### Orbito-frontal cortex

Common error: frontal bone of orbit labelled as cortex (identified on ITK-SNAP only)

[![orbito-frontal cortex error](assets/images/editing-cortical-labels/ctx-labels-010.png)](assets/images/editing-cortical-labels/ctx-labels-010.png)

Correction:

1. Identify regions in sagittal and locate in axial using crosshairs.
2. Delete any voxels mislabelled as cortex (Clear label over label 2).

[![orbito-frontal cortex solution](assets/images/editing-cortical-labels/ctx-labels-011.png)](assets/images/editing-cortical-labels/ctx-labels-011.png)

---

### Other cortical areas - examples

**Check for other regions with discontinuity in the surfaces, inspect all slices.**

Example: cortical ribbon overestimated, white matter voxels mistakenly labelled as cortex

[![other cortical areas example 1](assets/images/editing-cortical-labels/ctx-labels-012.png)](assets/images/editing-cortical-labels/ctx-labels-012.png)

Correction: Label 3 over label 2.

---

**Check for other regions with discontinuity in the surfaces, inspect all slices.**

Example: cortical ribbon overestimated, CSF voxels mistakenly labelled as cortex


[![other cortical areas example 2](assets/images/editing-cortical-labels/ctx-labels-013.png)](assets/images/editing-cortical-labels/ctx-labels-013.png)

Correction: Label 1 over label 2.

---

**Check for other regions with discontinuity in the surfaces, inspect all slices.**

Example: Cortex/skull boundary error due to partial volume, CSF labelled as cortex.  

[![other cortical areas example 3](assets/images/editing-cortical-labels/ctx-labels-014.png)](assets/images/editing-cortical-labels/ctx-labels-014.png)

Correction: Label 1 over label 2.

---

## Good to know

- [x] Keyboard shortcuts  
  - 'S' makes labels invisible
  - +/- size of brush

- [x] Before you start: adjust the T2 contrast
  - (Tools -> image contrast → contrast adjustment).

- [x] First work on the specific ROIs (Central sulcus, Parieto-occipital sulcus, Sylvian fissure, Orbitofrontal cortex).

- [x] Focus on one ROI at a time. Ignore other errors on the same slice in other areas until the ROI is
corrected. Then correct the closest errors.

- [x] Efficient set up: Wacom pen on right hand for editing and mouse on left hand for scrolling (R-handed)

- [x] You can save your segmentation and continue editing later.

