---
title: Przechowywanie atramentu
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ISF (Ink Serialized Format)
- storing ink [WPF]
- ink [WPF], storing
- retrieving ink [WPF]
- Ink Serialized Format (ISF)
ms.assetid: a3f6d16b-d682-4680-9965-907332b4d2b8
ms.openlocfilehash: c115e31b73afc1532973be3db8e3e184e9a4253b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54492891"
---
# <a name="storing-ink"></a>Przechowywanie atramentu
<xref:System.Windows.Ink.StrokeCollection.Save%2A> Metody umożliwiają przechowywanie pisma odręcznego jako pisma odręcznego serializacji formatu (ISF). Konstruktory <xref:System.Windows.Ink.StrokeCollection> klasy umożliwiają odczytywanie danych pisma odręcznego.  
  
## <a name="ink-storage-and-retrieval"></a>Przechowywanie pisma odręcznego i pobieranie  
 W tej sekcji omówiono sposób przechowywania i pobierania pisma odręcznego w [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] platformy.  
  
 Poniższy przykład wykonuje program obsługi zdarzeń kliknięcia przycisku, który przedstawia użytkownika z oknem dialogowym zapisywania pliku i zapisuje pisma odręcznego z <xref:System.Windows.Controls.InkCanvas> poza do pliku.  
  
 [!code-csharp[DigitalInkTopics#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#12)]
 [!code-vb[DigitalInkTopics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#12)]  
  
 Poniższy przykład wykonuje program obsługi zdarzeń kliknięcia przycisku, który wyświetli użytkownika z pliku otwarte okno dialogowe i odczytuje pisma odręcznego z pliku do <xref:System.Windows.Controls.InkCanvas> elementu.  
  
 [!code-csharp[DigitalInkTopics#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#13)]
 [!code-vb[DigitalInkTopics#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#13)]  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Windows.Controls.InkCanvas>
- [Windows Presentation Foundation](../../../../docs/framework/wpf/index.md)
