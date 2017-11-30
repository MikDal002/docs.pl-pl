---
title: "Porady: wyrównywanie narysowanego tekstu"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], aligning
- Windows Forms, aligning drawn text
ms.assetid: 83c10a81-1a90-4b5c-98aa-2c6c4b280079
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a2f2f6bd088ad58277839cf7e32a98d67ca3bd15
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-align-drawn-text"></a><span data-ttu-id="b8d8a-102">Porady: wyrównywanie narysowanego tekstu</span><span class="sxs-lookup"><span data-stu-id="b8d8a-102">How to: Align Drawn Text</span></span>
<span data-ttu-id="b8d8a-103">Podczas wykonywania Rysowanie niestandardowe można często Centrum narysowanego tekstu na formularz lub formant.</span><span class="sxs-lookup"><span data-stu-id="b8d8a-103">When you perform custom drawing, you may often want to center drawn text on a form or control.</span></span> <span data-ttu-id="b8d8a-104">Można łatwo Dopasuj narysowany tekst <xref:System.Drawing.Graphics.DrawString%2A> lub <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metod tworzenia prawidłowy obiekt formatowania i ustawiając flagi w odpowiednim formacie.</span><span class="sxs-lookup"><span data-stu-id="b8d8a-104">You can easily align text drawn with the <xref:System.Drawing.Graphics.DrawString%2A> or <xref:System.Windows.Forms.TextRenderer.DrawText%2A> methods by creating the correct formatting object and setting the appropriate format flags.</span></span>  
  
### <a name="to-draw-centered-text-with-gdi-drawstring"></a><span data-ttu-id="b8d8a-105">Rysowanie wyśrodkowany tekst mający GDI + (sznurkiem)</span><span class="sxs-lookup"><span data-stu-id="b8d8a-105">To draw centered text with GDI+ (DrawString)</span></span>  
  
1.  <span data-ttu-id="b8d8a-106">Użyj <xref:System.Drawing.StringFormat> z odpowiednią <xref:System.Drawing.Graphics.DrawString%2A> metodę, aby określić wyśrodkowany tekst.</span><span class="sxs-lookup"><span data-stu-id="b8d8a-106">Use a <xref:System.Drawing.StringFormat> with the appropriate <xref:System.Drawing.Graphics.DrawString%2A> method to specify centered text.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#10)]
     [!code-vb[System.Drawing.AlignDrawnText#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#10)]  
  
### <a name="to-draw-centered-text-with-gdi-drawtext"></a><span data-ttu-id="b8d8a-107">Rysowanie wyśrodkowany tekst mający GDI (DrawText)</span><span class="sxs-lookup"><span data-stu-id="b8d8a-107">To draw centered text with GDI (DrawText)</span></span>  
  
1.  <span data-ttu-id="b8d8a-108">Użyj <xref:System.Windows.Forms.TextFormatFlags> wyliczenie dla zawijania, jak również w poziomie i w pionie wyśrodkowanie tekstu z odpowiednią <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="b8d8a-108">Use the <xref:System.Windows.Forms.TextFormatFlags> enumeration for wrapping as well as vertically and horizontally centering text with the appropriate <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#20)]
     [!code-vb[System.Drawing.AlignDrawnText#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#20)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b8d8a-109">Kompilowanie kodu</span><span class="sxs-lookup"><span data-stu-id="b8d8a-109">Compiling the Code</span></span>  
 <span data-ttu-id="b8d8a-110">W powyższych przykładach kodu są przeznaczone do użytku z formularzy systemu Windows, a potrzebują <xref:System.Windows.Forms.PaintEventArgs> `e`, który jest parametrem <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="b8d8a-110">The preceding code examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8d8a-111">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b8d8a-111">See Also</span></span>  
 [<span data-ttu-id="b8d8a-112">Porady: Rysowanie tekstu z GDI</span><span class="sxs-lookup"><span data-stu-id="b8d8a-112">How to: Draw Text with GDI</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 [<span data-ttu-id="b8d8a-113">Używanie czcionek i tekstu</span><span class="sxs-lookup"><span data-stu-id="b8d8a-113">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [<span data-ttu-id="b8d8a-114">Porady: tworzenie rodzin czcionek i czcionek</span><span class="sxs-lookup"><span data-stu-id="b8d8a-114">How to: Construct Font Families and Fonts</span></span>](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)