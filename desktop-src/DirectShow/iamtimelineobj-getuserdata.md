---
Description: The GetUserData method retrieves the application-defined persistent data.
ms.assetid: dd2cdb37-9c4f-4356-a35f-2d42b7588da6
title: IAMTimelineObj::GetUserData method
ms.topic: reference
ms.date: 05/31/2018
topic_type: 
- APIRef
- kbSyntax
api_name: 
- IAMTimelineObj.GetUserData
api_type: 
- COM
api_location: 
- strmiids.lib
- strmiids.dll
---

# IAMTimelineObj::GetUserData method

> [!Note]  
> \[Deprecated. This API may be removed from future releases of Windows.\]

 

The `GetUserData` method retrieves the application-defined persistent data.

## Syntax


```C++
HRESULT GetUserData(
   BYTE *pData,
   long *pSize
);
```



## Parameters

<dl> <dt>

*pData* 
</dt> <dd>

Pointer to a buffer that receives the data. To determine the size of buffer to allocate, set this parameter to **NULL**. The required size is returned in *pSize*.

</dd> <dt>

*pSize* 
</dt> <dd>

Receives the size of the data, in bytes.

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

[**IAMTimelineObj Interface**](iamtimelineobj.md)
</dt> <dt>

[Error and Success Codes](error-and-success-codes.md)
</dt> </dl>

 

 




