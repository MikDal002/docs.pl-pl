---
title: "Używanie modelu DOM (Document Object Model) zarządzanych dokumentów HTML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: managed HTML DOM
ms.assetid: a017dd5c-cd7b-47e4-952c-f4f54cb48409
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ff1004248e709b4b4913b90eb81f0726ab390c54
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="using-the-managed-html-document-object-model"></a><span data-ttu-id="a783d-102">Używanie modelu DOM (Document Object Model) zarządzanych dokumentów HTML</span><span class="sxs-lookup"><span data-stu-id="a783d-102">Using the Managed HTML Document Object Model</span></span>
<span data-ttu-id="a783d-103">Zarządzane modelu obiektu dokumentu HTML (DOM) udostępnia otokę na podstawie [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] dla klas HTML udostępnianych przez program Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="a783d-103">The managed HTML document object model (DOM) provides a wrapper based on the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] for the HTML classes exposed by Internet Explorer.</span></span> <span data-ttu-id="a783d-104">Korzystając z tych klas do manipulowania stron HTML znajdujących się w <xref:System.Windows.Forms.WebBrowser> kontroli, lub do tworzenia nowych stron od początku.</span><span class="sxs-lookup"><span data-stu-id="a783d-104">Use these classes to manipulate HTML pages hosted in the <xref:System.Windows.Forms.WebBrowser> control, or to build new pages from the beginning.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a783d-105">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="a783d-105">In This Section</span></span>  
 [<span data-ttu-id="a783d-106">Porady: dostęp do modelu obiektów zarządzanych dokumentów HTML</span><span class="sxs-lookup"><span data-stu-id="a783d-106">How to: Access the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/how-to-access-the-managed-html-document-object-model.md)  
 <span data-ttu-id="a783d-107">Opisuje sposób uzyskać prawidłową instancją <xref:System.Windows.Forms.HtmlDocument> z aplikacji formularzy systemu Windows lub <xref:System.Windows.Forms.UserControl> hostowanej w programie Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="a783d-107">Describes how to obtain a valid instance of <xref:System.Windows.Forms.HtmlDocument> from either a Windows Forms application or a <xref:System.Windows.Forms.UserControl> hosted in Internet Explorer.</span></span>  
  
 [<span data-ttu-id="a783d-108">Porady: uzyskiwanie dostępu do źródła HTML w modelu obiektów zarządzanych dokumentów HTML</span><span class="sxs-lookup"><span data-stu-id="a783d-108">How to: Access the HTML Source in the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/how-to-access-the-html-source-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="a783d-109">W tym artykule opisano sposób uzyskiwania oryginalnego, bez modyfikacji źródła HTML i sposobie uzyskania źródła "na żywo", która odzwierciedla bieżący stan modelu DOM.</span><span class="sxs-lookup"><span data-stu-id="a783d-109">Describes how to obtain the original, unmodified HTML source, and how to obtain the "live" source that reflects the current state of the DOM.</span></span>  
  
 [<span data-ttu-id="a783d-110">Porady: Zmienianie stylu elementu w modelu obiektów zarządzanych dokumentów HTML</span><span class="sxs-lookup"><span data-stu-id="a783d-110">How to: Change Styles on an Element in the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/how-to-change-styles-on-an-element-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="a783d-111">Opisuje sposób modyfikowania style, które są używane do kontrolowania wyświetlania elementów.</span><span class="sxs-lookup"><span data-stu-id="a783d-111">Describes how to manipulate styles, which are used to control the visual display of elements.</span></span>  
  
 [<span data-ttu-id="a783d-112">Uzyskiwanie dostępu do ramek w modelu obiektów zarządzanych dokumentów HTML</span><span class="sxs-lookup"><span data-stu-id="a783d-112">Accessing Frames in the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/accessing-frames-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="a783d-113">W tym artykule opisano, jakie są ramek i zestawu ramek oraz uzyskania dostępu do modelu DOM ramki.</span><span class="sxs-lookup"><span data-stu-id="a783d-113">Describes what frames and framesets are, and how to access the DOM of a frame.</span></span>  
  
 [<span data-ttu-id="a783d-114">Uzyskiwanie dostępu do nieujawnionych elementów w modelu obiektów zarządzanych dokumentów HTML</span><span class="sxs-lookup"><span data-stu-id="a783d-114">Accessing Unexposed Members on the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/accessing-unexposed-members-on-the-managed-html-document-object-model.md)  
 <span data-ttu-id="a783d-115">Opisuje sposób dostęp do elementów członkowskich podstawowego modelu DOM, które nie mają odpowiednika zarządzanych.</span><span class="sxs-lookup"><span data-stu-id="a783d-115">Describes how to access members of the underlying DOM that do not have a managed equivalent.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="a783d-116">Tematy pomocy</span><span class="sxs-lookup"><span data-stu-id="a783d-116">Reference</span></span>  
 <xref:System.Windows.Forms.HtmlDocument>  
  
 <xref:System.Windows.Forms.HtmlElement>  
  
 <xref:System.Windows.Forms.HtmlWindow>  
  
## <a name="related-sections"></a><span data-ttu-id="a783d-117">Sekcje pokrewne</span><span class="sxs-lookup"><span data-stu-id="a783d-117">Related Sections</span></span>  
 [<span data-ttu-id="a783d-118">WebBrowser — formant</span><span class="sxs-lookup"><span data-stu-id="a783d-118">WebBrowser Control</span></span>](../../../../docs/framework/winforms/controls/webbrowser-control-windows-forms.md)  
  
## <a name="see-also"></a><span data-ttu-id="a783d-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a783d-119">See Also</span></span>  
 [<span data-ttu-id="a783d-120">O Model obiektowy DHTML</span><span class="sxs-lookup"><span data-stu-id="a783d-120">About the DHTML Object Model</span></span>](http://msdn.microsoft.com/library/default.asp?url=/workshop/author/om/doc_object.asp)