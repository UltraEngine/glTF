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
                    "NORMAL": 1
                },
                "indices": 3,
                "material": 0,
                "mode": 4,
                "extensions": {
                    "ULTRA_primitive_quads": {
                        "indices": 4
                    }
                }
            }
        ]
    }
]
```

## Implementation Notes

This extension does not dictate any specific rendering technique for quad meshes. It only provides a mechanism to store meshes qith quad geometry.

It is expected that in most implementations the number of quads will be half the number of triangles, and the accessor referenced in the extension will point to the same buffer as the triangle indices so that the indice array may be reused efficientaly, but these are not requirements. Implementations may reuse the triangle indice buffer or store a second buffer for quad indices.

## Justification

Although not all mesh geometry can be represented by quads, quads with tessellation produce a more even distribution of polygons than triangle tessellation, for greater visual quality. Having the ability to store quad meshes in glTF format enhances our ability to deliver greater visual acuity.
