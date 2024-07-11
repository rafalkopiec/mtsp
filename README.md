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
/// Required
#METASPACE_HOST
#METASPACE_VERSION:1
#METASPACE_NAME:"Untitled"
#METASPACE_PREVIEW_PATH:"preview.jpg"
#METASPACE_3D_PATH:"file.usdz"

/// Navigation
#METASPACE_NAVIGATION:"red_box" -> "red_box/index.mtsp"
#METASPACE_NAVIGATION:"yellow_box" -> "yellow_box/index.mtsp"
#METASPACE_NAVIGATION:"green_box" -> "green_box/index.mtsp"
#METASPACE_NAVIGATION:"home_box" -> "../index.mtsp"
#METASPACE_NAVIGATION:"root_box" -> "../../index.mtsp"
```

### Content definitions
#### Required

`#METASPACE_HOST` - must be present

`#METASPACE_VERSION `- mtsp version number

`#METASPACE_NAME` - name of experience (user-friendly)

`#METASPACE_PREVIEW_PATH` - relative path to image preview

`#METASPACE_3D_PATH` - relative path to 3D file (usdz)

#### Optional

`#METASPACE_NAVIGATION` - a string containing an entity name in quotes, an arrow, and a relative path to another `.mtsp` file. There can be an infinite or zero amount of these lines. The goal here is that the user would tap on an entity in a metaspace browser, and the browser would take them to the resolved URL provided by a metaspace decoder.


### Considerations
- The .mtsp file format is formatted in a similar way to .m3u8 playlist files.
- For v1, these five fields are required.
- The preview image should be a `.jpg` for loading efficiency.
- The 3D file format should be `.usdz`, as it is compatible with all involved XR systems.

### Decoding
A Swift-based decoder is available as a package here [github.com/rafalkopiec/mtsp-decoder](https://github.com/rafalkopiec/mtsp-decoder).

### Viewing
A RealityKit-based Swift `.usdz` viewer is available as a package here [github.com/rafalkopiec/mtsp-viewer](https://github.com/rafalkopiec/mtsp-viewer).

### Building a metaspace browser
To build a metaspace browser, you need implementations of an `mtsp-decoder` and an `mtsp-viewer`. 

Feel free to use my open-source packages to give you a head start, or you can roll on your own.
