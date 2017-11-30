---
title: Systemy Pomocy w aplikacjach Windows Forms
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Help [Windows Forms], adding to Windows applications
- Windows applications [Windows Forms], providing Help systems
- What's This? Help
- Help [Windows Forms], Windows Forms
- HelpProvider component [Windows Forms], providing Help in Windows applications
ms.assetid: 2a96a278-432c-41fc-9e3c-5bfedf5e1267
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 45d3385d008f823050f213252fdc2e1851cf422b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="help-systems-in-windows-forms-applications"></a><span data-ttu-id="8de9f-102">Systemy Pomocy w aplikacjach Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8de9f-102">Help Systems in Windows Forms Applications</span></span>
<span data-ttu-id="8de9f-103">Jednym z najważniejszych courtesies, jako Deweloper aplikacji, można dostarczyć użytkownikom jest właściwy system pomocy.</span><span class="sxs-lookup"><span data-stu-id="8de9f-103">One of the most important courtesies you, as a developer of applications, can furnish your users with is a competent Help system.</span></span> <span data-ttu-id="8de9f-104">Jest to, gdzie spowoduje wyłączenie, gdy stają się pomylić lub disoriented.</span><span class="sxs-lookup"><span data-stu-id="8de9f-104">This is where they will turn when they become confused or disoriented.</span></span> <span data-ttu-id="8de9f-105">Zapewnianie system pomocy w aplikacji opartych na systemie Windows łatwo odbywa się przy użyciu [helpprovider — składnik](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="8de9f-105">Providing a Help system in a Windows-based application is easily done by using the [HelpProvider Component](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md).</span></span>  
  
## <a name="different-types-of-help"></a><span data-ttu-id="8de9f-106">Różne rodzaje pomocy</span><span class="sxs-lookup"><span data-stu-id="8de9f-106">Different Types of Help</span></span>  
 <span data-ttu-id="8de9f-107">Formularze systemu Windows <xref:System.Windows.Forms.HelpProvider> składnika służy do kojarzenia pomocy HTML 1.x pliku pomocy (plik .chm produkowanych Workshop pomocy HTML, lub plik htm) z aplikacji opartych na systemie Windows.</span><span class="sxs-lookup"><span data-stu-id="8de9f-107">The Windows Forms <xref:System.Windows.Forms.HelpProvider> component is used to associate an HTML Help 1.x Help file (either a .chm file, produced with the HTML Help Workshop, or an .htm file) with your Windows-based application.</span></span> <span data-ttu-id="8de9f-108"><xref:System.Windows.Forms.HelpProvider> Składnika może służyć do zapewnienia pomocy kontekstowej dla formantów na formularzach systemu Windows lub kontrolek.</span><span class="sxs-lookup"><span data-stu-id="8de9f-108">The <xref:System.Windows.Forms.HelpProvider> component can be used to provide context-sensitive Help for controls on Windows Forms or specific controls.</span></span> <span data-ttu-id="8de9f-109">Ponadto <xref:System.Windows.Forms.HelpProvider> składnika można otworzyć pliku pomocy do określonych obszarów, takich jak strona główna spisu treści, indeksu lub funkcję wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="8de9f-109">Additionally, the <xref:System.Windows.Forms.HelpProvider> component can open a Help file to specific areas, such as the main page of a table of contents, an index, or a search function.</span></span> <span data-ttu-id="8de9f-110">Aby uzyskać ogólne informacje o <xref:System.Windows.Forms.HelpProvider> składników, zobacz [informacje o składniku helpprovider —](../../../../docs/framework/winforms/controls/helpprovider-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="8de9f-110">For general information about the <xref:System.Windows.Forms.HelpProvider> component, see [HelpProvider Component Overview](../../../../docs/framework/winforms/controls/helpprovider-component-overview-windows-forms.md).</span></span> <span data-ttu-id="8de9f-111">Aby uzyskać informacje dotyczące sposobu używania <xref:System.Windows.Forms.HelpProvider> składnik, aby wyświetlić Pomoc wyskakująca w formularzach systemu Windows, zobacz [jak: Wyświetl Pomoc wyskakujących](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md).</span><span class="sxs-lookup"><span data-stu-id="8de9f-111">For information on how to use the <xref:System.Windows.Forms.HelpProvider> component to show pop-up Help on Windows Forms, see [How to: Display Pop-up Help](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md).</span></span> <span data-ttu-id="8de9f-112">Informacji na temat używania <xref:System.Windows.Forms.ToolTip> składnik, aby wyświetlić Pomoc dotyczącą kontroli, zobacz [pomocy formantu przy użyciu etykietki narzędzi](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md).</span><span class="sxs-lookup"><span data-stu-id="8de9f-112">For information on using the <xref:System.Windows.Forms.ToolTip> component to show control-specific Help, see [Control Help Using ToolTips](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md).</span></span>  
  
 <span data-ttu-id="8de9f-113">Można wygenerować plików 1.x pomocy HTML z Workshop pomocy HTML.</span><span class="sxs-lookup"><span data-stu-id="8de9f-113">You can generate HTML Help 1.x files with the HTML Help Workshop.</span></span> <span data-ttu-id="8de9f-114">Aby uzyskać więcej informacji dotyczących pomocy HTML zobacz "HTML Help Workshop" lub innych "HTML" tematów w witrynie MSDN.</span><span class="sxs-lookup"><span data-stu-id="8de9f-114">For more information on HTML Help, see the "HTML Help Workshop" or the other "HTML Help" topics in MSDN.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8de9f-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8de9f-115">See Also</span></span>  
 [<span data-ttu-id="8de9f-116">Integrowanie pomocy użytkownika w formularzach systemu Windows</span><span class="sxs-lookup"><span data-stu-id="8de9f-116">Integrating User Help in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/integrating-user-help-in-windows-forms.md)  
 [<span data-ttu-id="8de9f-117">Helpprovider — składnik</span><span class="sxs-lookup"><span data-stu-id="8de9f-117">HelpProvider Component</span></span>](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md)  
 [<span data-ttu-id="8de9f-118">ToolTip — składnik</span><span class="sxs-lookup"><span data-stu-id="8de9f-118">ToolTip Component</span></span>](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)  
 [<span data-ttu-id="8de9f-119">Przegląd formularzy systemu Windows</span><span class="sxs-lookup"><span data-stu-id="8de9f-119">Windows Forms Overview</span></span>](../../../../docs/framework/winforms/windows-forms-overview.md)  
 [<span data-ttu-id="8de9f-120">Formularze systemu Windows</span><span class="sxs-lookup"><span data-stu-id="8de9f-120">Windows Forms</span></span>](../../../../docs/framework/winforms/index.md)