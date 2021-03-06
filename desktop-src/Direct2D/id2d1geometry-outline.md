---
title: ID2D1Geometry Outline methods
description: Computes the outline of the geometry and writes the result to an ID2D1SimplifiedGeometrySink.
ms.assetid: ec92db79-a1aa-4661-9e75-45a1763af370
keywords:
- Outline methods Direct2D
topic_type:
- apiref
api_location:
- D2d1.dll
api_type:
- DllExport
ms.topic: reference
ms.date: 05/31/2018
api_name: 
---

# ID2D1Geometry::Outline methods

Computes the outline of the geometry and writes the result to an [**ID2D1SimplifiedGeometrySink**](https://msdn.microsoft.com/en-us/library/Dd316919(v=VS.85).aspx).

### Overload list



| Method                                                                                                                                                          | Description                                                                                                                                      |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------|
| [**Outline(D2D1\_MATRIX\_3X2\_F&,ID2D1SimplifiedGeometrySink\*)**](https://msdn.microsoft.com/en-us/library/Dd316725(v=VS.85).aspx)              | Computes the outline of the geometry and writes the result to an [**ID2D1SimplifiedGeometrySink**](https://msdn.microsoft.com/en-us/library/Dd316919(v=VS.85).aspx). <br/> |
| [**Outline(D2D1\_MATRIX\_3X2\_F\*,ID2D1SimplifiedGeometrySink\*)**](https://msdn.microsoft.com/en-us/library/Dd316720(v=VS.85).aspx)             | Computes the outline of the geometry and writes the result to an [**ID2D1SimplifiedGeometrySink**](https://msdn.microsoft.com/en-us/library/Dd316919(v=VS.85).aspx).<br/>  |
| [**Outline(D2D1\_MATRIX\_3X2\_F&,FLOAT,ID2D1SimplifiedGeometrySink\*)**](https://msdn.microsoft.com/en-us/library/Dd316722(v=VS.85).aspx)  | Computes the outline of the geometry and writes the result to an [**ID2D1SimplifiedGeometrySink**](https://msdn.microsoft.com/en-us/library/Dd316919(v=VS.85).aspx).<br/>  |
| [**Outline(D2D1\_MATRIX\_3X2\_F\*,FLOAT,ID2D1SimplifiedGeometrySink\*)**](https://msdn.microsoft.com/en-us/library/Dd316717(v=VS.85).aspx) | Computes the outline of the geometry and writes the result to an [**ID2D1SimplifiedGeometrySink**](https://msdn.microsoft.com/en-us/library/Dd316919(v=VS.85).aspx).<br/>  |



## Remarks

The [**Outline**](https://msdn.microsoft.com/en-us/library/Dd316725(v=VS.85).aspx) method allows the caller to produce a geometry with an equivalent fill to the input geometry, with the following additional properties:

-   The output geometry contains no transverse intersections; that is, segments may touch, but they never cross.
-   The outermost figures in the output geometry are all oriented counterclockwise.
-   The output geometry is fill-mode invariant; that is, the fill of the geometry does not depend on the choice of the fill mode. For more information about the fill mode, see [**D2D1\_FILL\_MODE**](/windows/desktop/api/d2d1/ne-d2d1-d2d1_fill_mode).

Additionally, the [**Outline**](https://msdn.microsoft.com/en-us/library/Dd316725(v=VS.85).aspx) method can be useful in removing redundant portions of said geometries to simplify complex geometries. It can also be useful in combination with [**ID2D1GeometryGroup**](https://msdn.microsoft.com/en-us/library/Dd316581(v=VS.85).aspx) to create unions among several geometries simultaneously.

## Examples

The following code shows how to use **Outline** to construct an equivalent geometry with no self-intersections. It uses the default flattening tolerance and hence should not be used with very small geometries.


```C++
HRESULT D2DOutline(
    ID2D1Geometry *pGeometry,
    ID2D1Geometry **ppGeometry
    )
{
    HRESULT hr;
    ID2D1Factory *pFactory = NULL;
    pGeometry->GetFactory(&pFactory);

    ID2D1PathGeometry *pPathGeometry = NULL;
    hr = pFactory->CreatePathGeometry(&pPathGeometry);

    if (SUCCEEDED(hr))
    {
        ID2D1GeometrySink *pSink = NULL;
        hr = pPathGeometry->Open(&pSink);

        if (SUCCEEDED(hr))
        {
            hr = pGeometry->Outline(NULL, pSink);

            if (SUCCEEDED(hr))
            {
                hr = pSink->Close();

                if (SUCCEEDED(hr))
                {
                    *ppGeometry = pPathGeometry;
                    (*ppGeometry)->AddRef();
                }
            }
            pSink->Release();
        }
        pPathGeometry->Release();
    }

    pFactory->Release();

    return hr;
}
```



## Requirements



|                    |                                                                                     |
|--------------------|-------------------------------------------------------------------------------------|
| Library<br/> | <dl> <dt>D2d1.lib</dt> </dl> |
| DLL<br/>     | <dl> <dt>D2d1.dll</dt> </dl> |



## See also

<dl> <dt>

[**ID2D1Geometry**](https://msdn.microsoft.com/en-us/library/Dd316578(v=VS.85).aspx)
</dt> </dl>

 

 





