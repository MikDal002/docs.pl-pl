---
title: mc:ProcessContent — Atrybut
ms.date: 03/30/2017
helpviewer_keywords:
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
ms.openlocfilehash: f7db71c065a04fb14216ffd08ca3b7c9d7cdf5af
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54673962"
---
# <a name="mcprocesscontent-attribute"></a>mc:ProcessContent — Atrybut
Określa, która [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elementy nadal powinien mieć zawartość, przetwarzane przez nadrzędne odpowiednich elementów, nawet, jeśli element bezpośredni obiekt nadrzędny może być ignorowane przez [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesora ze względu na określanie [mc: Ignorable — atrybut](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) . `mc:ProcessContent` Atrybut obsługuje zgodność znaczników, zarówno dla mapowania niestandardowej przestrzeni nazw i [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] przechowywania wersji.  
  
## <a name="xaml-attribute-usage"></a>Użycie atrybutu języka XAML  
  
```  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...  
  mc:ProcessContent="ignorablePrefix:ThisElementCanBeIgnored"  
>  
    <ignorablePrefix:ThisElementCanBeIgnored>  
        [content]  
    </ignorablePrefix:ThisElementCanBeIgnored>  
</object>  
```  
  
## <a name="xaml-values"></a>Wartości XAML  
  
|||  
|-|-|  
|*ignorablePrefix*|Dowolny ciąg prawidłowy prefiks, na Specyfikacja XML 1.0.|  
|*ignorableUri*|Wszelkie prawidłowy identyfikator URI do wyznaczania obszaru nazw, na Specyfikacja XML 1.0.|  
|*ThisElementCanBeIgnored*|Element, który może być ignorowane przez [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] implementacji procesora, jeśli nie można rozpoznać typu bazowego.|  
|*[zawartość]*|*ThisElementCanBeIgnored* jest oznaczone do pominięcia. Jeśli procesor ignoruje ten element *[zawartość]* jest przetwarzany przez *obiektu*.|  
  
## <a name="remarks"></a>Uwagi  
 Domyślnie [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesora zignoruje zawartości w obrębie elementu zignorowane. Można określić elementu określonego przez `mc:ProcessContent`, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesora będzie w dalszym ciągu przetwarzać zawartość w elemencie zignorowane. To wykorzystania Jeśli zawartość jest zagnieżdżony w kilka tagów, co najmniej jeden z nich można zignorować, i nie jest co najmniej jeden z nich można zignorować.  
  
 Wiele prefiksów może być określone w atrybucie, używając separatora miejsca, na przykład: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.  
  
 [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] Nazw definiuje innych elementów i atrybutów, które nie zostały zamieszczone w tym obszarze [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)]. Aby uzyskać więcej informacji, zobacz [specyfikacji zgodności znaczników XML](https://go.microsoft.com/fwlink/?LinkId=73824).  
  
## <a name="see-also"></a>Zobacz także
- [mc:Ignorable, atrybut](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)
- [Przegląd XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
