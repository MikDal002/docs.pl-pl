---
title: 'Instrukcje: Tworzenie dokumentacji XML w Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments
- XML documentation [Visual Basic], creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
ms.openlocfilehash: d67724aad6cd3e7af30531328d85e89937390dd1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54551374"
---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a>Instrukcje: Tworzenie dokumentacji XML w Visual Basic
W tym przykładzie przedstawiono sposób dodawania komentarzy dokumentacji XML w kodzie.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-xml-documentation-for-a-type-or-member"></a>Aby utworzyć dokumentacji XML dla typu lub składowej  
  
1.  W **Edytor kodu**, umieść kursor w wierszu powyżej typu lub elementu członkowskiego, dla której chcesz utworzyć dokumentacji.  
  
2.  Typ `'''` (trzy znaki pojedynczego cudzysłowu).  
  
     Szkielet XML dla typu lub elementu członkowskiego zostanie dodany do **Edytor kodu**.  
  
3.  Dodaj informacje opisowe między odpowiednie tagi.  
  
    > [!NOTE]
    >  Jeśli dodasz dodatkowe wiersze w bloku dokumentacji XML, musi zaczynać się każdy wiersz `'''`.  
  
4.  Dodaj dodatkowy kod, który używa typu lub elementu członkowskiego przy użyciu nowych komentarzy dokumentacji XML.  
  
     Funkcja IntelliSense wyświetla tekst z \<podsumowania > tag w przypadku typu lub elementu członkowskiego.  
  
5.  Skompiluj kod, aby wygenerować plik XML zawierający komentarze dokumentacji. Aby uzyskać więcej informacji, zobacz [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## <a name="see-also"></a>Zobacz także
- [Dokumentowanie kodu za pomocą XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
- [Tagi komentarza XML](../../../visual-basic/language-reference/xmldoc/index.md)
- [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)
