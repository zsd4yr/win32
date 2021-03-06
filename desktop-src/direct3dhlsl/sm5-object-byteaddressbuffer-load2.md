---
title: Load2(uint) function
description: Gets two values.
ms.assetid: 696ce310-4d65-4382-97ec-046160197c67
keywords:
- Load2 function HLSL
topic_type:
- apiref
api_name:
- Load2
api_type:
- NA
ms.topic: reference
ms.date: 05/31/2018
api_location: 
---

# Load2(uint) function

Gets two values.

## Syntax

``` syntax
uint2 Load2(
  in uint address
);
```

## Parameters

<dl> <dt>

*address* \[in\]
</dt> <dd>

Type: **uint**

The input address in bytes, which must be a multiple of 4.

</dd> </dl>

## Return value

Type: **uint2**

Two values.

## Remarks

This function is supported for the following types of shaders:



| Vertex | Hull | Domain | Geometry | Pixel | Compute |
|--------|------|--------|----------|-------|---------|
| x      | x    | x      | x        | x     | x       |



 

## See also

<dl> <dt>

[Load2 methods](byteaddressbuffer-load2.md)
</dt> <dt>

[Shader Model 5](d3d11-graphics-reference-sm5.md)
</dt> </dl>

 

 




