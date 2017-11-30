---
title: "Formularz początkowy nie został określony"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrAppModel_NoStartupForm
ms.assetid: 8e04af49-4bef-49de-a7ec-e407e9873da7
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fdffc182ee66497d68aafb7dc37cfef75b4d2e9f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="a-startup-form-has-not-been-specified"></a><span data-ttu-id="24f50-102">Formularz początkowy nie został określony</span><span class="sxs-lookup"><span data-stu-id="24f50-102">A startup form has not been specified</span></span>
<span data-ttu-id="24f50-103">Aplikacja używa <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> klasy, ale nie określa formularz startowy.</span><span class="sxs-lookup"><span data-stu-id="24f50-103">The application uses the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> class but does not specify the startup form.</span></span>  
  
 <span data-ttu-id="24f50-104">Taka sytuacja może wystąpić, jeśli **struktury aplikacji Włącz** w Projektancie projektu jest zaznaczone pole wyboru, ale **formularz startowy** nie jest określona.</span><span class="sxs-lookup"><span data-stu-id="24f50-104">This can occur if the **Enable application framework** check box is selected in the project designer but the **Startup form** is not specified.</span></span> <span data-ttu-id="24f50-105">Aby uzyskać więcej informacji, zobacz [strona aplikacji, Projektant projektu (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="24f50-105">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="24f50-106">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="24f50-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="24f50-107">Określ obiekt uruchomienia aplikacji.</span><span class="sxs-lookup"><span data-stu-id="24f50-107">Specify a startup object for the application.</span></span>  
  
     <span data-ttu-id="24f50-108">Aby uzyskać więcej informacji, zobacz [strona aplikacji, Projektant projektu (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="24f50-108">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
2.  <span data-ttu-id="24f50-109">Zastąpienie <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> metodę, aby ustawić <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> formularz początkowy dla właściwości.</span><span class="sxs-lookup"><span data-stu-id="24f50-109">Override the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> method to set the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> property to the startup form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24f50-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="24f50-110">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>  
 [<span data-ttu-id="24f50-111">Omówienie modelu aplikacji Visual Basic</span><span class="sxs-lookup"><span data-stu-id="24f50-111">Overview of the Visual Basic Application Model</span></span>](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)