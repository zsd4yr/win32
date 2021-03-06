---
Description: The GetDefaultFPS method retrieves the default output frame rate, in frames per second (FPS). Groups use this value as their default frame rate. To set a group's frame rate, call the IAMTimelineGroup::SetOutputFPS method on the group.
ms.assetid: 91c83512-4295-440e-b3b2-09fe3629f827
title: IAMTimeline::GetDefaultFPS method
ms.topic: reference
ms.date: 05/31/2018
topic_type: 
- APIRef
- kbSyntax
api_name: 
- IAMTimeline.GetDefaultFPS
api_type: 
- COM
api_location: 
- strmiids.lib
- strmiids.dll
---

# IAMTimeline::GetDefaultFPS method

> [!Note]  
> \[Deprecated. This API may be removed from future releases of Windows.\]

 

The `GetDefaultFPS` method retrieves the default output frame rate, in frames per second (FPS). Groups use this value as their default frame rate. To set a group's frame rate, call the [**IAMTimelineGroup::SetOutputFPS**](iamtimelinegroup-setoutputfps.md) method on the group.

## Syntax


```C++
HRESULT GetDefaultFPS(
   double *pFPS
);
```



## Parameters

<dl> <dt>

*pFPS* 
</dt> <dd>

Receives the default frame rate, in frames per second.

</dd> </dl>

## Return value

If this method succeeds, it returns **S\_OK**. Otherwise, it returns an **HRESULT** error code.

## Remarks

> [!Note]  
> The header file Qedit.h is not compatible with Direct3D headers later than version 7.

 

> [!Note]  
> To obtain Qedit.h, download the [Microsoft Windows SDK Update for Windows Vista and .NET Framework 3.0](https://go.microsoft.com/fwlink/p/?linkid=129787). Qedit.h is not available in the Microsoft Windows SDK for Windows 7 and .NET Framework 3.5 Service Pack 1.

 

## Requirements



|                    |                                                                                         |
|--------------------|-----------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>Qedit.h</dt> </dl>      |
| Library<br/> | <dl> <dt>Strmiids.lib</dt> </dl> |



## See also

<dl> <dt>

[**IAMTimeline Interface**](iamtimeline.md)
</dt> <dt>

[Error and Success Codes](error-and-success-codes.md)
</dt> </dl>

 

 




