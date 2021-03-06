---
title: x:XData — Typ funkcji XAML
ms.date: 03/30/2017
f1_keywords:
- x:XData
- XData
- xXData
helpviewer_keywords:
- XAML [XAML Services], x:XData directive element
- XData in XAML [XAML Services]
- x:XData XAML directive element [XAML Services]
ms.assetid: 7ce209c2-621b-4977-b643-565f7e663534
ms.openlocfilehash: 8b951b33242fa7e17a02133adb8fed4ce638e51e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54498050"
---
# <a name="xxdata-intrinsic-xaml-type"></a>x:XData — Typ funkcji XAML
Umożliwia umieszczanie Wyspy danych XML w ramach produkcji XAML. Elementy XML wewnątrz `x:XData` nie powinny być traktowane przez procesory XAML, jak gdyby były częścią acting domyślna przestrzeń nazw XAML lub innych nazw XAML. `x:XData` może zawierać dowolną poprawnie sformułowany dokument XML.  
  
## <a name="xaml-object-element-usage"></a>Użycie elementu obiektu języka XAML  
  
```  
<x:XData>  
  <elementDataRoot>  
    [elementData]  
  </elementDataRoot>  
</x:XData>  
```  
  
## <a name="xaml-values"></a>Wartości XAML  
  
|||  
|-|-|  
|`elementDataRoot`|Element z jednym elementem głównym Wyspy danych zamknięte. Dla większości klientów ostatecznej XML, który nie ma jednym elementem głównym jest uznawane za nieprawidłowe. W szczególności jednym elementem głównym jest wymagany, jeśli `x:XData` ma służyć jako źródło danych XML do WPF lub wiele technologii, używające źródła XML dla powiązania danych.|  
|`[elementData]`|Opcjonalna. Plik XML, który reprezentuje dane XML. Dowolną liczbę elementów mogą być zawarte jako element danych i elementy zagnieżdżone mogą być zawarte w innych elementów; Jednakże zastosowania ogólne zasady XML.|  
  
## <a name="remarks"></a>Uwagi  
 Elementy XML w ramach `x:XData` obiektu ponownie zadeklarować wszystkie możliwe przestrzenie nazw i prefiksy zawierającego XMLDOM w ramach danych.  
  
 Programowy dostęp do danych XML i `x:XData` wewnętrzny typ XAML jest możliwe w .NET Framework XAML usług za pośrednictwem <xref:System.Windows.Markup.XData> klasy.  
  
## <a name="wpf-usage-notes"></a>Uwagi dotyczące użytkowania WPF  
 `x:XData` Obiekt jest używany głównie jako obiekt podrzędny panelu <xref:System.Windows.Data.XmlDataProvider>, albo, jako obiekt podrzędny obiektu <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> właściwości (w XAML, to jest zwykle wyrażona w składni elementu właściwości).  
  
 Dane zwykle powinny również ponownie definiować podstawowej przestrzeni nazw XML, w ramach Wyspy danych do nowego domyślnej przestrzeni nazw XML (ustawiony na pusty ciąg znaków). Jest to najprostszy Wyspy danych proste, ponieważ <xref:System.Windows.Data.Binding.XPath%2A> wyrażeń, które są używane do odwołania i powiąż z danymi można uniknąć włączenia prefiksów. Bardziej złożone Wyspy danych może zdefiniować wiele prefiksów dla danych i używaj określonego prefiksu dla przestrzeni nazw XML w folderze głównym. W takim przypadku wszystkie <xref:System.Windows.Data.Binding.XPath%2A> wyrażenie odwołuje się powinna zawierać odpowiedni prefiks mapowane w przestrzeni nazw. Aby uzyskać więcej informacji, zobacz [Przegląd wiązanie danych](../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 Z technicznego punktu widzenia `x:XData` może służyć jako zawartość żadnej właściwości typu <xref:System.Xml.Serialization.IXmlSerializable>. Jednak <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> tylko widocznym implementacji.  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Windows.Data.XmlDataProvider>
- [Powiązanie danych — omówienie](../../../docs/framework/wpf/data/data-binding-overview.md)
- [Rozszerzenie znaczników powiązania](../../../docs/framework/wpf/advanced/binding-markup-extension.md)
