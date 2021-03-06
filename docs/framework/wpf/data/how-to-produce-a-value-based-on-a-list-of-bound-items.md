---
title: 'Instrukcje: Uzyskaj wartość w oparciu o listę powiązanych elementów'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], MultiBinding
- Multibinding [WPF]
ms.assetid: b3d06378-b511-4181-95aa-316d60c9229b
ms.openlocfilehash: 8f4e5b7767e475128b61080ca87e38ee311f4a3a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54706433"
---
# <a name="how-to-produce-a-value-based-on-a-list-of-bound-items"></a>Instrukcje: Uzyskaj wartość w oparciu o listę powiązanych elementów
<xref:System.Windows.Data.MultiBinding> Umożliwia powiązanie właściwość target powiązania do listy właściwości źródła, a następnie stosuje logikę w celu utworzenia wartości danego danych wejściowych. W tym przykładzie przedstawiono sposób użycia <xref:System.Windows.Data.MultiBinding>.  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie `NameListData` odwołuje się do kolekcji `PersonName` obiektów, które są obiektami, które zawierają dwie właściwości, `firstName` i `lastName`. Poniższy przykład tworzy <xref:System.Windows.Controls.TextBlock> imiona i nazwiska osoby o nazwisku przedstawiająca pierwszy.  
  
 [!code-xaml[MultiBinding#Resources1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources1)]  
[!code-xaml[MultiBinding#Resources2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources2)]  
[!code-xaml[MultiBinding#MultiBindingTextBox2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#multibindingtextbox2)]  
[!code-xaml[MultiBinding#Window](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#window)]  
  
 Aby dowiedzieć się, jak jest generowany format ostatnia nazwa pierwszego, Przyjrzyjmy się na implementacji `NameConverter`:  
  
 [!code-csharp[MultiBinding#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/NameConverter.cs#3)]
 [!code-vb[MultiBinding#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MultiBinding/VisualBasic/NameConverter.vb#3)]  
  
 `NameConverter` implementuje <xref:System.Windows.Data.IMultiValueConverter> interfejsu. `NameConverter` przyjmuje wartości od poszczególnych powiązania i przechowuje je w tablicy obiektu wartości. Kolejność, w której <xref:System.Windows.Data.Binding> elementy są wyświetlane w obszarze <xref:System.Windows.Data.MultiBinding> element polega na kolejności, w której te wartości są przechowywane w tablicy. Wartość <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> atrybut odwołuje się do niej argumentu parametru <xref:System.Windows.Data.MultiBinding.Converter%2A> metody, która wykonuje przełącznikiem parametru do określenia, jak format nazwy.  
  
## <a name="see-also"></a>Zobacz także
- [Konwertowanie powiązanych danych](../../../../docs/framework/wpf/data/how-to-convert-bound-data.md)
- [Powiązanie danych — omówienie](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [Tematy z instrukcjami](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
