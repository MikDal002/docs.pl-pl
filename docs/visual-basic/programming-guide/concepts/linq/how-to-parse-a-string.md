---
title: 'Instrukcje: Przeanalizować składni ciągu (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 896e1b4b-f9bd-4975-8bc1-55b6badce1ac
ms.openlocfilehash: 513a82cbed796be42eb8e531ec71221ef0ac267f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54652452"
---
# <a name="how-to-parse-a-string-visual-basic"></a>Instrukcje: Przeanalizować składni ciągu (Visual Basic)
W tym temacie przedstawiono sposób tworzenia drzewa XML w C#.  
  
## <a name="example"></a>Przykład  
 Ciąg w języku Visual Basic można analizować za pomocą `XElement.Parse` metody. Jednak jest bardziej wydajne, aby użyć literałów XML, jak pokazano w poniższym kodzie, ponieważ literały XML nie borykają się z tym samym spadku wydajności jako analizowanie kodu XML z ciągu.  
  
 Przy użyciu literałów XML, można po prostu skopiować i wkleić kod XML do programu Visual Basic.  
  
> [!NOTE]
>  Analizowanie tekstu lub podczas ładowania dokumentu XML z pliku tekstowego jest mniej wydajne niż konstrukcja funkcjonalna. Jeśli są inicjowanie drzewa XML z kodu, zajmuje mniej czasu procesora, aby użyć konstrukcja funkcjonalna, niż można przeanalizować tekstu.  
  
```vb  
Dim contacts as XElement = _  
    <Contacts>  
        <Contact>  
            <Name>Patrick Hines</Name>  
            <Phone Type="home">206-555-0144</Phone>  
            <Phone Type="work">425-555-0145</Phone>  
            <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
            </Address>  
            <NetWorth>10</NetWorth>  
        </Contact>  
        <Contact>  
            <Name>Gretchen Rivas</Name>  
            <Phone Type="mobile">206-555-0163</Phone>  
            <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
            </Address>  
            <NetWorth>11</NetWorth>  
        </Contact>  
    </Contacts>  
```  
  
## <a name="see-also"></a>Zobacz także
- [Analizowanie kodu XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
