---
title: 'Instrukcje: Tworzenie klawiszy dostępu dla formantów formularzy Windows przy użyciu narzędzia Projektant'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics [Windows Forms], adding to dialog box controls
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.assetid: 4c374c4c-4ca9-4a68-ac96-9dc3ab0f518a
ms.openlocfilehash: e9524449b457fc276678ecaadd1d137e7280156a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527474"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls-using-the-designer"></a>Instrukcje: Tworzenie klawiszy dostępu dla formantów formularzy Windows przy użyciu narzędzia Projektant
*Klucz dostępu* jest podkreślony znak w tekście menu, element menu lub etykieta kontrolki, takiej jak przycisk. Umożliwia użytkownikowi "przycisk", naciskając klawisz ALT w połączeniu z kluczem dostępu wstępnie zdefiniowane. Na przykład, jeśli przycisk uruchamia procedurę do Drukowanie formularza i dlatego jego `Text` właściwość jest ustawiona na "Print" Dodawanie handlowe "i" (&) przed litery "P" powoduje, że litery "P" podkreślić w tekst przycisku w czasie wykonywania. Użytkownik może uruchamiać polecenie skojarzone z przyciskiem, naciskając klawisze ALT + P. Nie może mieć klucza dostępu dla formantu, który nie może otrzymać ostrości.  
  
> [!NOTE]
>  Okna dialogowe i polecenia menu mogą się różnić od tych opisanych w Pomocy, w zależności od ustawień aktywnych lub wydania. Aby zmienić swoje ustawienia, wybierz opcję **Import i eksport ustawień** na **narzędzia** menu. Aby uzyskać więcej informacji, zobacz [personalizowanie środowiska IDE programu Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-create-an-access-key-for-a-control"></a>Aby utworzyć klucz dostępu dla formantu  
  
1.  W **właściwości** oknie `Text` właściwość ciąg, który zawiera handlowe "i" (&) przed literą, która będzie klucz dostępu. Na przykład, aby ustawić litery "P", jako klawisz dostępu, wpisz **& Drukuj** do siatki.  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Windows.Forms.Button>
- [Instrukcje: Odpowiadanie na kliknięcia przycisków formularzy Windows](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)
- [Instrukcje: Ustawianie tekstu wyświetlanego przez kontrolki formularzy Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [Etykietowanie pojedynczych kontrolek formularzy Windows Forms i określanie skrótów dla nich](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
