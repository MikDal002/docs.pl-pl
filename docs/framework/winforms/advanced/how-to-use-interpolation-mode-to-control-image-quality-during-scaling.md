---
title: 'Instrukcje: Używanie trybu interpolacji do sterowania jakością obrazu w czasie skalowania'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interpolation mode [Windows Forms], controlling image quality
- images [Windows Forms], scaling
- images [Windows Forms], controlling quality
ms.assetid: fde9bccf-8aa5-4b0d-ba4b-788740627b02
ms.openlocfilehash: 0c295411418dabac74626c3c4ab43fb8210bbfa4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54631429"
---
# <a name="how-to-use-interpolation-mode-to-control-image-quality-during-scaling"></a>Instrukcje: Używanie trybu interpolacji do sterowania jakością obrazu w czasie skalowania
Tryb interpolacji <xref:System.Drawing.Graphics> obiekt ma wpływ na sposób [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] obrazów w skali (odcinkach i zmniejsza). <xref:System.Drawing.Drawing2D.InterpolationMode> Wyliczenie definiuje kilka trybów interpolacji, niektóre z nich są wyświetlane na poniższej liście:  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.Bilinear>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBilinear>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.Bicubic>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic>  
  
 Obraz jest rozciągany tak, każdego piksela oryginalnego obrazu, musi być zmapowany do grupy pikseli większy obraz. Aby zmniejszyć obrazu, grup pikseli, oryginalnym obrazie musi być zamapowany na jednym pikseli w mniejszym obrazem. Skuteczność algorytmy, które wykonują te mapowania określa jakość skalowany obraz. Algorytmy, które powoduje, że wyższej jakości skalowanych zwykle wymagają więcej czasu na przetwarzanie. Z powyższej listy <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor> jest tryb najniższej jakości i <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic> jest tryb najwyższej jakości.  
  
 Aby ustawić tryb interpolacji, należy przypisać jeden z elementów członkowskich <xref:System.Drawing.Drawing2D.InterpolationMode> wyliczeniu, aby <xref:System.Drawing.Graphics.InterpolationMode%2A> właściwość <xref:System.Drawing.Graphics> obiektu.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład pobiera obraz i następnie zmniejsza obraz z trzech trybów różnych interpolacji.  
  
 Na poniższej ilustracji przedstawiono oryginalnego obrazu i trzy obrazy mniejsze.  
  
 ![Obraz ze zróżnicowanymi ustawieniami interpolacji](../../../../docs/framework/winforms/advanced/media/csgrapes1.png "csgrapes1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#81](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#81)]
 [!code-vb[System.Drawing.WorkingWithImages#81](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#81)]  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  
 Poprzedni przykład jest przeznaczony do użytku z formularzami Windows Forms i potrzebny <xref:System.Windows.Forms.PaintEventArgs> `e`, czyli parametrem <xref:System.Windows.Forms.Control.Paint> programu obsługi zdarzeń.  
  
## <a name="see-also"></a>Zobacz także
- [Obrazy, mapy bitowe i metapliki](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
- [Praca z obrazami, mapami bitowymi, ikonami i metaplikami](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
