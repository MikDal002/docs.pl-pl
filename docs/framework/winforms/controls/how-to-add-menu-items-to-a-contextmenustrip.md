---
title: 'Instrukcje: Dodawanie elementów Menu do paska ContextMenuStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ContextMenuStrips [Windows Forms], adding menu items
- shortcut menus [Windows Forms], adding items
- context menus [Windows Forms], adding menu items
ms.assetid: 1ec14776-3ea2-4752-bd22-4fae0fd19e1a
ms.openlocfilehash: 88bf56ea21c4f120b9d745e7f8a31fed485fa192
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506241"
---
# <a name="how-to-add-menu-items-to-a-contextmenustrip"></a>Instrukcje: Dodawanie elementów Menu do paska ContextMenuStrip
Można dodać element menu tylko jeden lub kilka elementów, które znajdują się w czasie <xref:System.Windows.Forms.ContextMenuStrip>.  
  
### <a name="to-add-a-single-menu-item-to-a-contextmenustrip"></a>Aby dodać pojedynczy element menu do paska ContextMenuStrip  
  
-   Użyj <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> metodę, aby dodać jeden element menu do <xref:System.Windows.Forms.ContextMenuStrip>.  
  
    ```vb  
    Me.contextMenuStrip1.Items.Add(Me.toolStripMenuItem1)  
    ```  
  
    ```csharp  
    this.contextMenuStrip1.Items.Add(toolStripMenuItem1);  
    ```  
  
### <a name="to-add-several-menu-items-to-a-contextmenustrip"></a>Aby dodać kilka elementów menu do paska ContextMenuStrip  
  
-   Użyj <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> metodę, aby dodać kilka elementów menu do <xref:System.Windows.Forms.ContextMenuStrip>.  
  
    ```vb  
    Me.contextMenuStrip1.Items.AddRange(New _  
       System.Windows.Forms.ToolStripItem() {Me.toolStripMenuItem1, _  
          Me.toolStripMenuItem2})  
    ```  
  
    ```csharp  
    this.contextMenuStrip1.Items.AddRange(new   
       System.Windows.Forms.ToolStripItem[] {  
          this.toolStripMenuItem1, this.toolStripMenuItem2});  
    ```  
  
## <a name="see-also"></a>Zobacz także
- [ContextMenuStrip, kontrolka](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)
