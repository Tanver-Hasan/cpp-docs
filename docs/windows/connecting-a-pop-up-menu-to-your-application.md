---
title: "Connecting a Pop-up Menu to Your C++ Application"
ms.date: "11/04/2016"
helpviewer_keywords: ["pop-up menus [C++], connecting to applications", "context menus [C++], connecting to applications", "menus [C++], pop-up", "shortcut menus [C++], connecting to applications"]
ms.assetid: 295cbf0e-6416-478e-bc3d-472fb98e0e52
---
# Connecting a Pop-up Menu to Your C++ Application

### To connect a pop-up menu to your application

1. Add a message handler for WM_CONTEXTMENU (for example). For more information, see [Mapping Messages to Functions](../mfc/reference/mapping-messages-to-functions.md).

2. Add the following code to the message handler:

    ```cpp
    CMenu menu;
    VERIFY(menu.LoadMenu(IDR_MENU1));
    CMenu* pPopup = menu.GetSubMenu(0);
    ASSERT(pPopup != NULL);
    pPopup->TrackPopupMenu(TPM_LEFTALIGN | TPM_RIGHTBUTTON, point.x, point.y, AfxGetMainWnd());
    ```

   > [!NOTE]
   > The [CPoint](../atl-mfc-shared/reference/cpoint-class.md) passed by the message handler is in screen coordinates.

## Requirements

MFC

## See Also

[Creating Pop-up Menus](../windows/creating-pop-up-menus.md)<br/>
[Menu Editor](../windows/menu-editor.md)