---
title: StatusBar — Informacje o formancie [Formularze systemu Windows]
ms.date: 03/30/2017
f1_keywords:
- StatusBar
helpviewer_keywords:
- StatusBar control [Windows Forms], about StatusBar control
- status bars
ms.assetid: b7b9852c-633d-4416-bb2e-94852b989c6c
ms.openlocfilehash: c3e52a91a31eb898d0176bc35a97cda7de9a8368
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491353"
---
# <a name="statusbar-control-overview-windows-forms"></a>StatusBar — Informacje o formancie [Formularze systemu Windows]
> [!IMPORTANT]
>  <xref:System.Windows.Forms.StatusStrip> i <xref:System.Windows.Forms.ToolStripStatusLabel> kontrolki Zastąp i dodawania funkcjonalności do <xref:System.Windows.Forms.StatusBar> i <xref:System.Windows.Forms.StatusBarPanel> kontroluje; jednak <xref:System.Windows.Forms.StatusBar> i <xref:System.Windows.Forms.StatusBarPanel> kontrolek zostaną zachowane dla zgodności z poprzednimi wersjami i użycia w przyszłości, jeśli możesz Wybierz.  
  
 Formularze Windows [StatusBar, kontrolka](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) jest używana w formularzach jako obszar, zwykle są wyświetlane w dolnej części okna, w którym aplikacja może wyświetlać różne rodzaje informacji o stanie. <xref:System.Windows.Forms.StatusBar> Formanty mogą mieć paneli paska stanu na nich, które wyświetlania tekstu lub ikony wskazujące stan lub szeregu ikony w animacji, które wskazują, że proces działa; na przykład [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] wskazująca, że dokument jest zapisywany.  
  
## <a name="using-the-statusbar-control"></a>Używanie formantu StatusBar  
 Program Internet Explorer używa pasek stanu, aby wskazać adres URL strony, po najechaniu kursorem myszy nad hiperłącze. [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] zawiera informacje dotyczące Lokalizacja strony, Lokalizacja sekcji i tryby edycji, takie jak zastępowania i śledzenie poprawek; i programu Visual Studio używa pasek stanu, co zapewnia kontekstowe informacje, takie jak informujące sposoby manipulowania dokowalnych jak zadokowany lub przestawny.  
  
 Jeden komunikat o można wyświetlić na pasku stanu, ustawiając <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> właściwości `false` (ustawienie domyślne) i ustawienie <xref:System.Windows.Forms.StatusBar.Text%2A> właściwości paska stanu w tekście, które mają być wyświetlane na pasku stanu. Na pasku stanu można podzielić paneli, aby wyświetlić więcej niż jeden typ informacji przez ustawienie <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> właściwości `true` i przy użyciu <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> metody <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [Instrukcje: Określanie, które panelu w formancie StatusBar formularzy Windows został kliknięty](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)
