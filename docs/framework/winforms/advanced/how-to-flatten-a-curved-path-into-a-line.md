---
title: 'Instrukcje: Spłaszczanie ścieżki krzywej do linii'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], flattening curves into lines
- curves [Windows Forms], flattening
- GraphicsPath object
- paths [Windows Forms], flattening
- drawing [Windows Forms], flattening curves
ms.assetid: e654b8de-25f4-4735-9208-42e4514a589c
ms.openlocfilehash: aa47a655417cdf82d79fb222dc6ff6f6d8c3a947
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54601821"
---
# <a name="how-to-flatten-a-curved-path-into-a-line"></a>Instrukcje: Spłaszczanie ścieżki krzywej do linii
A <xref:System.Drawing.Drawing2D.GraphicsPath> obiekt przechowuje sekwencji linii i krzywych Beziera. Można dodać kilka typów krzywych (wielokropek, łuki kardynalne) do ścieżki, ale każda krzywa jest konwertowany na krzywej Beziera, zanim znajduje się w ścieżce. Spłaszczanie ścieżki składa się z konwersji każdego krzywej Beziera w ścieżce z linii prostych sekwencji. Na poniższej ilustracji przedstawiono ścieżkę przed i po nim spłaszczanie.  
  
 ![Proste linii i krzywych](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")  
  
### <a name="to-flatten-a-path"></a>Spłaszczanie ścieżki  
  
-   Wywołaj <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> metody <xref:System.Drawing.Drawing2D.GraphicsPath> obiektu. <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> Metoda otrzymuje argument płaskość, który określa maksymalną odległość między ścieżką spłaszczone i Oryginalna ścieżka.  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- [Linie, krzywe i kształty](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)
- [Konstruowanie i rysowanie ścieżek](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)
