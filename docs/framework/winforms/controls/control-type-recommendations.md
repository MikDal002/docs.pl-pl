---
title: Zalecenia dotyczące typu formantu
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- user controls [Windows Forms], when to use
- custom controls [Windows Forms], types
- controls [Windows Forms], creating
ms.assetid: 5235fe9d-c36a-4c08-ae76-6cb90b50085e
ms.openlocfilehash: 5e3337dddcc39517558cf85af76223306d20d2bb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54599702"
---
# <a name="control-type-recommendations"></a>Zalecenia dotyczące typu formantu
Zapewnia .NET Framework power opracowanie i wdrożenie nowych kontrolek. Oprócz kontrolki użytkownika znanych teraz znajdziesz się możliwość zapisywania niestandardowych formantów, które narysowania własne, a nawet mogą rozszerzać funkcjonalność istniejących kontrolek poprzez dziedziczenie. Przy wyborze rozwiązania, jakiego typu formantu, aby utworzyć może być mylące. W tej sekcji przedstawiono różnice między różnymi typami kontrolek, z którego może dziedziczyć i zapewnia uwagi dotyczące wpisz, aby wybrać projekt.  
  
> [!NOTE]
>  Jeśli chcesz utworzyć formant do użycia w formularzach sieci Web, zobacz artykuł [tworzenia formanty serwera ASP.NET niestandardowe](https://msdn.microsoft.com/library/fbe26c16-cff4-4089-b3dd-877411f0c0ef).  
  
## <a name="inheriting-from-a-windows-forms-control"></a>Dziedziczenie z Windows formantu formularzy  
 Odziedziczoną kontrolkę może pochodzić z dowolnego istniejącego formantu Windows Forms. To podejście pozwala zachować wszystkie funkcje nieprzerwaną pracę formantu Windows Forms i następnie rozszerzyć tę funkcję, dodając niestandardowe właściwości, metody i innych funkcji. Na przykład utworzyć formant pochodzące z <xref:System.Windows.Forms.TextBox> który może akceptować tylko liczby i automatycznie konwertuje dane wejściowe na wartość. Taki formant może zawierać kod sprawdzania poprawności, który został wywołany po każdym zmieniony tekst w polu tekstowym i może mieć dodatkowe właściwości wartości. W niektórych kontrolek, można również dodać niestandardowy wygląd interfejsu graficznego kontrolki poprzez zastąpienie <xref:System.Windows.Forms.Control.OnPaint%2A> metody klasy bazowej.  
  
 Dziedziczenie z kontrolki formularzy Windows Forms, jeśli:  
  
-   Większość funkcji, których potrzebujesz już jest identyczna z istniejącej kontrolki Windows Forms.  
  
-   Nie ma potrzeby niestandardowego interfejsu graficznego lub projektowania nowych graficznych fronton dla istniejącej kontrolki.  
  
## <a name="inheriting-from-the-usercontrol-class"></a>Dziedziczenie z klasy UserControl  
 Formant użytkownika to zbiór kontrolek formularzy Windows Forms umieszczane na wspólnym kontenerem. Zawiera wszystkie funkcje nieprzerwaną pracę związany z każdą z kontrolek Windows Forms i umożliwia selektywne udostępnianie i wiązania ich właściwości kontenera. Przykładem kontrolki użytkownika może być kontrolki utworzona w celu wyświetlenia danych adres klienta z bazy danych. Ten formant obejmuje kilka pól tekstowych do wyświetlenia każdego pola i formanty przycisków, aby poruszać się po rekordów. Selektywnie widoczne właściwości powiązania danych, a cały kontroli może spakowane i ponownie z aplikacji do aplikacji.  
  
 Dziedzicz <xref:System.Windows.Forms.UserControl> klasy, jeśli:  
  
-   Chcesz połączyć funkcje kilka kontrolek Windows Forms w pojedynczą jednostkę wielokrotnego użytku.  
  
## <a name="inheriting-from-the-control-class"></a>Dziedziczenie z klasy formantów  
 Innym sposobem, aby utworzyć formant jest utworzenie jednego znacznie od podstaw przez dziedziczenie z <xref:System.Windows.Forms.Control>. <xref:System.Windows.Forms.Control> Klasy zawiera wszystkie podstawowe funkcje wymagane przez formanty (na przykład zdarzenia), ale funkcje specyficzne dla formantu lub interfejsu graficznego. Tworzenie formantu przez dziedziczenie z <xref:System.Windows.Forms.Control> klasy wymaga o wiele więcej myślenia i nakładu pracy niż dziedziczenie z kontrolki użytkownika lub istniejącej kontrolki Windows Forms. Autor trzeba napisać kod dla <xref:System.Windows.Forms.Control.OnPaint%2A> zdarzenia kontroli, jak również wszelki kod określonych funkcji, który jest potrzebny. Większa elastyczność jest dozwolone, jednak i możesz dostosować niestandardowego formantu do własnych potrzeb dokładnie. Przykład formantu niestandardowego jest formantem zegara powielającą wygląd i działanie zegar analogowy. Malowanie niestandardowe będą wywoływane w celu spowodować ręce zegar przenoszone w odpowiedzi na <xref:System.Windows.Forms.Timer.Tick> zdarzenia ze składnika wewnętrznego zegara.  
  
 Dziedzicz <xref:System.Windows.Forms.Control> klasy, jeśli:  
  
-   Chcesz zapewnić niestandardowy graficzną reprezentację kontrolki.  
  
-   Musisz zaimplementować niestandardowy funkcji, która nie jest dostępna za pośrednictwem standardowych kontrolek.  
  
-   [Instrukcje: Wyświetlanie kontroli w wybierz elementy przybornika — okno dialogowe](https://msdn.microsoft.com/library/9yxtkx75\(v=vs.110\))  
  
-   [Przewodnik: Serializowanie kolekcji standardowych typów za pomocą DesignerSerializationVisibilityAttribute](serializing-collections-designerserializationvisibilityattribute.md)  
  
-   [Przewodnik: Dziedziczenie z kontrolki formularzy Windows Forms za pomocą Visual C#](https://msdn.microsoft.com/library/5h0k2e6x\(v=vs.110\))  
  
-   [Instrukcje: Dostarczanie mapy bitowej przybornika dla formantu](https://msdn.microsoft.com/library/4wk1wc0a\(v=vs.110\))  
  
-   [Instrukcje: Dziedzicz Windows istniejących formantów formularzy](https://msdn.microsoft.com/library/7h62478z\(v=vs.110\))  
  
-   [Przewodnik: Debugowanie Windows niestandardowych formantów formularzy w czasie projektowania](https://msdn.microsoft.com/library/5ytx0z24\(v=vs.110\))  
  
-   [Instrukcje: Dziedziczenie z klasy formantów](https://msdn.microsoft.com/library/skcysbt2\(v=vs.110\))  
  
-   [Instrukcje: Testowanie zachowania UserControl w czasie wykonywania](how-to-test-the-run-time-behavior-of-a-usercontrol.md)  
  
-   [Instrukcje: Wyrównywanie formantu z krawędziami formularzy w czasie projektowania](https://msdn.microsoft.com/library/1fxyb15b\(v=vs.110\))  
  
-   [Instrukcje: Dziedziczenie z klasy UserControl](https://msdn.microsoft.com/library/00ctb4z0\(v=vs.110\))  
  
-   [Instrukcje: Tworzenie kontrolek dla formularzy Windows Forms](https://msdn.microsoft.com/library/bs3yhkh7\(v=vs.110\))  
  
-   [Instrukcje: Formanty złożone autora](https://msdn.microsoft.com/library/3sf86w5h\(v=vs.110\))  
  
-   [Przewodnik: Tworzenie formantu złożonego za pomocą Visual Basic](https://msdn.microsoft.com/library/c316f119\(v=vs.110\))  
  
-   [Przewodnik: Tworzenie formantu złożonego za pomocą Visual C#](https://msdn.microsoft.com/library/a6h7e207\(v=vs.110\))  
  
-   [Przewodnik: Dziedziczenie z kontrolki formularzy Windows Forms za pomocą Visual Basic](https://msdn.microsoft.com/library/w2a8y03d\(v=vs.110\))  
  
-   [Instrukcje: Tworzenie formantu formularzy Windows wykorzystującego funkcje czasu projektowania](https://msdn.microsoft.com/library/307hck25\(v=vs.110\))  
  
-   [Instrukcje: Tworzenie formantu formularzy Windows wykorzystującego funkcje czasu projektowania](https://msdn.microsoft.com/library/307hck25\(v=vs.120\))  
  
## <a name="see-also"></a>Zobacz także
- [Instrukcje: Tworzenie kontrolki formularzy Windows prosty](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md)
- [Różne typy kontrolek niestandardowych](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
