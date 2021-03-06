---
title: 'Instrukcje: Tworzenie obrazów miniatur'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thumbnail images [Windows Forms], creating
- images [Windows Forms], creating thumbnails
ms.assetid: e956242a-1e5b-4217-a3cf-5f3fb45d00ba
ms.openlocfilehash: fd5e0b5341a712f25f9d41670f9b3ede5414dda4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54497045"
---
# <a name="how-to-create-thumbnail-images"></a>Instrukcje: Tworzenie obrazów miniatur
Obraz miniatury jest mały wersję obrazu. Możesz utworzyć obraz miniatury, przez wywołanie metody <xref:System.Drawing.Image.GetThumbnailImage%2A> metody <xref:System.Drawing.Image> obiektu.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład tworzy <xref:System.Drawing.Image> obiekt z pliku JPG. Oryginalny obraz ma 640 pikseli szerokości i wysokości 479 pikseli. Ten kod tworzy obraz miniatury, który ma 100 pikseli szerokości i wysokości 100 pikseli.  
  
 Poniższa ilustracja przedstawia obraz miniatury.  
  
 ![Obraz miniatury](../../../../docs/framework/winforms/advanced/media/thumbnail1.png "Thumbnail1")  
  
> [!NOTE]
>  W tym przykładzie metody wywołania zwrotnego jest zadeklarowana, ale nigdy używane. To obsługuje wszystkie wersje interfejsu GDI +.  
  
 [!code-csharp[System.Drawing.WorkingWithImages#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.WorkingWithImages#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  
 Poprzedni przykład jest przeznaczony do użytku z formularzami Windows Forms i potrzebny <xref:System.Windows.Forms.PaintEventArgs> `e`, czyli parametrem <xref:System.Windows.Forms.Control.Paint> programu obsługi zdarzeń. Aby uruchomić przykład, wykonaj następujące kroki:  
  
1.  Tworzenie nowej aplikacji Windows Forms.  
  
2.  Dodaj przykładowy kod do formularza.  
  
3.  Utwórz procedurę obsługi w formularzu <xref:System.Windows.Forms.Control.Paint> zdarzeń  
  
4.  W <xref:System.Windows.Forms.Control.Paint> program obsługi, wywołanie `GetThumbnail` metody i przekazać `e` dla <xref:System.Windows.Forms.PaintEventArgs>.  
  
5.  Znajdź plik obrazu, który ma się miniaturę.  
  
6.  W `GetThumbnail` metody, określ ścieżkę i nazwę obrazu pliku.  
  
7.  Naciśnij klawisz F5, aby uruchomić przykład.  
  
     W formularzu pojawi się miniaturę 100 x 100.  
  
## <a name="see-also"></a>Zobacz także
- [Obrazy, mapy bitowe i metapliki](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
- [Praca z obrazami, mapami bitowymi, ikonami i metaplikami](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
