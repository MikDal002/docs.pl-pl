---
title: 'Instrukcje: Definiowanie zmieniania rozmiaru i pozycjonowania zachowania w podzielonym oknie'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- split windows [Windows Forms], resizing
- splitter windows [Windows Forms], resizing
- SplitContainer control [Windows Forms], resizing
ms.assetid: 9bf73f36-ed2d-4a02-b15a-0770eff4fdfa
ms.openlocfilehash: a0e16a1961e5eb7fcb81503d0ccead38e08974dc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54628256"
---
# <a name="how-to-define-resize-and-positioning-behavior-in-a-split-window"></a>Instrukcje: Definiowanie zmieniania rozmiaru i pozycjonowania zachowania w podzielonym oknie
Panele <xref:System.Windows.Forms.SplitContainer> kontroli nadają się również do bycia ze zmienionym rozmiarem i przetwarzany przez użytkowników. Jednak będzie konieczny będzie Aby programistycznie sterować rozdzielacza — gdzie jest umieszczony i w jakim stopniu można go przenieść.  
  
 <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> Właściwości i inne właściwości na <xref:System.Windows.Forms.SplitContainer> kontroli zapewniają ścisłą kontrolę nad zachowaniem interfejsu użytkownika do własnych potrzeb. Te właściwości są wymienione w poniższej tabeli.  
  
|Nazwa|Opis|  
|----------|-----------------|  
|<xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> Właściwość|Określa, czy rozdzielacza ruchome za pomocą klawiatury lub myszy.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> Właściwość|Określa odległość w pikselach pasek podziału ruchome z lewej lub górnej krawędzi.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> Właściwość|Określa minimalną odległość w pikselach, że rozdzielacza mogą być przenoszone przez użytkownika.|  
  
 Poniższy przykład modyfikuje <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> właściwości do utworzenia efektu "przyciągania rozdzielacz"; gdy użytkownik przeciąga rozdzielacz, zwiększa się w jednostkach 10 pikseli, a nie wartość domyślna: 1.  
  
### <a name="to-define-splitcontainer-resize-behavior"></a>Aby zdefiniować zachowanie przy zmianie rozmiaru SplitContainer  
  
1.  W procedurze, należy ustawić <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> właściwość żądany rozmiar, dzięki czemu uzyskuje się zachowanie "przyciąganie" rozdzielacza.  
  
     W poniższym przykładzie kodu w formularzu <xref:System.Windows.Forms.Form.Load> zdarzenie, podziału w ramach <xref:System.Windows.Forms.SplitContainer> kontrolki jest ustawiona na szybkie 10 pikseli po przeciągnięciu.  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, _  
        ByVal e As System.EventArgs) Handles MyBase.Load  
        Dim splitSnapper as new SplitContainer()  
        splitSnapper.SplitterIncrement = 10  
        splitSnapper.Dock = DockStyle.Fill  
        splitSnapper.Parent = me  
    End Sub  
    ```  
  
    ```csharp  
    private void Form1_Load(System.Object sender, System.EventArgs e)  
    {  
        SplitContainer splitSnapper = new SplitContainer();  
        splitSnapper.SplitterIncrement = 10;  
        splitSnapper.Dock = DockStyle.Fill;  
        splitSnapper.Parent = this;  
    }  
    ```  
  
     (Visual C#) Umieść następujący kod w Konstruktorze formularza, aby zarejestrować program obsługi zdarzeń.  
  
    ```csharp  
    this.Load += new System.EventHandler(this.Form1_Load);  
    ```  
  
     Przenoszenie rozdzielacza nieco do lewej lub prawej odniesie żadnego skutku zauważalny; Gdy wskaźnik myszy przechodzi 10 pikseli w dowolnym kierunku, rozdzielacza będą przyciągane do nowej pozycji.  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>
