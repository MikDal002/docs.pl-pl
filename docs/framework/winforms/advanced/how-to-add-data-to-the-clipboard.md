---
title: 'Instrukcje: Dodawanie danych do Schowka'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Clipboard [Windows Forms], copying data to
- data [Windows Forms], copying to Clipboard
ms.assetid: 25152454-0e78-40a9-8a9e-a2a5a274e517
ms.openlocfilehash: 37e46c48be41d0b527e73b15bfff1f069924fa20
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54682813"
---
# <a name="how-to-add-data-to-the-clipboard"></a>Instrukcje: Dodawanie danych do Schowka
<xref:System.Windows.Forms.Clipboard> Klasa zawiera metody, które służy do interakcji z funkcją Schowka systemu operacyjnego Windows. Wiele aplikacji używa Schowka jako tymczasowy repozytorium danych. Na przykład edytory użyć Schowka podczas operacji kopiowania i wklejania. Schowek jest również przydatne w przypadku przesyłania danych między aplikacjami na inny.  
  
 Po dodaniu danych do Schowka można określić format danych tak, aby inne aplikacje mogą rozpoznaje danych, jeśli używają tego formatu. Możesz również dodać dane do Schowka w wielu różnych formatach, aby zwiększyć liczbę inne aplikacje, które potencjalnie mogą używać danych.  
  
 Format Schowka jest ciągiem, który identyfikuje format tak, aby skojarzone dane mogą być przywracane aplikacji korzystającej z tego formatu. <xref:System.Windows.Forms.DataFormats> Klasa udostępnia wstępnie zdefiniowany format nazw do użycia. Można również użyć własnych nazw formatu lub użyć typ obiektu jako jego format.  
  
 Aby dodać dane do Schowka w jednej lub wielu formatów, należy użyć <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> metody. Dowolny obiekt można przekazać do tej metody, ale aby dodać dane w wielu formatach, należy najpierw dodać dane do oddzielny obiekt przeznaczony do pracy w wielu formatach. Zazwyczaj doda dane do <xref:System.Windows.Forms.DataObject>, ale można używać dowolnego typu, który implementuje <xref:System.Windows.Forms.IDataObject> interfejsu.  
  
 W [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)], możesz dodać dane bezpośrednio do Schowka, korzystając z nowych metod, które mają ułatwić podstawowe zadania do Schowka. Podczas pracy z danymi w postaci jednej, wspólnej, np. tekstu, należy użyć tych metod.  
  
> [!NOTE]
>  Wszystkie aplikacje oparte na Windows Udostępnianie Schowka. W związku z tym zawartość mogą ulec zmianie po przełączeniu do innej aplikacji.  
>   
>  <xref:System.Windows.Forms.Clipboard> Klasy należy używać tylko w wątkach ustawiany w trybie Jednowątkowego apartamentu jednego wątku. Aby użyć tej klasy, upewnij się, że Twoje `Main` metoda jest oznaczona atrybutem <xref:System.STAThreadAttribute> atrybutu.  
>   
>  Obiekt musi być możliwy do serializacji, aby mogła być umieść w Schowku. Aby typ był możliwy do serializacji, oznacz go za pomocą <xref:System.SerializableAttribute> atrybutu. Nie można serializować obiektu jest przekazywane do metody Schowka, metoda zakończy się niepowodzeniem bez zgłoszenia wyjątku. Aby uzyskać więcej informacji na temat serializacji, zobacz <xref:System.Runtime.Serialization>.  
  
### <a name="to-add-data-to-the-clipboard-in-a-single-common-format"></a>Aby dodać dane do Schowka w postaci jednej, wspólnej  
  
1.  Użyj <xref:System.Windows.Forms.Clipboard.SetAudio%2A>, <xref:System.Windows.Forms.Clipboard.SetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.SetImage%2A>, lub <xref:System.Windows.Forms.Clipboard.SetText%2A> metody. Metody te są dostępne tylko w [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].  
  
     [!code-csharp[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]  
  
### <a name="to-add-data-to-the-clipboard-in-a-custom-format"></a>Aby dodać dane do Schowka w niestandardowym formacie  
  
1.  Użyj <xref:System.Windows.Forms.Clipboard.SetData%2A> metodę o nazwie formatu niestandardowego. Ta metoda jest dostępna tylko w [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].  
  
     Można również użyć wstępnie zdefiniowany format nazwy <xref:System.Windows.Forms.Clipboard.SetData%2A> metody. Aby uzyskać więcej informacji, zobacz <xref:System.Windows.Forms.DataFormats>.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
### <a name="to-add-data-to-the-clipboard-in-multiple-formats"></a>Aby dodać dane do Schowka w wielu formatach  
  
1.  Użyj <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> metody i przekaż <xref:System.Windows.Forms.DataObject> zawierający dane. Tej metody należy użyć, aby dodać dane do Schowka w wersjach wcześniejszych niż [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].  
  
     [!code-csharp[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
## <a name="see-also"></a>Zobacz także
- [Operacje przeciągania i upuszczania oraz obsługa schowka](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md)
- [Instrukcje: Pobieranie danych ze Schowka](../../../../docs/framework/winforms/advanced/how-to-retrieve-data-from-the-clipboard.md)
