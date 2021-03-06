---
title: 'Instrukcje: Użyj przestrzeni nazw XML w powiązaniu danych'
ms.date: 03/30/2017
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
ms.openlocfilehash: bd2a156920057dc197fabbaa46e3a2d886a1b322
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54600352"
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a>Instrukcje: Użyj przestrzeni nazw XML w powiązaniu danych
## <a name="example"></a>Przykład  
 W tym przykładzie pokazano, jak obsługiwać przestrzenie nazw określony w swojej [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] źródło wiążące.  
  
 Jeśli Twoje [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] danych ma [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] definicję przestrzeni nazw:  
  
 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`  
  
 Możesz użyć <xref:System.Windows.Data.XmlNamespaceMapping> element do mapowania na przestrzeń nazw w celu <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, jak w poniższym przykładzie. Następnie można użyć <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> do odwoływania się do [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] przestrzeni nazw. <xref:System.Windows.Controls.ListBox> w tym przykładzie wyświetla *tytuł* i *dc:date* każdego *elementu*.  
  
 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]  
  
 Należy pamiętać, że <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> określasz, że nie ma odpowiadający komentarzowi użytemu w [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] źródła; Jeśli zmieni się prefiks [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] źródła wciąż działa mapowanie.  
  
 W tym konkretnym przykładzie [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] dane pochodzą z usługi sieci web, ale <xref:System.Windows.Data.XmlNamespaceMapping> element współpracuje również z wbudowanego [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] lub [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] osadzonego pliku danych.  
  
## <a name="see-also"></a>Zobacz także
- [Powiązywanie z danymi XML przy użyciu XMLDataProvider i zapytań XPath](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [Powiązanie danych — omówienie](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [Tematy z instrukcjami](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
