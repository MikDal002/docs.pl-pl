---
title: 'Instrukcje: Deklarowanie i wywoływanie w właściwości domyślnej w języku Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- defaults [Visual Basic], properties
- properties [Visual Basic], default
- procedures [Visual Basic], defining
- default properties [Visual Basic], in Visual Basic
- Visual Basic code, procedures
- Visual Basic code, properties
- default properties
ms.assetid: 68b4026e-09ef-4613-808e-f6287494ff63
ms.openlocfilehash: ca282acbe6831f2189d83faa2f83d32d420d9b53
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54640969"
---
# <a name="how-to-declare-and-call-a-default-property-in-visual-basic"></a>Instrukcje: Deklarowanie i wywoływanie w właściwości domyślnej w języku Visual Basic
A *właściwość domyślna* jest właściwością klasy lub struktury, których Twój kod może uzyskać dostęp bez określania go. Podczas wywoływania kodu nazwy klasy lub struktury, ale nie właściwości i kontekst zezwala na dostęp do właściwości, Visual Basic jest rozpoznawana jako dostęp do tej klasy lub struktury domyślnej właściwości jeśli taka istnieje.  
  
 Klasa lub struktura może mieć co najwyżej jeden domyślny właściwości. Jednak można przeciążać właściwości domyślne i mieć więcej niż jedną wersję.  
  
 Aby uzyskać więcej informacji, zobacz temat [Default](../../../../visual-basic/language-reference/modifiers/default.md).  
  
### <a name="to-declare-a-default-property"></a>Aby zadeklarować właściwość domyślną  
  
1.  Zadeklaruj właściwość w normalny sposób. Nie określaj `Shared` lub `Private` — słowo kluczowe.  
  
2.  Obejmują `Default` — słowo kluczowe w deklaracji właściwości.  
  
3.  Określ co najmniej jeden parametr dla właściwości. Nie można zdefiniować domyślnej właściwości, które nie wymaga co najmniej jednego argumentu.  
  
     [!code-vb[VbVbcnProcedures#17](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_1.vb)]  
  
### <a name="to-call-a-default-property"></a>Aby wywoływanie w właściwości domyślnej  
  
1.  Zadeklaruj zmienną typu zawierającego klasy lub struktury.  
  
     [!code-vb[VbVbcnProcedures#16](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_2.vb)]  
  
2.  Użyj nazwy zmiennej wyłącznie w wyrażeniu, w których zwykle zawierałoby nazwę właściwości.  
  
     [!code-vb[VbVbcnProcedures#21](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_3.vb)]  
  
3.  Postępuj zgodnie z nazwą zmiennej listy argumentów w nawiasach. Domyślna właściwość musi mieć co najmniej jednego argumentu.  
  
     [!code-vb[VbVbcnProcedures#20](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_4.vb)]  
  
4.  Aby pobrać wartość właściwości domyślne, za pomocą nazwę zmiennej listy argumentów, w wyrażeniu lub równości (`=`) Zaloguj się w instrukcji przypisania.  
  
     [!code-vb[VbVbcnProcedures#15](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_5.vb)]  
  
5.  Aby ustawić właściwości wartość domyślna, nazwa zmiennej za pomocą listy argumentów, po lewej stronie instrukcji przypisania.  
  
     [!code-vb[VbVbcnProcedures#14](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_6.vb)]  
  
6.  Zawsze można określić nazwę właściwości domyślnej wraz z nazwą zmiennej, tak jak dostęp do wszystkich innych właściwości.  
  
     [!code-vb[VbVbcnProcedures#19](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_7.vb)]  
  
## <a name="example"></a>Przykład  
 Poniższy przykład deklaruje właściwości domyślnej klasy.  
  
 [!code-vb[VbVbcnProcedures#12](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_8.vb)]  
  
## <a name="example"></a>Przykład  
 Poniższy przykład pokazuje, jak wywoływanie w właściwości domyślnej `myProperty` klasy `class1`. Instrukcje przypisania trzy przechowywać wartości w `myProperty`i <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> wywołanie odczytuje wartości.  
  
 [!code-vb[VbVbcnProcedures#13](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_9.vb)]  
  
 Najczęściej właściwości domyślnej jest <xref:Microsoft.VisualBasic.Collection.Item%2A> właściwość różnych klas kolekcji.  
  
## <a name="robust-programming"></a>Niezawodne programowanie  
 Właściwości domyślnych może spowodować zmniejszenie małe znaki kodu źródłowego, ale mogą robić więjsze kodu czytelność. Jeśli kod wywołujący nie są zaznajomieni z klasy lub struktury, jeśli go nawiązuje odwołanie do nazwy klasy lub struktury nie może być określone czy tego odwołania uzyskuje dostęp do, klasa lub struktura lub domyślnej właściwości. Może to prowadzić do błędów kompilatora lub błędy subtelne logiki czasu wykonywania.  
  
 Trochę zmniejsza ryzyko wystąpienia błędów właściwości domyślne przy użyciu zawsze [Option Strict — instrukcja](../../../../visual-basic/language-reference/statements/option-strict-statement.md) ustawienie typu kompilatora sprawdzanie `On`.  
  
 Jeśli planujesz użyć wstępnie zdefiniowanych klasy lub struktury w kodzie, należy określić, czy ma ona właściwości domyślnej, a jeśli tak, jakie jego nazwa jest.  
  
 Z powodu niedogodności należy rozważyć nie definiuje właściwości domyślnych. Aby zwiększyć czytelność kodu należy również wziąć pod uwagę zawsze odwołujące się do wszystkich właściwości jawnie, nawet domyślne właściwości.  
  
## <a name="see-also"></a>Zobacz także
- [Procedury właściwości](./property-procedures.md)
- [Parametry i argumenty procedur](./procedure-parameters-and-arguments.md)
- [Instrukcja Property](../../../../visual-basic/language-reference/statements/property-statement.md)
- [Default](../../../../visual-basic/language-reference/modifiers/default.md)
- [Różnice między właściwościami i zmiennymi w Visual Basic](./differences-between-properties-and-variables.md)
- [Instrukcje: Tworzenie właściwości](./how-to-create-a-property.md)
- [Instrukcje: Deklarowanie właściwości z mieszanymi poziomami dostępu](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Instrukcje: Wywoływanie procedury właściwości](./how-to-call-a-property-procedure.md)
- [Instrukcje: Umieszczanie wartości we właściwości](./how-to-put-a-value-in-a-property.md)
- [Instrukcje: Pobieranie wartości z właściwości](./how-to-get-a-value-from-a-property.md)
