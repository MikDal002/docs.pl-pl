---
title: Uzyskiwanie atrybutów tekstu przy użyciu automatyzacji interfejsu użytkownika
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting, text attributes
- UI Automation, getting text attributes
- text attributes, getting
ms.assetid: fdefc6c3-b836-4cfe-8dec-1484bfdc5551
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: 62abb18e9ef43e78c0e908b94f3ed9fc69861c7b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54512583"
---
# <a name="obtain-text-attributes-using-ui-automation"></a>Uzyskiwanie atrybutów tekstu przy użyciu automatyzacji interfejsu użytkownika
> [!NOTE]
>  Ta dokumentacja jest przeznaczona dla deweloperów .NET Framework, którzy chcą używać zarządzanych [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] klas zdefiniowanych w <xref:System.Windows.Automation> przestrzeni nazw. Aby uzyskać najnowsze informacje o [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], zobacz [Windows Automation API: Automatyzacja interfejsu użytkownika](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 W tym temacie pokazano, jak używać [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] na uzyskiwanie atrybutów tekstu z zakresu tekstu. Zakres tekstu może odpowiadać w bieżącej lokalizacji karetki (lub zdegenerowanym zaznaczenia) w dokumencie, wyboru ciągłego, tekstu, zbiór zaznaczenia tekstu rozłączne lub całej zawartości tekstowej dokumentu.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład kodu demonstruje sposób uzyskiwania <xref:System.Windows.Automation.TextPattern.FontNameAttribute> z zakresu tekstu.  
  
 [!code-csharp[UIATextPattern_snip#StartTarget](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#starttarget)]
 [!code-vb[UIATextPattern_snip#StartTarget](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATextPattern_snip/VisualBasic/SearchWindow.vb#starttarget)]  
[!code-csharp[UIATextPattern_snip#GetTextElement](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#gettextelement)]
[!code-vb[UIATextPattern_snip#GetTextElement](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATextPattern_snip/VisualBasic/SearchWindow.vb#gettextelement)]  
[!code-csharp[UIATextPattern_snip#FontName](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#fontname)]
[!code-vb[UIATextPattern_snip#FontName](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATextPattern_snip/VisualBasic/SearchWindow.vb#fontname)]  
  
 <xref:System.Windows.Automation.TextPattern> — Wzorzec kontrolki, w połączeniu z sekcją <xref:System.Windows.Automation.Text.TextPatternRange> klasy, obsługuje podstawowe atrybuty, właściwości i metody. Dla funkcji specyficznej dla kontroli, która nie jest obsługiwana przez <xref:System.Windows.Automation.TextPattern> lub <xref:System.Windows.Automation.Text.TextPatternRange> <xref:System.Windows.Automation.AutomationElement>, klasa dostarcza metody dla klientów automatyzacji interfejsu użytkownika dostępu odpowiedni model obiektów natywnych.  
  
## <a name="see-also"></a>Zobacz także
- [Przegląd automatyzacji interfejsu użytkownika — TextPattern](../../../docs/framework/ui-automation/ui-automation-textpattern-overview.md)
- [Dodawanie zawartości do pola tekstowego przy użyciu automatyzacji interfejsu użytkownika](../../../docs/framework/ui-automation/add-content-to-a-text-box-using-ui-automation.md)
- [Znajdowanie i wyróżnianie tekstu przy użyciu automatyzacji interfejsu użytkownika](../../../docs/framework/ui-automation/find-and-highlight-text-using-ui-automation.md)
- [Wzorce kontrolek automatyzacji interfejsu użytkownika — omówienie](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)
- [Wzorce kontrolek automatyzacji interfejsu użytkownika dla klientów](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
- [Uzyskiwanie szczegółów atrybutów tekstu mieszanego przy użyciu automatyzacji interfejsu użytkownika](../../../docs/framework/ui-automation/obtain-mixed-text-attribute-details-using-ui-automation.md)
