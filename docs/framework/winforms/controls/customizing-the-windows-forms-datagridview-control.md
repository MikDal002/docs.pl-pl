---
title: Dostosowywanie formantu DataGridView formularzy systemu Windows
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data grids [Windows Forms], customization
- DataGridView control [Windows Forms], customization
ms.assetid: 01ea5d4c-a736-4596-b0e9-a67a1b86e15f
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7d1246a8052af19057f7aa9d6729e34203177f8e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="customizing-the-windows-forms-datagridview-control"></a><span data-ttu-id="8dbbe-102">Dostosowywanie formantu DataGridView formularzy systemu Windows</span><span class="sxs-lookup"><span data-stu-id="8dbbe-102">Customizing the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="8dbbe-103">`DataGridView` Kontrola zapewnia kilka właściwości, które można dostosować wygląd i zachowanie podstawowe (wyglądu i działania), jego komórek, wierszy i kolumn.</span><span class="sxs-lookup"><span data-stu-id="8dbbe-103">The `DataGridView` control provides several properties that you can use to adjust the appearance and basic behavior (look and feel) of its cells, rows, and columns.</span></span> <span data-ttu-id="8dbbe-104">Jeśli masz specjalnymi potrzebami, które wykraczają poza możliwości <xref:System.Windows.Forms.DataGridViewCellStyle> klasy, jednak można zaimplementować rysowanie formantu przez właściciela lub rozszerzyć jej możliwości, tworząc niestandardowe komórek, kolumn i wierszy.</span><span class="sxs-lookup"><span data-stu-id="8dbbe-104">If you have special needs that go beyond the capabilities of the <xref:System.Windows.Forms.DataGridViewCellStyle> class, however, you can also implement owner drawing for the control or extend its capabilities by creating custom cells, columns, and rows.</span></span>  
  
 <span data-ttu-id="8dbbe-105">Namalować komórek i wierszy samodzielnie, może obsługiwać różne `DataGridView` zdarzenia rysowania.</span><span class="sxs-lookup"><span data-stu-id="8dbbe-105">To paint cells and rows yourself, you can handle various `DataGridView` painting events.</span></span> <span data-ttu-id="8dbbe-106">Aby zmodyfikować istniejące funkcje lub udostępnia nowych funkcji, można utworzyć własne typy pochodzące z istniejącego `DataGridViewCell`, `DataGridViewColumn`, i `DataGridViewRow` typów.</span><span class="sxs-lookup"><span data-stu-id="8dbbe-106">To modify existing functionality or provide new functionality, you can create your own types derived from the existing `DataGridViewCell`, `DataGridViewColumn`, and `DataGridViewRow` types.</span></span> <span data-ttu-id="8dbbe-107">Można też podać nowe możliwości edytowania przez tworzenie typów pochodnych zawierających formantu użytkownika wybrać, gdy komórka jest w trybie edycji.</span><span class="sxs-lookup"><span data-stu-id="8dbbe-107">You can also provide new editing capabilities by creating derived types that display a control of your choosing when a cell is in edit mode.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8dbbe-108">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="8dbbe-108">In This Section</span></span>  
 [<span data-ttu-id="8dbbe-109">Porady: Dostosowywanie wyglądu komórek w formancie DataGridView formularzy systemu Windows</span><span class="sxs-lookup"><span data-stu-id="8dbbe-109">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md)  
 <span data-ttu-id="8dbbe-110">Opisuje sposób obsługi <xref:System.Windows.Forms.DataGridView.CellPainting> zdarzeń w celu rysowania komórek ręcznie.</span><span class="sxs-lookup"><span data-stu-id="8dbbe-110">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellPainting> event in order to paint cells manually.</span></span>  
  
 [<span data-ttu-id="8dbbe-111">Porady: Dostosowywanie wyglądu wierszy w formancie DataGridView formularzy systemu Windows</span><span class="sxs-lookup"><span data-stu-id="8dbbe-111">How to: Customize the Appearance of Rows in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customize-the-appearance-of-rows-in-the-datagrid.md)  
 <span data-ttu-id="8dbbe-112">Opisuje sposób obsługi <xref:System.Windows.Forms.DataGridView.RowPrePaint> i <xref:System.Windows.Forms.DataGridView.RowPostPaint> zdarzeń w celu rysowania wiersze z niestandardowych, gradientu tła i zawartością, która obejmuje wielu kolumn.</span><span class="sxs-lookup"><span data-stu-id="8dbbe-112">Describes how to handle the <xref:System.Windows.Forms.DataGridView.RowPrePaint> and <xref:System.Windows.Forms.DataGridView.RowPostPaint> events in order to paint rows with a custom, gradient background and content that spans multiple columns.</span></span>  
  
 [<span data-ttu-id="8dbbe-113">Porady: dostosowywanie komórek i kolumn w oknach formantu DataGridView formularzy przez rozszerzanie ich zachowania i wyglądu</span><span class="sxs-lookup"><span data-stu-id="8dbbe-113">How to: Customize Cells and Columns in the Windows Forms DataGridView Control by Extending Their Behavior and Appearance</span></span>](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)  
 <span data-ttu-id="8dbbe-114">Opisuje sposób tworzenia niestandardowych typów pochodnych `DataGridViewCell` i `DataGridViewColumn` aby wyróżnić komórki, gdy wskaźnik myszy znajduje się na nich.</span><span class="sxs-lookup"><span data-stu-id="8dbbe-114">Describes how to create custom types derived from `DataGridViewCell` and `DataGridViewColumn` in order to highlight cells when the mouse pointer rests on them.</span></span>  
  
 [<span data-ttu-id="8dbbe-115">Porady: wyłączanie przycisków w kolumnie przycisków w oknach formantu DataGridView formularzy</span><span class="sxs-lookup"><span data-stu-id="8dbbe-115">How to: Disable Buttons in a Button Column in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/disable-buttons-in-a-button-column-in-the-datagrid.md)  
 <span data-ttu-id="8dbbe-116">Opisuje sposób tworzenia niestandardowych typów pochodnych <xref:System.Windows.Forms.DataGridViewButtonCell> i <xref:System.Windows.Forms.DataGridViewButtonColumn> w celu wyświetlenia wyłączone przycisków w kolumnie przycisków.</span><span class="sxs-lookup"><span data-stu-id="8dbbe-116">Describes how to create custom types derived from <xref:System.Windows.Forms.DataGridViewButtonCell> and <xref:System.Windows.Forms.DataGridViewButtonColumn> in order to display disabled buttons in a button column.</span></span>  
  
 [<span data-ttu-id="8dbbe-117">Porady: formanty hosta w formularzach systemu Windows komórek DataGridView</span><span class="sxs-lookup"><span data-stu-id="8dbbe-117">How to: Host Controls in Windows Forms DataGridView Cells</span></span>](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md)  
 <span data-ttu-id="8dbbe-118">Opisuje sposób wdrożenia `IDataGridViewEditingControl` interfejsu i tworzyć niestandardowych typów pochodnych `DataGridViewCell` i `DataGridViewColumn` w celu wyświetlenia <xref:System.Windows.Forms.DateTimePicker> kontroli, gdy komórka jest w trybie edycji.</span><span class="sxs-lookup"><span data-stu-id="8dbbe-118">Describes how to implement the `IDataGridViewEditingControl` interface and create custom types derived from `DataGridViewCell` and `DataGridViewColumn` in order to display a <xref:System.Windows.Forms.DateTimePicker> control when a cell is in edit mode.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="8dbbe-119">Tematy pomocy</span><span class="sxs-lookup"><span data-stu-id="8dbbe-119">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="8dbbe-120">Zawiera dokumentacja referencyjna dla <xref:System.Windows.Forms.DataGridView> formantu.</span><span class="sxs-lookup"><span data-stu-id="8dbbe-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewCell>  
 <span data-ttu-id="8dbbe-121">Zawiera dokumentacja referencyjna dla <xref:System.Windows.Forms.DataGridViewCell> klasy.</span><span class="sxs-lookup"><span data-stu-id="8dbbe-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewCell> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewRow>  
 <span data-ttu-id="8dbbe-122">Zawiera dokumentacja referencyjna dla <xref:System.Windows.Forms.DataGridViewRow> klasy.</span><span class="sxs-lookup"><span data-stu-id="8dbbe-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewRow> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 <span data-ttu-id="8dbbe-123">Zawiera dokumentacja referencyjna dla <xref:System.Windows.Forms.DataGridViewColumn> klasy.</span><span class="sxs-lookup"><span data-stu-id="8dbbe-123">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumn> class.</span></span>  
  
 <xref:System.Windows.Forms.IDataGridViewEditingControl>  
 <span data-ttu-id="8dbbe-124">Zawiera dokumentacja referencyjna dla <xref:System.Windows.Forms.IDataGridViewEditingControl> interfejsu.</span><span class="sxs-lookup"><span data-stu-id="8dbbe-124">Provides reference documentation for the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8dbbe-125">Sekcje pokrewne</span><span class="sxs-lookup"><span data-stu-id="8dbbe-125">Related Sections</span></span>  
 [<span data-ttu-id="8dbbe-126">Podstawowe formatowanie i style w oknach formantu DataGridView formularzy</span><span class="sxs-lookup"><span data-stu-id="8dbbe-126">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="8dbbe-127">Udostępnia tematach opisano sposób modyfikowania podstawowe wygląd formantu i formatowania wyświetlania danych komórki.</span><span class="sxs-lookup"><span data-stu-id="8dbbe-127">Provides topics that describe how to modify the basic appearance of the control and the display formatting of cell data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dbbe-128">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8dbbe-128">See Also</span></span>  
 [<span data-ttu-id="8dbbe-129">DataGridView — formant</span><span class="sxs-lookup"><span data-stu-id="8dbbe-129">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [<span data-ttu-id="8dbbe-130">Typy kolumn w formancie DataGridView formularzy systemu Windows</span><span class="sxs-lookup"><span data-stu-id="8dbbe-130">Column Types in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)