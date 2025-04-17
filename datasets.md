# Dataset Formats Cheatsheet

---

## 1. COCO (Common Objects in Context)

- **Single JSON file** containing:
  - `images`: list of `{ "id", "file_name", "height", "width" }`
  - `annotations`: list of `{ "id", "image_id", "category_id", "bbox", "segmentation", "area", "iscrowd" }`
  - `categories`: list of `{ "id", "name", "supercategory" }`

- **Directory Layout:**
  ```
  coco/
    images/train2017/
    images/val2017/
    annotations/instances_train2017.json
    annotations/instances_val2017.json
  ```

- **Sample Annotation Entry:**
  ```json
  {
    "id": 42,
    "image_id": 10,
    "category_id": 3,
    "bbox": [120.5, 45.0, 80.2, 100.3],
    "area": 8020.06,
    "iscrowd": 0
  }
  ```

---

## 2. YOLO (You Only Look Once)

- **One TXT label per image**, same base name:
  ```
  <class_id> <x_center> <y_center> <width> <height>
  ```
  (all normalized to [0,1])

- **Directory Layout:**
  ```
  yolo/
    images/train/
    images/val/
    labels/train/img001.txt
    labels/val/img002.txt
  ```

- **Sample Label (`img001.txt`):**
  ```
  2 0.523 0.412 0.114 0.237
  0 0.245 0.678 0.100 0.150
  ```

---

## 3. KITTI (Autonomous Driving)

- **Detection Labels:** one TXT per frame:
  ```
  <type> <truncation> <occlusion> <alpha> 
  <xmin> <ymin> <xmax> <ymax> 
  <h> <w> <l> <X> <Y> <Z> <rotation_y>
  ```

- **Directory Layout:**
  ```
  kitti/
    image_2/
    velodyne/
    label_2/000000.txt
  ```

- **Sample Label (`000000.txt`):**
  ```
  Car 0.00 0 1.57 712.40 143.00 810.73 307.92 1.89 1.64 4.28 1.84 1.47 8.41 -1.59
  ```

---

## 4. LLM Text Corpora

### 4.1 JSONL

- **One JSON object per line**:
  ```json
  {"text": "Once upon a time, ..."}
  {"text": "In a world where AI ..."}
  ```

### 4.2 CSV/TSV

- **Header + rows**:
  ```csv
  id,text,label
  1,"The cat sat on the mat.",positive
  ```

### 4.3 HuggingFace Datasets

- **Parquet + JSON metadata**, load via `datasets`:
  ```python
  from datasets import load_dataset
  ds = load_dataset("wikitext", "wikitext-2-raw-v1")
  print(ds["train"][0])
  ```

---

## Tips

- Always **visualize** a few samples.
- Ensure **coordinate normalization** when needed.
- Keep a `classes.txt` or `meta.json` for category mapping.
- Record **split ratios** and **random seeds** in metadata.
