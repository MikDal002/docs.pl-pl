---
title: 'Instrukcje: Przechowaj wiele formatów danych w obiekcie danych'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataObject class [WPF], storing multiple formats
- DataFormats class [WPF], storing multiple formats
- drag-and-drop [WPF], storing multiple formats
ms.assetid: 941ace29-29c4-4c26-b75b-ea7d06aa0d69
ms.openlocfilehash: 33415dd3cb1a05263cf9fb9ecafcbc857d364d57
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555677"
---
# <a name="how-to-store-multiple-data-formats-in-a-data-object"></a>Instrukcje: Przechowaj wiele formatów danych w obiekcie danych
Poniższy przykład pokazuje, jak używać <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%29> metodę, aby dodać dane do obiektu danych w wielu formatach.  
  
## <a name="example"></a>Przykład  
  
### <a name="description"></a>Opis  
  
### <a name="code"></a>Kod  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_storemultipleformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_storemultipleformats)]  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Windows.IDataObject>
- [Przegląd przeciągania i upuszczania](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)
