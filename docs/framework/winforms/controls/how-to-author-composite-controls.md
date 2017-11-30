---
title: "Porady: autoryzowanie formantów złożonych"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UserControl class [Windows Forms], creating composite controls
- user controls [Windows Forms], creating
- user controls [Windows Forms], inheriting from
- composite controls [Windows Forms], creating
ms.assetid: 79c9cf05-5ab6-4a18-886d-88a64748b098
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 72c68568f0178956d6154f0b3a070e69b6ff0502
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-author-composite-controls"></a>Porady: autoryzowanie formantów złożonych
Formanty złożone można zastosować na wiele sposobów. Można tworzyć je jako część projekt aplikacji komputerowych systemu Windows i ich używać tylko w formularzach w projekcie. Lub tworzyć je w projekcie Biblioteka formantów systemu Windows, skompiluj projekt do zestawu i użyj formantów w innych projektach. Można nawet dziedziczą z nich i umożliwia szybkie dostosować je do celów specjalnych dziedziczenie visual.  
  
> [!NOTE]
>  Jeśli chcesz tworzyć formantu złożonego do używania w formularzach sieci Web, zobacz [tworzenia kontrolek serwera ASP.NET niestandardowe](http://msdn.microsoft.com/library/fbe26c16-cff4-4089-b3dd-877411f0c0ef).  
>   
>  Okna dialogowe i polecenia menu mogą się różnić od tych opisanych w Pomocy, w zależności od ustawień aktywnych lub wydania. Aby zmienić ustawienia, wybierz **Import i eksport ustawień** na **narzędzia** menu. Aby uzyskać więcej informacji, zobacz [Dostosowywanie ustawień środowiska w programie Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-author-a-composite-control"></a>Do tworzenia złożonych kontrolek  
  
1.  Otwórz nowe **aplikacji systemu Windows** projektu o nazwie `DemoControlHost`.  
  
2.  Na **projektu**menu, kliknij przycisk **Dodaj kontrolkę użytkownika**.  
  
3.  W **Dodaj nowy element** okno dialogowe, plik klasy (plik .vb lub CS) nazwę, która ma formant złożone, aby podać.  
  
4.  Kliknij przycisk **Dodaj** przycisk, aby utworzyć plik klasy dla formantu złożonego.  
  
5.  Dodaj formanty z **przybornika** na powierzchnię złożonego formantu.  
  
6.  Umieść kod w procedurach zdarzeń do obsługi zdarzeń zgłaszanych przez formantu złożonego lub jego formantów składowych.  
  
7.  Zamknij projektanta dla formantu złożonego, a następnie zapisz plik po wyświetleniu monitu.  
  
8.  Na **kompilacji** menu, kliknij przycisk **Kompiluj rozwiązanie**.  
  
     Projektu muszą zostać skompilowane w kolejności, w przypadku kontrolek niestandardowych w wynikach **przybornika**.  
  
9. Użyj **DemoControlHost** karcie **przybornika** można dodać wystąpienia formantu do `Form1`.  
  
### <a name="to-author-a-control-class-library"></a>Do tworzenia biblioteki klas formantu  
  
1.  Otwórz nowe **Biblioteka formantów systemu Windows** projektu.  
  
     Domyślnie projekt zawiera złożonych kontrolek.  
  
2.  Dodaj formanty i kod, zgodnie z opisem w powyższej procedurze.  
  
3.  Wybierz formant nie ma dziedziczenie klas do zmiany, a następnie ustaw **Modyfikatory** właściwości do **prywatnej**.  
  
4.  Skompiluj bibliotekę DLL.  
  
### <a name="to-inherit-from-a-composite-control-in-a-control-class-library"></a>Dziedziczenie z formantu złożonego w bibliotece klas formantu  
  
1.  Na **pliku** menu wskaż **Dodaj** i wybierz **nowy projekt** Aby dodać nowy **aplikacji systemu Windows** projektu do rozwiązania.  
  
2.  W **Eksploratora rozwiązań**, kliknij prawym przyciskiem myszy **odwołania** folderu dla nowego projektu i wybierz polecenie **Dodaj odwołanie do** można otworzyć **Dodaj odwołanie**okno dialogowe.  
  
3.  Wybierz **projekty** karcie, a następnie kliknij dwukrotnie ikonę projektu biblioteki formantu.  
  
4.  Na **kompilacji** menu, kliknij przycisk **Kompiluj rozwiązanie**.  
  
5.  W **Eksploratora rozwiązań**, kliknij prawym przyciskiem myszy projektu biblioteki sterowania i wybierz **Dodaj nowy element** z menu skrótów.  
  
6.  Wybierz **dziedziczone kontrolki użytkownika** szablonu z **Dodaj nowy element** okno dialogowe.  
  
7.  W **selektora dziedziczenia** okno dialogowe, kliknij dwukrotnie formant ma być dziedziczona z.  
  
     Nowy formant został dodany do projektu.  
  
8.  Otwórz projektanta dla nowego formantu i Dodaj formanty dodatkowych składników.  
  
     Można sprawdzić formanty składników, które zostały odziedziczone złożonych kontrolek w bibliotece DLL i można zmieniać właściwości formantów których **Modyfikatory** właściwość jest **publicznego**. Nie można zmienić właściwości formantu których **Modyfikatory** właściwość jest **prywatnej**.  
  
## <a name="see-also"></a>Zobacz też  
 [Wskazówki: Tworzenie formantu złożonego za pomocą Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)  
 [Wskazówki: Tworzenie formantu złożonego za pomocą Visual C#](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)  
 [Wskazówki: Dziedziczenie z formantu formularzy systemu Windows za pomocą Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)  
 [Wskazówki: Dziedziczenie z formantu formularzy systemu Windows w języku Visual C#](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)  
 [Zalecenia dotyczące typu formantu](../../../../docs/framework/winforms/controls/control-type-recommendations.md)  
 [Porady: formanty autoryzacji dla formularzy systemu Windows](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)  
 [Różne typy formantów niestandardowych](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)