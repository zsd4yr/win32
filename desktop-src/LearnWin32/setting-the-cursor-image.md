---
title: Setting the Cursor Image
description: Setting the Cursor Image
ms.assetid: FB223131-19AE-41DD-87DE-73992AE2A0CA
ms.technology: desktop
ms.prod: windows
ms.author: windowssdkdev
ms.topic: article
ms.date: 05/31/2018
---

# Setting the Cursor Image

The *cursor* is the small image that shows the location of the mouse or other pointing device. Many applications change the cursor image to give feedback to the user. Although it is not required, it adds a nice bit of polish to your application.

Windows provides a set of standard cursor images, called *system cursors*. These include the arrow, the hand, the I-beam, the hourglass (which is now a spinning circle), and others. This section describes how to use the system cursors. For more advanced tasks, such as creating custom cursors, see [Cursors](https://msdn.microsoft.com/library/windows/desktop/ms646970).

You can associate a cursor with a window class by setting the **hCursor** member of the [**WNDCLASS**](https://msdn.microsoft.com/library/windows/desktop/ms633576) or [**WNDCLASSEX**](https://msdn.microsoft.com/library/windows/desktop/ms633577) structure. Otherwise, the default cursor is the arrow. When the mouse moves over a window, the window receives a [**WM\_SETCURSOR**](https://msdn.microsoft.com/library/windows/desktop/ms648382) message (unless another window has captured the mouse). At this point, one of the following events occurs:

-   The application sets the cursor and the window procedure returns **TRUE**.
-   The application does nothing and passes [**WM\_SETCURSOR**](https://msdn.microsoft.com/library/windows/desktop/ms648382) to [**DefWindowProc**](https://msdn.microsoft.com/library/windows/desktop/ms633572).

To set the cursor, a program does the following:

1.  Calls [**LoadCursor**](https://msdn.microsoft.com/library/windows/desktop/ms648391) to load the cursor into memory. This function returns a handle to the cursor.
2.  Calls [**SetCursor**](https://msdn.microsoft.com/library/windows/desktop/ms648393) and passes in the cursor handle.

Otherwise, if the application passes [**WM\_SETCURSOR**](https://msdn.microsoft.com/library/windows/desktop/ms648382) to [**DefWindowProc**](https://msdn.microsoft.com/library/windows/desktop/ms633572), the **DefWindowProc** function uses the following algorithm to set the cursor image:

1.  If the window has a parent, forward the [**WM\_SETCURSOR**](https://msdn.microsoft.com/library/windows/desktop/ms648382) message to the parent to handle.
2.  Otherwise, if the window has a class cursor, set the cursor to the class cursor.
3.  If there is no class cursor, set the cursor to the arrow cursor.

The [**LoadCursor**](https://msdn.microsoft.com/library/windows/desktop/ms648391) function can load either a custom cursor from a resource, or one of the system cursors. The following example shows how to set the cursor to the system hand cursor.


```C++
    hCursor = LoadCursor(NULL, cursor);
    SetCursor(hCursor);
```



If you change the cursor, the cursor image resets on the next mouse move, unless you intercept the [**WM\_SETCURSOR**](https://msdn.microsoft.com/library/windows/desktop/ms648382) message and set the cursor again. The following code shows how to handle **WM\_SETCURSOR**.


```C++
    case WM_SETCURSOR:
        if (LOWORD(lParam) == HTCLIENT)
        {
            SetCursor(hCursor);
            return TRUE;
        }
        break;
```



This code first checks the lower 16 bits of *lParam*. If `LOWORD(lParam)` equals **HTCLIENT**, it means the cursor is over the client area of the window. Otherwise, the cursor is over the nonclient area. Typically, you should only set the cursor for the client area, and let Windows set the cursor for the nonclient area.

## Next

[User Input: Extended Example](user-input--extended-example.md)

 

 



