# Offline SMT CVAT Annotator

Single-file offline annotation UI for SMT images. It runs directly in a browser and exports CVAT 1.1 XML with polygon annotations.

## Features

- Works offline as one HTML file
- Load a full image folder
- Draw polygon annotations
- Add text notes to each polygon
- Track total images, marked images, and current image index
- Add or delete custom classes
- Save annotations as JSON
- Read saved JSON annotations
- Export CVAT 1.1 XML

## How To Use

1. Open `offline-cvat-smt-annotator.html` in Chrome or Edge.
2. Click the folder loading button and choose the SMT image folder.
3. Select the current class from the class dropdown.
4. Click `POLYGON`.
5. Click points on the image to draw a polygon.
6. Double-click or click the finish button to finish the polygon.
7. Select a polygon to edit its class, text note, or attributes.
8. Click the save button to save annotations as a JSON file.
9. Later, reload the same image folder and click the load button to restore the JSON annotations.
10. Click the export XML button to export CVAT 1.1 XML.

## Default Classes

| Chinese | English |
| --- | --- |
| 正常 | ok |
| 缺件 | missing |
| 偏移 | shift |
| 立碑 | tombstone |
| 空焊 | open |
| 側立 | sideflip |
| 損件 | damage |
| 翻轉 | overturn |
| 異物 | foreign_material |
| 極反 | polarity |
| 錯件 | wrong_part |
| 連錫 | bridge |
| 少錫 | less_solder |

## Saving And Loading

The tool does not use browser cache on startup. Each time you open the HTML file, it starts blank.

- Save exports a JSON annotation file.
- Load imports a JSON annotation file.
- Images are not embedded in the JSON file, so reload the same image folder before reading annotations.

## CVAT Export

The exported XML uses CVAT annotation format version `1.1`.

Annotations are exported as polygon shapes:

```xml
<polygon label="missing" source="manual" occluded="0" points="x1,y1;x2,y2;x3,y3" z_order="0">
  <attribute name="text">note</attribute>
</polygon>
```

## Files

- `offline-cvat-smt-annotator.html`: the complete offline UI
- `.gitignore`: excludes local annotation JSON files
