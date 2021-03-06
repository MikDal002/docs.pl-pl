---
title: 'Instrukcje: Dodawanie i usuwanie węzłów za pomocą kontrolki TreeView formularzy Windows przy użyciu narzędzia Projektant'
ms.date: 03/30/2017
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: 35bf1750-045e-4ec5-97cb-b47b0dbdaa2c
ms.openlocfilehash: 7ef1a21ee4cb6e8313c01e7f5af30d19d00d07cf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54649885"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control-using-the-designer"></a>Instrukcje: Dodawanie i usuwanie węzłów za pomocą kontrolki TreeView formularzy Windows przy użyciu narzędzia Projektant
Ponieważ formularzy Windows Forms <xref:System.Windows.Forms.TreeView> kontrolka Wyświetla węzły w hierarchiczny sposób, podczas dodawania węzła należy zwrócić uwagę na to swojego węzła nadrzędnego.  
  
 Poniższa procedura wymaga **aplikacji Windows** projektu za pomocą zawierający formularz <xref:System.Windows.Forms.TreeView> kontroli. Aby uzyskać informacje o konfigurowaniu taki projekt, zobacz [jak: Utwórz projekt aplikacji Windows](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) i [jak: Dodawanie formantów do formularzy Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Okna dialogowe i polecenia menu mogą się różnić od tych opisanych w Pomocy, w zależności od ustawień aktywnych lub wydania. Aby zmienić swoje ustawienia, wybierz opcję **Import i eksport ustawień** na **narzędzia** menu. Aby uzyskać więcej informacji, zobacz [personalizowanie środowiska IDE programu Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-add-or-remove-nodes-in-the-designer"></a>Aby dodać lub usunąć węzły w Projektancie  
  
1.  Wybierz <xref:System.Windows.Forms.TreeView> kontroli.  
  
2.  W **właściwości** okna, kliknij przycisk **wielokropka** (![VisualStudioEllipsesButton — zrzut ekranu](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) znajdujący się obok <xref:System.Windows.Forms.TreeView.Nodes%2A> właściwości.  
  
     **TreeNode Editor** pojawia się.  
  
3.  Aby dodać węzły, węzeł główny musi istnieć; Jeśli nie istnieje, należy najpierw dodać katalog główny, klikając **Dodawanie głównego** przycisku. Następnie można dodać węzły podrzędne, wybierając głównego lub dowolnego innego węzła i klikając **Dodaj element podrzędny** przycisku.  
  
4.  Aby usunąć węzły, wybierz węzeł, aby usunąć, a następnie kliknij przycisk **Usuń** przycisku.  
  
## <a name="see-also"></a>Zobacz także
- [TreeView, kontrolka](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)
- [TreeView, kontrolka — omówienie](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)
- [Instrukcje: Ustawienie ikon dla kontrolki TreeView formularzy Windows](../../../../docs/framework/winforms/controls/how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [Instrukcje: Iterowanie wszystkich węzłów kontrolki TreeView formularzy Windows](../../../../docs/framework/winforms/controls/how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [Instrukcje: Określanie, który węzeł TreeView został kliknięty](../../../../docs/framework/winforms/controls/how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [Instrukcje: Dodawanie niestandardowych informacji do TreeView lub ListView — formant (formularze Windows)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)
