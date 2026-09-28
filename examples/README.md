# GeoJSON annotation export

[`annotations.geojson`](annotations.geojson) was written by SlideScope's own exporter, for an
example slide named `example-HE-slide.svs` with a pixel size of 0.25 µm. It contains one of
each kind of object SlideScope exports:

| Feature | Geometry | `properties.source` |
|---|---|---|
| A rectangle measurement | `Polygon` | `slidescope-measurement` |
| A line measurement | `LineString` | `slidescope-measurement` |
| A note on the slide | `Point` | `slidescope-note` |
| A saved region | `Polygon` | `slidescope-region` |

## How to read it

- **Coordinates are in full-resolution slide pixels**, with the origin at the top-left corner.
  They do not depend on the zoom you drew them at.
- **Ellipses** have no GeoJSON primitive, so they are written as a 72-point polygon.
- **`properties.objectType`** is `"annotation"`, the convention QuPath uses, so the objects
  import as annotations.
- **`properties.measurements`** holds length, perimeter and area in pixels and, when the slide
  records a pixel size, in micrometres (`µm`, `µm²`).
- **`properties.classification.name`** carries the project a note belongs to.
- **The top-level `slidescope` object** names the application and the slide, and gives the
  slide's full-resolution width and height.

## Opening it elsewhere

- **QuPath:** open the same slide, then drag the `.geojson` file onto the viewer.
- **Python:** any GeoJSON reader works, for example `json.load` or `geopandas.read_file`.
