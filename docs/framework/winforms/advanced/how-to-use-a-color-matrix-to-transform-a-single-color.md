---
title: 'Instrukcje: Stosowanie macierzy kolorów do przekształcenia pojedynczego koloru'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image colors [Windows Forms], transforming
- color matrices [Windows Forms], using
ms.assetid: 44df4556-a433-49c0-ac0f-9a12063a5860
ms.openlocfilehash: 050bb147358636ff9ce250bd5026facd53e9bf51
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54498950"
---
# <a name="how-to-use-a-color-matrix-to-transform-a-single-color"></a>Instrukcje: Stosowanie macierzy kolorów do przekształcenia pojedynczego koloru
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] udostępnia <xref:System.Drawing.Image> i <xref:System.Drawing.Bitmap> klasy do przechowywania i manipulowania obrazami. <xref:System.Drawing.Image> i <xref:System.Drawing.Bitmap> obiektów przechowywać kolor każdego piksela jako wartość liczby 32-bitowej: 8 bitów na każdy czerwony, zielony, niebieski i alfa. Każdy z czterech składników jest liczba z przedziału od 0 do 255, od 0, reprezentujących natężenie i 255 reprezentujący pełnej intensywności. Składnik alfa określa Przezroczystość koloru: 0 jest w pełni przezroczyste, a 255 jest całkowicie nieprzezroczyste.  
  
 Wektor kolorów jest 4-krotka formularza (czerwony, zielony, niebieski, alfa). Na przykład wektor kolorów (0, 255, 0, 255) reprezentuje nieprzezroczyste kolor, który nie ma czerwony lub niebieski, ale ma kolor zielony w pełnej intensywności.  
  
 Inną konwencję reprezentująca kolorów używa numer 1 do pełnej intensywności. Przy użyciu Konwencji, kolor, który został opisany w poprzednim akapicie jest przedstawiany przez vector (0, 1, 0, 1). [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] używa konwencji 1 jako pełnej intensywności, podczas wykonywania przekształcenia kolorów.  
  
 Linear — przekształcenia (obrotu, skalowanie i podobne) można stosować do wektorów kolorów, poprzez pomnożenie wektorów kolorów w macierzy 4 x 4. Jednak nie można używać macierzy 4 x 4, aby wykonać tłumaczenie (nieliniowych). Jeśli dodasz fikcyjnego współrzędnych piąty (na przykład numer 1) do każdego wektorów kolor, można użyć macierzy 5 × 5 można zastosować dowolną kombinację linear — przekształcenia i tłumaczenia. Przekształcenie składający się z liniowego transformacji, następuje tłumaczenia jest wywoływana affine — przekształcenia.  
  
 Na przykład załóżmy, że chcesz rozpocząć z kolorem (0.2 0.0, 0,4, 1.0) i stosuje się następujące przekształcenia:  
  
1.  Double składnik czerwony  
  
2.  Dodaj wymagane 0,2 dla składników czerwonego, zielonego i niebieskiego  
  
 Następujące mnożenie macierzy wykona pary przekształcenia w podanej kolejności.  
  
 ![Ponowne kolorowanie](../../../../docs/framework/winforms/advanced/media/recoloring01.gif "recoloring01")  
  
 Elementów macierzy kolorów są indeksowane (liczony od zera), wiersz, a następnie kolumny. Na przykład wpis w piątym wierszu, a trzecia kolumna macierzy M jest oznaczona M [4] [2].  
  
 5 x 5 macierzą (pokazane na poniższej ilustracji) ma 1s na przekątnej i 0s wszędzie, gdzie else. Jeśli wektor kolor mnożenia macierz tożsamości, vector kolorów nie zmienia się. Wygodny sposób do utworzenia macierzy transformacji kolorów jest rozpoczynać macierz tożsamości i wprowadź niewielką zmianę, który produkuje żądane transformacje.  
  
 ![Ponowne kolorowanie](../../../../docs/framework/winforms/advanced/media/recoloring02.gif "recoloring02")  
  
 Bardziej szczegółowe omówienie macierzy, a przekształcenia zobacz [systemy i przekształcenia współrzędnych](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md).  
  
## <a name="example"></a>Przykład  
 Poniższy przykład pobiera obraz, który jest w jednym kolorze (0.2 0.0, 0,4, 1.0) i stosuje przekształcenia opisanych w poprzednich akapitach.  
  
 Poniższa ilustracja pokazuje oryginalny obraz po lewej stronie i przekształcone obraz po prawej stronie.  
  
 ![Colors](../../../../docs/framework/winforms/advanced/media/colortrans1.png "colortrans1")  
  
 Kod w poniższym przykładzie używa następujące kroki, aby wykonać ponowne kolorowanie:  
  
1.  Inicjowanie <xref:System.Drawing.Imaging.ColorMatrix> obiektu.  
  
2.  Tworzenie <xref:System.Drawing.Imaging.ImageAttributes> i przekazać <xref:System.Drawing.Imaging.ColorMatrix> obiekt <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> metody <xref:System.Drawing.Imaging.ImageAttributes> obiektu.  
  
3.  Przekaż <xref:System.Drawing.Imaging.ImageAttributes> obiekt <xref:System.Drawing.Graphics.DrawImage%2A> metody <xref:System.Drawing.Graphics> obiektu.  
  
 [!code-csharp[System.Drawing.RecoloringImages#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.RecoloringImages#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  
 Poprzedni przykład jest przeznaczony do użytku z formularzami Windows Forms i potrzebny <xref:System.Windows.Forms.PaintEventArgs> `e`, czyli parametrem <xref:System.Windows.Forms.Control.Paint> programu obsługi zdarzeń.  
  
## <a name="see-also"></a>Zobacz także
- [Ponowne kolorowanie obrazów](../../../../docs/framework/winforms/advanced/recoloring-images.md)
- [Systemy i przekształcenia współrzędnych](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)
