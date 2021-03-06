---
title: 'Instrukcje: Używanie tabeli ponownego mapowania kolorów'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- color tables [Windows Forms], remapping colors with
- custom colors [Windows Forms], creating with color remap table
- color remap tables [Windows Forms], using
ms.assetid: 977df1ce-8665-42d4-9fb1-ef7f0ff63419
ms.openlocfilehash: 06a25179a3afc004029972bbf7d4d5691d42b25b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54683914"
---
# <a name="how-to-use-a-color-remap-table"></a>Instrukcje: Używanie tabeli ponownego mapowania kolorów
Ponowne mapowanie jest procesem konwertowania kolory na obrazie zgodnie z tabeli ponownego mapowania kolorów. Tabeli ponownego mapowania kolorów jest tablicą <xref:System.Drawing.Imaging.ColorMap> obiektów. Każdy <xref:System.Drawing.Imaging.ColorMap> obiektów w tablicy ma <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> właściwości i <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> właściwości.  
  
 Gdy [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] rysuje na ilustracji każdego piksela obraz, który jest porównywany z tablicy stare kolory. Jeśli kolor piksela odpowiada stary kolor, jego kolor jest zmieniany na odpowiedniej nowy kolor. Kolory są zmieniane tylko w przypadku renderowania — wartości kolorów sam obraz (przechowywane w <xref:System.Drawing.Image> lub <xref:System.Drawing.Bitmap> obiektu) nie są zmieniane.  
  
 Aby narysować ponownie zmapowany obrazu, zainicjowania tablicy <xref:System.Drawing.Imaging.ColorMap> obiektów. Ta tablica do przekazania <xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A> metody <xref:System.Drawing.Imaging.ImageAttributes> obiektu, a następnie przekazać <xref:System.Drawing.Imaging.ImageAttributes> do obiektu <xref:System.Drawing.Graphics.DrawImage%2A> metody <xref:System.Drawing.Graphics> obiektu.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład tworzy <xref:System.Drawing.Image> obiektu na podstawie pliku RemapInput.bmp. Ten kod tworzy tabeli ponownego mapowania kolorów, która składa się z pojedynczego <xref:System.Drawing.Imaging.ColorMap> obiektu. <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> Właściwość `ColorRemap` obiekt ma kolor czerwony i <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> właściwość ma kolor niebieski. Obraz jest rysowane raz bez ponownego mapowania i drugi raz z ponownego mapowania. Proces ponownego mapowania zmienia wszystkie piksele czerwony na niebieski.  
  
 Poniższa ilustracja pokazuje oryginalny obraz po lewej stronie i ponownie zmapowany obraz po prawej stronie.  
  
 ![Ponowne mapowanie kolorów](../../../../docs/framework/winforms/advanced/media/colortrans7.png "colortrans7")  
  
 [!code-csharp[System.Drawing.RecoloringImages#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.RecoloringImages#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  
 Poprzedni przykład jest przeznaczony do użytku z formularzami Windows Forms i potrzebny <xref:System.Windows.Forms.PaintEventArgs> `e`, czyli parametrem <xref:System.Windows.Forms.Control.Paint> programu obsługi zdarzeń.  
  
## <a name="see-also"></a>Zobacz także
- [Ponowne kolorowanie obrazów](../../../../docs/framework/winforms/advanced/recoloring-images.md)
- [Obrazy, mapy bitowe i metapliki](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
