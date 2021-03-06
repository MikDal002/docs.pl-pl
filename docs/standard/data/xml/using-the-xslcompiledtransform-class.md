---
title: Używanie klasy XslCompiledTransform
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: f9b074f6-d6f4-49dd-a093-df510bf0cf7b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ce9a06c14141bb658eb665e643d8da27e18dd94f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54590380"
---
# <a name="using-the-xslcompiledtransform-class"></a>Używanie klasy XslCompiledTransform
<xref:System.Xml.Xsl.XslCompiledTransform> Klasa jest procesora XSLT programu Microsoft .NET Framework. Ta klasa jest używana do kompilowania arkusze stylów i wykonania przekształcenia XSLT.  
  
> [!NOTE]
>  Mimo że ogólną wydajność <xref:System.Xml.Xsl.XslCompiledTransform> klasy jest lepsze niż <xref:System.Xml.Xsl.XslTransform> klasy <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> metody <xref:System.Xml.Xsl.XslCompiledTransform> klasy może działać więcej wolniej niż <xref:System.Xml.Xsl.XslTransform.Load%2A> metody <xref:System.Xml.Xsl.XslTransform> klasy pierwszego czasu jest wywoływana w transformacji. Jest to spowodowane plik XSLT, ale muszą być skompilowane, zanim został załadowany. Aby uzyskać więcej informacji zobacz następujący wpis w blogu: [XslCompiledTransform wolniej niż XslTransform?](https://blogs.msdn.microsoft.com/antosha/2006/07/16/xslcompiledtransform-slower-than-xsltransform/)  
  
## <a name="in-this-section"></a>W tej sekcji  
 [Dane wejściowe klasy XslCompiledTransform](../../../../docs/standard/data/xml/inputs-to-the-xslcompiledtransform-class.md)  
 W tym artykule opisano dostępne opcje danych wejściowych XSLT.  
  
 [Opcje danych wyjściowych klasy XslCompiledTransform](../../../../docs/standard/data/xml/output-options-on-the-xslcompiledtransform-class.md)  
 W tym artykule opisano dostępne opcje wyjściowe XSLT.  
  
 [Rozpoznawanie zewnętrznych zasobów podczas przetwarzania XSLT](../../../../docs/standard/data/xml/resolving-external-resources-during-xslt-processing.md)  
 Omawia przy użyciu <xref:System.Xml.XmlResolver> klasy, aby rozwiązać zasobów zewnętrznych.  
  
 [Rozszerzanie arkuszy stylów XSLT](../../../../docs/standard/data/xml/extending-xslt-style-sheets.md)  
 W tym artykule omówiono, jak XSLT rozszerzenia są obsługiwane.  
  
|||  
|-|-|  
|[Odwracalne błędy XSLT](../../../../docs/standard/data/xml/recoverable-xslt-errors.md)|Wyświetla listę zachowań uznaniowych dozwolone przez XSLT World Wide Web Consortium (W3C) 1.0 zalecenia i w tym artykule opisano, jak te zachowania są obsługiwane przez <xref:System.Xml.Xsl.XslCompiledTransform> klasy.|  
|[Instrukcje: Przekształcanie fragmentu węzła](../../../../docs/standard/data/xml/how-to-transform-a-node-fragment.md)|Opisuje sposób Przekształcanie fragmentu węzła.|  
  
## <a name="related-sections"></a>Sekcje pokrewne  
 [Migrowanie z klasy XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)  
 W tym artykule omówiono sposób migracji kodu z <xref:System.Xml.Xsl.XslTransform> klasy  
  
## <a name="see-also"></a>Zobacz także

- <xref:System.Xml.Xsl.XsltSettings>
- <xref:System.Xml.Xsl.XsltMessageEncounteredEventArgs>
