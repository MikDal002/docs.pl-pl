---
title: 'Porady: wyliczanie zainstalowanych czcionek'
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
- fonts [Windows Forms], enumerating installed
- examples [Windows Forms], fonts
ms.assetid: 26d74ef5-0f39-4eeb-8d20-00e66e014abe
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bca536ed2f3e493e8d50fe8f1a0115327f1d8720
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-enumerate-installed-fonts"></a><span data-ttu-id="fef6c-102">Porady: wyliczanie zainstalowanych czcionek</span><span class="sxs-lookup"><span data-stu-id="fef6c-102">How to: Enumerate Installed Fonts</span></span>
<span data-ttu-id="fef6c-103"><xref:System.Drawing.Text.InstalledFontCollection> Klasa dziedziczy <xref:System.Drawing.Text.FontCollection> abstrakcyjnej klasy podstawowej.</span><span class="sxs-lookup"><span data-stu-id="fef6c-103">The <xref:System.Drawing.Text.InstalledFontCollection> class inherits from the <xref:System.Drawing.Text.FontCollection> abstract base class.</span></span> <span data-ttu-id="fef6c-104">Można użyć <xref:System.Drawing.Text.InstalledFontCollection> obiektu wyliczyć czcionek zainstalowanych na komputerze.</span><span class="sxs-lookup"><span data-stu-id="fef6c-104">You can use an <xref:System.Drawing.Text.InstalledFontCollection> object to enumerate the fonts installed on the computer.</span></span> <span data-ttu-id="fef6c-105"><xref:System.Drawing.Text.FontCollection.Families%2A> Właściwość <xref:System.Drawing.Text.InstalledFontCollection> obiektu to tablica <xref:System.Drawing.FontFamily> obiektów.</span><span class="sxs-lookup"><span data-stu-id="fef6c-105">The <xref:System.Drawing.Text.FontCollection.Families%2A> property of an <xref:System.Drawing.Text.InstalledFontCollection> object is an array of <xref:System.Drawing.FontFamily> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fef6c-106">Przykład</span><span class="sxs-lookup"><span data-stu-id="fef6c-106">Example</span></span>  
 <span data-ttu-id="fef6c-107">Poniższy przykład zawiera listę nazw rodzin czcionek zainstalowanych na komputerze.</span><span class="sxs-lookup"><span data-stu-id="fef6c-107">The following example lists the names of all the font families installed on the computer.</span></span> <span data-ttu-id="fef6c-108">Pobiera kod <xref:System.Drawing.FontFamily.Name%2A> właściwości każdego <xref:System.Drawing.FontFamily> obiektu w tablicy zwracanej przez <xref:System.Drawing.Text.FontCollection.Families%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="fef6c-108">The code retrieves the <xref:System.Drawing.FontFamily.Name%2A> property of each <xref:System.Drawing.FontFamily> object in the array returned by the <xref:System.Drawing.Text.FontCollection.Families%2A> property.</span></span> <span data-ttu-id="fef6c-109">Jako nazwy rodziny są pobierane, są one połączone do postaci rozdzielanej przecinkami listy.</span><span class="sxs-lookup"><span data-stu-id="fef6c-109">As the family names are retrieved, they are concatenated to form a comma-separated list.</span></span> <span data-ttu-id="fef6c-110">Następnie przy użyciu <xref:System.Drawing.Graphics.DrawString%2A> metody <xref:System.Drawing.Graphics> klasy rysuje listy rozdzielanej przecinkami w prostokącie.</span><span class="sxs-lookup"><span data-stu-id="fef6c-110">Then the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class draws the comma-separated list in a rectangle.</span></span>  
  
 <span data-ttu-id="fef6c-111">Po uruchomieniu przykładowy kod dane wyjściowe będą podobne jak pokazano na poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="fef6c-111">If you run the example code, the output will be similar to that shown in the following illustration.</span></span>  
  
 <span data-ttu-id="fef6c-112">![Zainstalowane czcionki](../../../../docs/framework/winforms/advanced/media/csfontstext6.png "csfontstext6")</span><span class="sxs-lookup"><span data-stu-id="fef6c-112">![Installed Fonts](../../../../docs/framework/winforms/advanced/media/csfontstext6.png "csfontstext6")</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.FontsAndText#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fef6c-113">Kompilowanie kodu</span><span class="sxs-lookup"><span data-stu-id="fef6c-113">Compiling the Code</span></span>  
 <span data-ttu-id="fef6c-114">Powyższy przykład jest przeznaczony do użytku z formularzy systemu Windows i wymaga <xref:System.Windows.Forms.PaintEventArgs> `e`, który jest parametrem <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="fef6c-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span> <span data-ttu-id="fef6c-115">Ponadto należy zaimportować <xref:System.Drawing.Text> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="fef6c-115">In addition, you should import the <xref:System.Drawing.Text> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fef6c-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="fef6c-116">See Also</span></span>  
 [<span data-ttu-id="fef6c-117">Używanie czcionek i tekstu</span><span class="sxs-lookup"><span data-stu-id="fef6c-117">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)