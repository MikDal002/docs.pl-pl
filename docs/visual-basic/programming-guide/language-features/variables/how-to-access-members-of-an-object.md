---
title: 'Instrukcje: Dostęp do elementów członkowskich obiektu (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- members [Visual Basic], accessing
- object variables [Visual Basic], accessing members
ms.assetid: a0072514-6a79-4dd6-8d03-ca8c13e61ddc
ms.openlocfilehash: 5e91f1b99a17f4bbdc65a77ab26050ee57e96ac4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54724846"
---
# <a name="how-to-access-members-of-an-object-visual-basic"></a>Instrukcje: Dostęp do elementów członkowskich obiektu (Visual Basic)
Jeśli masz zmienną obiektu, który odwołuje się do obiektu, często chcą pracować z członkami tego obiektu, takie jak metody, właściwości, pola i zdarzenia. Na przykład po utworzeniu nowego <xref:System.Windows.Forms.Form> obiektu, warto ustawić jej <xref:System.Windows.Forms.Control.Text%2A> właściwość lub wywołanie jego <xref:System.Windows.Forms.Control.Focus%2A> metody.  
  
## <a name="accessing-members"></a>Uzyskiwanie dostępu do elementów członkowskich  
 Uzyskujesz dostęp do członków obiektu za pomocą zmiennej, która odwołuje się do niego.  
  
#### <a name="to-access-members-of-an-object"></a>Aby dostęp do elementów członkowskich obiektu  
  
-   Użyj operatora dostępu do elementu członkowskiego (`.`) między nazwą zmiennej obiektu i nazwę elementu członkowskiego.  
  
    ```  
    currentText = newForm.Text  
    ```  
  
     Jeśli element jest [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), nie trzeba zmiennej, aby uzyskać do niego dostęp.  
  
## <a name="accessing-members-of-an-object-of-known-type"></a>Uzyskiwanie dostępu do elementów członkowskich obiektu znany typ  
 Jeśli znasz typ obiektu w czasie kompilacji, możesz użyć *wczesne powiązania* zmiennej, która odwołuje się do niego.  
  
#### <a name="to-access-members-of-an-object-for-which-you-know-the-type-at-compile-time"></a>Aby dostęp do elementów członkowskich obiektu, dla którego typ znany w czasie kompilacji  
  
1.  Zadeklaruj zmienną obiektu typu obiektu, który chcesz przypisać do zmiennej.  
  
    ```  
    Dim extraForm As System.Windows.Forms.Form  
    ```  
  
     Za pomocą `Option Strict On`, można przypisać tylko <xref:System.Windows.Forms.Form> obiektów (lub obiektów typu pochodnego od <xref:System.Windows.Forms.Form>) do `extraForm`. Jeśli zdefiniowano klasy lub struktury za pomocą rozszerzenia `CType` konwersji <xref:System.Windows.Forms.Form>, można także przypisać tej klasy lub struktury do `extraForm`.  
  
2.  Użyj operatora dostępu do elementu członkowskiego (`.`) między nazwą zmiennej obiektu i nazwę elementu członkowskiego.  
  
    ```  
    extraForm.Show()  
    ```  
  
     Dostęp do wszystkich metod i właściwości specyficzne dla <xref:System.Windows.Forms.Form> klasy, niezależnie od tego, co `Option Strict` to ustawienie.  
  
## <a name="accessing-members-of-an-object-of-unknown-type"></a>Uzyskiwanie dostępu do elementów członkowskich obiektu nieznanego typu  
 Jeśli typ obiektu nie jest znany w czasie kompilacji, należy użyć *późnym wiązaniu* dla dowolnej zmiennej, która odwołuje się do niego.  
  
#### <a name="to-access-members-of-an-object-for-which-you-do-not-know-the-type-at-compile-time"></a>Aby dostęp do elementów członkowskich obiektu, dla którego nie znasz typu w czasie kompilacji  
  
1.  Deklarowanie zmiennej obiektu będzie [Object — typ danych](../../../../visual-basic/language-reference/data-types/object-data-type.md). (Zadeklarowanie zmiennej jako `Object` jest taka sama jak deklarowania go jako <xref:System.Object?displayProperty=nameWithType>.)  
  
    ```  
    Dim someControl As Object  
    ```  
  
     Za pomocą `Option Strict On`, możesz uzyskać dostęp tylko do elementów członkowskich, które są zdefiniowane na <xref:System.Object> klasy.  
  
2.  Użyj operatora dostępu do elementu członkowskiego (`.`) między nazwą zmiennej obiektu i nazwę elementu członkowskiego.  
  
    ```  
    someControl.GetType()  
    ```  
  
     Aby umożliwić dostęp do elementów członkowskich obiektu można przypisać do zmiennej obiektu, należy ustawić `Option Strict Off`. Gdy to zrobisz, kompilator nie może zagwarantować, że dany element jest uwidaczniany przez obiekt, który można przypisać do zmiennej. Jeśli obiekt nie ujawnia członka, nastąpi próba uzyskania dostępu, <xref:System.MemberAccessException> wystąpi wyjątek.  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Object>
- <xref:System.Windows.Forms.Form>
- <xref:System.MemberAccessException>
- [Zmienne obiektów](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Deklaracja zmiennej obiektu](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [Object, typ danych](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Option Strict, instrukcja](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
