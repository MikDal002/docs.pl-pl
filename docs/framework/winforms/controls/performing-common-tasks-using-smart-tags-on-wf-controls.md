---
title: 'Przewodnik: Wykonywania typowych zadań przy użyciu inteligentnych tagów w Windows Forms, formanty'
ms.date: 03/30/2017
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
ms.openlocfilehash: b17fbaea48660a47630dd310c74be9cd3cc78609
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54579319"
---
# <a name="walkthrough-performing-common-tasks-using-smart-tags-on-windows-forms-controls"></a>Przewodnik: Wykonywania typowych zadań przy użyciu inteligentnych tagów w Windows Forms, formanty
Podczas przygotowywania formularzy i kontrolek dla aplikacji Windows Forms, istnieje wiele zadań, które należy wykonać wielokrotnie. Oto niektóre z często wykonywanych zadań, które można napotkać:  
  
-   Dodawanie lub usuwanie karty na <xref:System.Windows.Forms.TabControl>.  
  
-   Dokowanie formantu do elementu nadrzędnego.  
  
-   Zmiana orientacji <xref:System.Windows.Forms.SplitContainer> kontroli.  
  
 Aby przyspieszyć rozwój, wiele kontrolek oferują tagów inteligentnych, które są menu kontekstowe, które pozwalają wykonywać typowe zadania, takie jak te przy użyciu pojedynczego gestu w czasie projektowania. Zadania te są nazywane *zleceń tagów inteligentnych*.  
  
 Tagi inteligentne pozostać dołączony do wystąpienia formantu przez cały okres ich istnienia w Projektancie i są zawsze dostępne.  
  
 Zadania zilustrowane w tym przewodniku obejmują:  
  
-   Tworzenie projektu Windows Forms  
  
-   Za pomocą tagów inteligentnych  
  
-   Włączanie i wyłączanie tagi inteligentne  
  
 Gdy skończysz, masz zrozumienia rolę odgrywaną przez te funkcje ważne układu.  
  
> [!NOTE]
>  Okna dialogowe i polecenia menu mogą się różnić od tych opisanych w Pomocy, w zależności od ustawień aktywnych lub wydania. Aby zmienić swoje ustawienia, wybierz opcję **Import i eksport ustawień** na **narzędzia** menu. Aby uzyskać więcej informacji, zobacz [personalizowanie środowiska IDE programu Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="creating-the-project"></a>Tworzenie projektu  
 Pierwszym krokiem jest tworzenie projektu i konfigurowanie formularza.  
  
#### <a name="to-create-the-project"></a>Aby utworzyć projekt  
  
1.  Utwórz projekt aplikacji systemu Windows o nazwie "SmartTagsExample" (**pliku** > **New** > **projektu**  >   **Visual C#** lub **języka Visual Basic** > **Classic Desktop** > **Windows Forms aplikacji**).  
  
2.  Wybierz formularz w **Windows Forms Designer**.  
  
## <a name="using-smart-tags"></a>Za pomocą tagów inteligentnych  
 Tagi inteligentne są zawsze dostępne w czasie projektowania dla formantów, które oferują je.  
  
#### <a name="to-use-smart-tags"></a>Tagi inteligentne  
  
1.  Przeciągnij <xref:System.Windows.Forms.TabControl> z **przybornika** do formularza. Należy pamiętać glif tagów inteligentnych (![symbol tagu inteligentnego](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) wyświetlany na stronie z <xref:System.Windows.Forms.TabControl>.  
  
2.  Kliknij symbol tagu inteligentnych. W menu skrótów, która pojawia się obok glif, wybierz **Dodaj zakładkę** elementu. Sprawdź, czy nowa strona karty zostanie dodany do <xref:System.Windows.Forms.TabControl>.  
  
3.  Przeciągnij <xref:System.Windows.Forms.TableLayoutPanel> z kontrolować **przybornika** do formularza.  
  
4.  Kliknij symbol tagu inteligentnych. W menu skrótów, która pojawia się obok glif, wybierz **Dodaj kolumnę** elementu. Sprawdź, czy nowa kolumna zostanie dodana do <xref:System.Windows.Forms.TableLayoutPanel> kontroli.  
  
5.  Przeciągnij <xref:System.Windows.Forms.SplitContainer> z kontrolować **przybornika** do formularza.  
  
6.  Kliknij symbol tagu inteligentnych. W menu skrótów, która pojawia się obok glif, wybierz **orientacji poziomej rozdzielacza** elementu. Zauważ, że <xref:System.Windows.Forms.SplitContainer> pasek podziału kontrolki jest teraz orientacji poziomej.  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>
- [Przewodnik: Dodawanie tagów inteligentnych do składnika Windows Forms](https://msdn.microsoft.com/library/a6814169-fa7d-4527-808c-637ca5c95f63)
