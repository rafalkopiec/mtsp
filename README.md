## .mtsp
### Metaspace hosting standard
The open standard for the three-dimensional web.
<br>
By default, a regular web browser navigates to the `index.html` of a website.
<br>
A metaspace browser instead responds to the `index.mtsp` if available.

### Demo
The demo project is hosted here [metaspace.rocks/mtsp/](https://metaspace.rocks/mtsp/)

### Sample `.mtsp` file
Below is an example `index.mtsp` file, generally to be hosted alongside an `index.html`.

```
#METASPACE_HOST
#METASPACE_VERSION:1
#METASPACE_NAME:"Untitled"
#METASPACE_PREVIEW_PATH:"preview.jpg"
#METASPACE_3D_PATH:"file.usdz"
```

### Content definitions

`#METASPACE_HOST` - must be present

`#METASPACE_VERSION `- mtsp version number

`#METASPACE_NAME` - name of experience (user-friendly)

`#METASPACE_PREVIEW_PATH` - relative path to image preview

`#METASPACE_3D_PATH` - relative path to 3D file (usdz)

### Considerations
- The .mtsp file format is formatted in a similar way to .m3u8 playlist files.
- For v1, these five fields are required.
- The preview image should be a `.jpg` for loading efficiency.
- The 3D file format should be `.usdz`, as it is compatible with all involved XR systems.
