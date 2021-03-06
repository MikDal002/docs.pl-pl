---
title: Wywoływanie formantu przy użyciu automatyzacji interfejsu użytkownika
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- invoking controls
- UI Automation, invoking controls
- controls, invoking
ms.assetid: 5ee2de3f-256c-43ec-b64c-62ace91f9983
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: b4ee4b4929d5aa80ccfb91d07031b4ab195d311e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54654779"
---
# <a name="invoke-a-control-using-ui-automation"></a>Wywoływanie kontrolki przy użyciu automatyzacji interfejsu użytkownika
> [!NOTE]
>  Ta dokumentacja jest przeznaczona dla deweloperów .NET Framework, którzy chcą używać zarządzanych [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] klas zdefiniowanych w <xref:System.Windows.Automation> przestrzeni nazw. Aby uzyskać najnowsze informacje o [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], zobacz [Windows Automation API: Automatyzacja interfejsu użytkownika](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 W tym temacie przedstawiono sposób wykonywania następujących zadań:  
  
-   Znajdź formant, który dopasowuje warunki określonej właściwości przy zalet widoku kontrolnym [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] drzewa dla aplikacji docelowej.  
  
-   Utwórz <xref:System.Windows.Automation.AutomationElement> dla każdego formantu.  
  
-   Uzyskaj <xref:System.Windows.Automation.InvokePattern> obiektu za pomocą dowolnego [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] znaleziony element, który obsługuje <xref:System.Windows.Automation.InvokePattern> — wzorzec kontrolki.  
  
-   Użyj <xref:System.Windows.Automation.InvokePattern.Invoke%2A> do wywołania kontrolki z obsługi zdarzeń klienta.  
  
## <a name="example"></a>Przykład  
 W tym przykładzie użyto <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> metody <xref:System.Windows.Automation.AutomationElement> klasy do generowania <xref:System.Windows.Automation.InvokePattern> obiektu i wywoływanie kontrolki przy użyciu <xref:System.Windows.Automation.InvokePattern.Invoke%2A> metody.  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
[!code-csharp[InvokePatternApp#1102](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1102)]
[!code-vb[InvokePatternApp#1102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1102)]  
  
## <a name="see-also"></a>Zobacz także
- [Klasy InvokePattern i przykładowych elementów Menu klasy ExpandCollapsePattern](https://msdn.microsoft.com/library/b7fa141c-e2d1-4da2-a27f-81a7d1172210)
