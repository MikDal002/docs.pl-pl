---
title: 'Instrukcje: Wyrównywanie formantu z krawędziami formularzy w czasie projektowania'
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], docking using designer
- Dock property [Windows Forms], aligning controls (using designer)
ms.assetid: 51f08998-5e3b-4330-be58-a4edd0eb60f4
ms.openlocfilehash: 27bf9da02f16f0f5ee036153beeec75d5a37bf67
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54716326"
---
# <a name="how-to-align-a-control-to-the-edges-of-forms-at-design-time"></a>Instrukcje: Wyrównywanie formantu z krawędziami formularzy w czasie projektowania
Ułatwia kontrolki wyrównane do krawędzi formularzy, ustawiając <xref:System.Windows.Forms.Control.Dock%2A>. Ta właściwość wskazuje, której formant znajduje się w formularzu. <xref:System.Windows.Forms.Control.Dock%2A> Właściwość można ustawić następujące wartości:  
  
|Ustawienie|Wpływ na Twoją kontrolą|  
|-------------|----------------------------|  
|<xref:System.Windows.Forms.DockStyle.Bottom>|Doków do dolnej części formularza.|  
|<xref:System.Windows.Forms.DockStyle.Fill>|Wypełnia całe pozostałe miejsce w formularzu.|  
|<xref:System.Windows.Forms.DockStyle.Left>|Doków do lewej części formularza.|  
|<xref:System.Windows.Forms.DockStyle.None>|Czy nie Zadokuj z dowolnego miejsca i pojawia się w lokalizacji określonej przez jego <xref:System.Windows.Forms.Control.Location%2A>.|  
|<xref:System.Windows.Forms.DockStyle.Right>|Doków prawą stronę formularza.|  
|<xref:System.Windows.Forms.DockStyle.Top>|Doków do górnej części formularza.|  
  
 Wartości te można ustawić w taki sposób, w kodzie. Aby uzyskać więcej informacji, zobacz [jak: Wyrównywanie formantu z krawędziami formularzy](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms.md).  
  
> [!NOTE]
>  Okna dialogowe i polecenia menu mogą się różnić od tych opisanych w Pomocy, w zależności od ustawień aktywnych lub wydania. Aby zmienić swoje ustawienia, wybierz opcję **Import i eksport ustawień** na **narzędzia** menu. Aby uzyskać więcej informacji, zobacz [personalizowanie środowiska IDE programu Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-set-the-dock-property-for-your-control-at-design-time"></a>Aby ustawić właściwość dokowania dla formantu w czasie projektowania  
  
1.  W programie Windows Forms Designer wybierz formant.  
  
2.  W **właściwości** , kliknij listę rozwijaną pola obok <xref:System.Windows.Forms.Control.Dock%2A> właściwości.  
  
     Graficzny interfejs reprezentujący sześć najbardziej <xref:System.Windows.Forms.Control.Dock%2A> wyświetlane ustawienia.  
  
3.  Wybierz odpowiednie ustawienie.  
  
4.  Formant teraz zostanie zadokowany w sposób określony w ustawieniu.  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType>
- [Instrukcje: Wyrównywanie formantu z krawędziami formularzy](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms.md)
- [Przewodnik: Rozmieszczanie kontrolek na formularzach Windows Forms za pomocą linii przyciągania](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [Instrukcje: Zakotwiczenia formantów na formularzach Windows Forms](../../../../docs/framework/winforms/controls/how-to-anchor-controls-on-windows-forms.md)
- [Instrukcje: Zakotwiczenie i dokowanie formantów podrzędnych w formancie TableLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [Instrukcje: Zakotwiczenie i dokowanie formantów podrzędnych w formancie FlowLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [Przewodnik: Rozmieszczanie kontrolek na formularzach Windows Forms za pomocą TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Przewodnik: Rozmieszczanie kontrolek na formularzach Windows Forms za pomocą FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Opracowywanie kontrolek formularzy Windows Forms w czasie projektowania](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)
