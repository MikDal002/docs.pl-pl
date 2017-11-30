---
title: "FolderBrowserDialog — Informacje o składniku (Formularze systemu Windows)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: FolderBrowserDialog
helpviewer_keywords:
- FolderBrowserDialog component [Windows Forms], about FolderBrowserDialog
- directories [Windows Forms], enabling browsing in applications
- folders [Windows Forms], enabling browsing in applications
ms.assetid: 796b622c-3ba9-4356-93bb-e217fc52f2c7
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d7fab1dbe01c5b21e510841b1541150f6152ab0b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="folderbrowserdialog-component-overview-windows-forms"></a><span data-ttu-id="66c98-102">FolderBrowserDialog — Informacje o składniku (Formularze systemu Windows)</span><span class="sxs-lookup"><span data-stu-id="66c98-102">FolderBrowserDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="66c98-103">Formularze systemu Windows <xref:System.Windows.Forms.FolderBrowserDialog> składnik jest modalne okno dialogowe służy do przeglądania i wybierz foldery.</span><span class="sxs-lookup"><span data-stu-id="66c98-103">The Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> component is a modal dialog box that is used for browsing and selecting folders.</span></span> <span data-ttu-id="66c98-104">Można również tworzyć nowe foldery z poziomu <xref:System.Windows.Forms.FolderBrowserDialog> składnika.</span><span class="sxs-lookup"><span data-stu-id="66c98-104">New folders can also be created from within the <xref:System.Windows.Forms.FolderBrowserDialog> component.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="66c98-105">Aby wybrać pliki zamiast folderów, użyj [OpenFileDialog](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md) składnika.</span><span class="sxs-lookup"><span data-stu-id="66c98-105">To select files, instead of folders, use the [OpenFileDialog](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md) component.</span></span>  
  
 <span data-ttu-id="66c98-106"><xref:System.Windows.Forms.FolderBrowserDialog> Składnika jest wyświetlany w czasie wykonywania za pomocą <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="66c98-106">The <xref:System.Windows.Forms.FolderBrowserDialog> component is displayed at run time using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span> <span data-ttu-id="66c98-107">Ustaw <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> właściwości w celu określenia folderu najwyższy i wszelkich podfolderów, które będą wyświetlane w widoku drzewa okna dialogowego.</span><span class="sxs-lookup"><span data-stu-id="66c98-107">Set the <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> property to determine the top-most folder and any subfolders that will appear within the tree view of the dialog box.</span></span> <span data-ttu-id="66c98-108">Gdy okno dialogowe wykazało, możesz użyć <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> właściwości pobierania ścieżki folderu, który został wybrany.</span><span class="sxs-lookup"><span data-stu-id="66c98-108">Once the dialog box has been shown, you can use the <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property to get the path of the folder that was selected.</span></span>  
  
 <span data-ttu-id="66c98-109">Gdy jest ona dodawana do formularza, <xref:System.Windows.Forms.FolderBrowserDialog> składnika jest wyświetlana na pasku w dolnej części Projektant formularzy systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="66c98-109">When it is added to a form, the <xref:System.Windows.Forms.FolderBrowserDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66c98-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="66c98-110">See Also</span></span>  
 <xref:System.Windows.Forms.FolderBrowserDialog>  
 [<span data-ttu-id="66c98-111">Porady: Wybieranie składnika FolderBrowserDialog formularzy folderów z systemu Windows</span><span class="sxs-lookup"><span data-stu-id="66c98-111">How to: Choose Folders with the Windows Forms FolderBrowserDialog Component</span></span>](../../../../docs/framework/winforms/controls/how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component.md)  
 [<span data-ttu-id="66c98-112">FolderBrowserDialog — składnik</span><span class="sxs-lookup"><span data-stu-id="66c98-112">FolderBrowserDialog Component</span></span>](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-windows-forms.md)