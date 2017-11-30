---
title: "Porady: tworzenie formularzy systemu Windows o określonych kształtach"
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
- cpp
helpviewer_keywords:
- forms [Windows Forms], rounded
- Windows Forms, custom shapes
- Windows Forms, shaped
- shaped forms
- forms [Windows Forms], changing the shape of
- forms [Windows Forms], circular
- forms [Windows Forms], nonrectangular
- Windows Forms, nonrectangular shape
- Windows Forms, rounded
- Windows Forms, circular
- forms [Windows Forms], custom shapes
ms.assetid: 6e6041e0-8e67-4487-b1e9-e410dbd1ef6c
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 981256c2447a53aef8e1ea676db38ce693d1337e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-shaped-windows-form"></a><span data-ttu-id="454cf-102">Porady: tworzenie formularzy systemu Windows o określonych kształtach</span><span class="sxs-lookup"><span data-stu-id="454cf-102">How to: Create a Shaped Windows Form</span></span>
<span data-ttu-id="454cf-103">W tym przykładzie zapewnia formularza eliptycznej kształtu, który zmienia rozmiar w formularzu.</span><span class="sxs-lookup"><span data-stu-id="454cf-103">This example gives a form an elliptical shape that resizes with the form.</span></span>  
  
## <a name="example"></a><span data-ttu-id="454cf-104">Przykład</span><span class="sxs-lookup"><span data-stu-id="454cf-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#10](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#10)]
 [!code-csharp[System.Drawing.ConceptualHowTos#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#10)]
 [!code-vb[System.Drawing.ConceptualHowTos#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="454cf-105">Kompilowanie kodu</span><span class="sxs-lookup"><span data-stu-id="454cf-105">Compiling the Code</span></span>  
 <span data-ttu-id="454cf-106">Ten przykład wymaga:</span><span class="sxs-lookup"><span data-stu-id="454cf-106">This example requires:</span></span>  
  
-   <span data-ttu-id="454cf-107">Odwołuje się do <xref:System.Windows.Forms> i <xref:System.Drawing> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="454cf-107">References to the <xref:System.Windows.Forms> and <xref:System.Drawing> namespaces.</span></span>  
  
 <span data-ttu-id="454cf-108">Ten przykład zastępuje <xref:System.Windows.Forms.Control.OnPaint%2A> metodę, aby zmienić kształt formularza.</span><span class="sxs-lookup"><span data-stu-id="454cf-108">This example overrides the <xref:System.Windows.Forms.Control.OnPaint%2A> method to change the shape of the form.</span></span> <span data-ttu-id="454cf-109">Aby użyć tego kodu, skopiuj deklaracji metody, a także kod rysowania wewnątrz metody.</span><span class="sxs-lookup"><span data-stu-id="454cf-109">To use this code, copy the method declaration as well as the drawing code inside the method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="454cf-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="454cf-110">See Also</span></span>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 <xref:System.Drawing.Region>  
 <xref:System.Drawing>  
 <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>  
 <xref:System.Windows.Forms.Control.Region%2A>  
 [<span data-ttu-id="454cf-111">Wprowadzenie do programowania grafiki</span><span class="sxs-lookup"><span data-stu-id="454cf-111">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)