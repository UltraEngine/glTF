# ULTRA_primitive_quads



## Contributors

- Josh Klint, Ultra Software, [@ultraengine](https://github.com/ultraengine)

## Status

Ultra Engine Vendor Extension - Currently supported in [Ultra Engine](https://www.ultraengine.com).

## Dependencies

Written against the glTF 2.0 spec.

## Overview

## Extending Primitives

Quads are requested by adding the `ULTRA_primitive_quads` extension to a primitive rendered with `"mode": 4`, `TRIANGLES`.

```json
"meshes": [
    {
        "primitives": [
            {
                "attributes": {
                    "POSITION": 0,
                    "NORMAL": 1,
                    "_BATCHID": 2
                },
                "indices": 3,
                "material": 0,
                "mode": 4,
                "extensions": {
                    "CESIUM_primitive_outline": {
                        "indices": 4
                    }
                }
            }
        ]
    }
]
```


5.24.4. mesh.primitive.mode
The topology type of primitives to render.

Type: integer

Required: No, default: 4

Allowed values:
0 POINTS
1 LINES
2 LINE_LOOP
3 LINE_STRIP
4 TRIANGLES
5 TRIANGLE_STRIP
6 TRIANGLE_FAN
7 QUADS

## Implementation Notes



## Justification

Although not all mesh geometry can be represented by quads, quads with tessellation produce a more even distribution of polygons than triangle tessellation, for greater visual quality. Having the ability to store quad meshes in glTF format enhances our ability to deliver higher quality visuals.
