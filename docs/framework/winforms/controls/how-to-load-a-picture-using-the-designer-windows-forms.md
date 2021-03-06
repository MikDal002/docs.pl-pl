---
title: 'Instrukcje: Zdjęcia przy użyciu narzędzia Projektant (formularze Windows)'
ms.date: 03/30/2017
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
ms.openlocfilehash: 6142474c2009e0998852dc28d346e73f4abbf1b0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54539093"
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a>Instrukcje: Zdjęcia przy użyciu narzędzia Projektant (formularze Windows)
Za pomocą interfejsu Windows Forms <xref:System.Windows.Forms.PictureBox> kontrolki, można załadować i wyświetlania obrazu w postaci, w czasie projektowania, ustawiając <xref:System.Windows.Forms.PictureBox.Image%2A> właściwość prawidłowy obraz. W poniższej tabeli przedstawiono typy plików dopuszczalne.  
  
|Typ|Rozszerzenie nazwy pliku|  
|----------|-------------------------|  
|Mapy bitowej|.bmp|  
|Ikona|.ico|  
|GIF|.gif|  
|Metafile|.wmf|  
|JPEG|.jpg|  
  
> [!NOTE]
>  Okna dialogowe i polecenia menu mogą się różnić od tych opisanych w Pomocy, w zależności od ustawień aktywnych lub wydania. Aby zmienić swoje ustawienia, wybierz opcję **Import i eksport ustawień** na **narzędzia** menu. Aby uzyskać więcej informacji, zobacz [personalizowanie środowiska IDE programu Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-display-a-picture-at-design-time"></a>Aby wyświetlić obraz w czasie projektowania  
  
1.  Rysowanie <xref:System.Windows.Forms.PictureBox> kontrolkę w formularzu.  
  
2.  W oknie dialogowym właściwości wybierz <xref:System.Windows.Forms.PictureBox.Image%2A> właściwości, a następnie kliknij przycisk wielokropka, aby wyświetlić **Otwórz** okno dialogowe.  
  
3.  Jeśli potrzebujesz określonego typu pliku (na przykład pliki GIF), wybierz ją w **pliki typu** pole.  
  
4.  Wybierz plik, który chcesz wyświetlić.  
  
### <a name="to-clear-the-picture-at-design-time"></a>Aby wyczyścić obrazu w czasie projektowania  
  
1.  Na **właściwości** wybierz <xref:System.Windows.Forms.PictureBox.Image%2A> właściwości i kliknij prawym przyciskiem myszy mały obraz miniatury, który pojawia się po lewej stronie nazwy obiektu obrazu. Wybierz **resetowania**.  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Windows.Forms.PictureBox>
- [PictureBox, kontrolka — omówienie](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)
- [Instrukcje: Modyfikowanie rozmiaru lub położenia obrazu w czasie wykonywania](../../../../docs/framework/winforms/controls/how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [Instrukcje: Ustawienie obrazów w czasie wykonywania](../../../../docs/framework/winforms/controls/how-to-set-pictures-at-run-time-windows-forms.md)
- [PictureBox, kontrolka](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)
