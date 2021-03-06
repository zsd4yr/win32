---
title: LBN_SETFOCUS notification code
description: Notifies the application that the list box has received the keyboard focus. The parent window of the list box receives this notification code through the WM\_COMMAND message.
ms.assetid: d9e5e035-98a5-4ece-ba40-6d341c101859
keywords:
- LBN_SETFOCUS notification code Windows Controls
topic_type:
- apiref
api_name:
- LBN_SETFOCUS
api_location:
- Winuser.h
api_type:
- HeaderDef
ms.topic: reference
ms.date: 05/31/2018
---

# LBN\_SETFOCUS notification code

Notifies the application that the list box has received the keyboard focus. The parent window of the list box receives this notification code through the [**WM\_COMMAND**](https://docs.microsoft.com/windows/desktop/menurc/wm-command) message.


```C++
LBN_SETFOCUS

    WPARAM wParam;
    LPARAM lParam; 
```



## Parameters

<dl> <dt>

*wParam* 
</dt> <dd>

The [**LOWORD**](https://docs.microsoft.com/previous-versions/windows/desktop/legacy/ms632659(v=vs.85)) contains the identifier of the list box. The [**HIWORD**](https://docs.microsoft.com/previous-versions/windows/desktop/legacy/ms632657(v=vs.85)) specifies the notification code.

</dd> <dt>

*lParam* 
</dt> <dd>

Handle to the list box.

</dd> </dl>

## Requirements



|                                     |                                                                                                          |
|-------------------------------------|----------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista \[desktop apps only\]<br/>                                                           |
| Minimum supported server<br/> | Windows Server 2003 \[desktop apps only\]<br/>                                                     |
| Header<br/>                   | <dl> <dt>Winuser.h (include Windows.h)</dt> </dl> |



## See also

<dl> <dt>

**Reference**
</dt> <dt>

[LBN\_KILLFOCUS](lbn-killfocus.md)
</dt> <dt>

**Other Resources**
</dt> <dt>

[**HIWORD**](https://docs.microsoft.com/previous-versions/windows/desktop/legacy/ms632657(v=vs.85))
</dt> <dt>

[**LOWORD**](https://docs.microsoft.com/previous-versions/windows/desktop/legacy/ms632659(v=vs.85))
</dt> <dt>

[**WM\_COMMAND**](https://docs.microsoft.com/windows/desktop/menurc/wm-command)
</dt> </dl>

 

 





