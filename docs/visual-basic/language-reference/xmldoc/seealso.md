---
title: <seealso> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <seealso> XML tag
- seealso XML tag
ms.assetid: 36050c95-1af2-4284-b9b6-1a70691ed978
ms.openlocfilehash: ca0b298c0c95e018febbcfac95de7db05bffedb8
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2019
ms.locfileid: "55287888"
---
# <a name="seealso-visual-basic"></a>\<seealso> (Visual Basic)
Określa łącze, które pojawia się w sekcji Zobacz też.  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<seealso cref="member"/>  
```  
  
#### <a name="parameters"></a>Parametry  
 `member`  
 Odwołanie do elementu członkowskiego lub pola, które są dostępne do wywoływania z bieżącym środowisku kompilacji. Kompilator sprawdza, czy dany element kodu istnieje i przekazuje `member` do nazwy elementu w danych wyjściowych XML. `member` musi znajdować się w znaki podwójnego cudzysłowu ("").  
  
## <a name="remarks"></a>Uwagi  
 Użyj `<seealso>` tag, aby określić tekst, który ma być wyświetlany w sekcji Zobacz też. Użyj [ \<zobacz >](../../../visual-basic/language-reference/xmldoc/see.md) określić łącze między w tekście.  
  
 Kompiluj przy użyciu [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) do Przetwarzaj komentarze dokumentacji do pliku.  
  
## <a name="example"></a>Przykład  
 W tym przykładzie użyto `<seealso>` tagów w `DoesRecordExist` uwagi sekcji do odwoływania się do `UpdateRecord` metody.  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/seealso_1.vb)]  
  
## <a name="see-also"></a>Zobacz także
- [Tagi komentarza XML](../../../visual-basic/language-reference/xmldoc/index.md)
