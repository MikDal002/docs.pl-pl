---
title: Określanie zestawu znaków
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- platform invoke, attribute fields
- attribute fields in platform invoke, CharSet
- CharSet field
ms.assetid: a8347eb1-295f-46b9-8a78-63331f9ecc50
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 45810390ced8584ea7b37908a9e4af8d3da73f34
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549853"
---
# <a name="specifying-a-character-set"></a>Określanie zestawu znaków
<xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> Pole kontroluje kierowanie ciągu i określa, jak wywołanie platformy znajduje nazwy funkcji w bibliotece DLL. W tym temacie opisano obie zachowania.  
  
 Niektóre interfejsy API wyeksportować dwie wersje funkcji, które przyjmują argumenty typu string: wąskiego (ANSI) i dwubajtowych (Unicode). Win32 API zawiera na przykład następujące nazwy punktu wejścia dla **MessageBox** funkcji:  
  
-   **MessageBoxA**  
  
     Zawiera formatowanie ANSI 1-bajtowych wartości znakowych rozróżnianych na podstawie "A", po której dołączany do wybranej nazwy punktu wejścia. Wywołania **MessageBoxA** zawsze sformatować przeprowadzanie marshalingu ciągów ANSI, co jest często spotykane na platformach Windows 95 i Windows 98.  
  
-   **MessageBoxW**  
  
     Zawiera formatowanie 2-bajtowych wartości znakowych Unicode, rozróżnianych na podstawie "W" dołączany do wybranej nazwy punktu wejścia. Wywołania **MessageBoxW** zawsze przeprowadzanie marshalingu ciągów w formacie Unicode, co jest często spotykane na platformach Windows NT, Windows 2000 i Windows XP.  
  
## <a name="string-marshaling-and-name-matching"></a>Marshaling ciągów i dopasowywanie nazw  
 **CharSet** pole akceptuje następujące wartości:  
  
 **CharSet.Ansi** (wartość domyślna)  
  
-   Ciąg marshalingu  
  
     Wywołanie platformy marshals ciągi z ich formatu zarządzanych (Unicode) na ANSI format.  
  
-   Dopasowywanie nazw  
  
     Gdy <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType> pole jest **true**, ponieważ jest ona domyślnie w [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], wyszukuje tylko należy określić nazwę wywołania platformy. Na przykład, jeśli określisz **MessageBox**, wyszukuje wywołania platformy **MessageBox** i kończy się niepowodzeniem, gdy nie można odnaleźć dokładnej pisowni.  
  
     Gdy **ExactSpelling** pole jest **false**, ponieważ jest ona domyślnie w języku C++ i C#, pierwsze wywołanie platformy wyszukuje unmangled aliasu (**MessageBox**), a następnie zniekształcone nazwy (**MessageBoxA**) Jeśli nie zostanie znaleziony unmangled aliasu. Należy zauważyć, że zachowanie Dopasowywanie nazw ANSI różni się od zachowania Dopasowywanie nazw Unicode.  
  
 **CharSet.Unicode**  
  
-   Ciąg marshalingu  
  
     Wywołanie platformy ciągi kopie z ich formatu zarządzanych (Unicode) do formatu Unicode.  
  
-   Dopasowywanie nazw  
  
     Gdy **ExactSpelling** pole jest **true**, ponieważ jest ona domyślnie w [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], wyszukuje tylko należy określić nazwę wywołania platformy. Na przykład, jeśli określisz **MessageBox**, wyszukuje wywołania platformy **MessageBox** i kończy się niepowodzeniem, jeśli nie może zlokalizować dokładnej pisowni.  
  
     Gdy **ExactSpelling** pole jest **false**, ponieważ jest ona domyślnie w języku C++ i C#, pierwsze wywołanie platformy wyszukuje zniekształcone nazwy (**MessageBoxW**), a następnie unmangled alias (**MessageBox**) Jeśli nie znaleziono zniekształcone nazwy. Należy zauważyć, że zachowanie Dopasowywanie nazw Unicode różni się od zachowania Dopasowywanie nazw ANSI.  
  
 **CharSet.Auto**  
  
-   Wywołanie platformy wybiera między ANSI i Unicode formaty w czasie wykonywania, oparte na platformie docelowej.  
  
## <a name="specifying-a-character-set-in-visual-basic"></a>Określanie zestawu znaków w języku Visual Basic  
 Poniższy przykład deklaruje **MessageBox** funkcja trzy razy, każdorazowo przy użyciu różnych zachowanie zestawu znaków. Można określić zachowanie zestawu znaków w języku Visual Basic, dodając **Ansi**, **Unicode**, lub **automatycznie** — słowo kluczowe do instrukcji deklaracji.  
  
 Jeżeli pominięto słowa kluczowego zestaw znaków, jak odbywa się w pierwszej instrukcji deklaracji <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> pola wartość domyślna to zestawu znaków ANSI. Drugi i trzeci instrukcji w przykładzie jawnie określić znak, który został ustawiony za pomocą słowa kluczowego.  
  
```vb  
Imports System.Runtime.InteropServices  
  
Public Class Win32  
   Declare Function MessageBoxA Lib "user32.dll"(ByVal hWnd As Integer, _  
       ByVal txt As String, ByVal caption As String, _  
       ByVal Typ As Integer) As Integer  
  
   Declare Unicode Function MessageBoxW Lib "user32.dll" _  
       (ByVal hWnd As Integer, ByVal txt As String, _  
        ByVal caption As String, ByVal Typ As Integer) As Integer  
  
   Declare Auto Function MessageBox Lib "user32.dll" _  
       (ByVal hWnd As Integer, ByVal txt As String, _  
        ByVal caption As String, ByVal Typ As Integer) As Integer  
End Class  
```  
  
## <a name="specifying-a-character-set-in-c-and-c"></a>Określanie zestawu znaków w C# i C++  
 <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> Pole identyfikuje podstawowy zestaw znaków jako ANSI lub Unicode. Formanty, jak powinny być wprowadzane argumenty typu string do metody zestawu znaków. Aby wskazać zestaw znaków, użyj jednej z następujących form:  
  
```csharp  
[DllImport("dllname", CharSet=CharSet.Ansi)]  
[DllImport("dllname", CharSet=CharSet.Unicode)]  
[DllImport("dllname", CharSet=CharSet.Auto)]  
```  
  
```cpp  
[DllImport("dllname", CharSet=CharSet::Ansi)]  
[DllImport("dllname", CharSet=CharSet::Unicode)]  
[DllImport("dllname", CharSet=CharSet::Auto)]  
```  
  
 W poniższym przykładzie przedstawiono trzy definicje zarządzanych **MessageBox** opartego na atrybutach funkcji do określenia zestawu znaków. W pierwszym definicji przez jej pominięcia **CharSet** pola wartość domyślna to zestawu znaków ANSI.  
  
```csharp  
[DllImport("user32.dll")]  
    public static extern int MessageBoxA(int hWnd, String text,   
        String caption, uint type);  
[DllImport("user32.dll", CharSet=CharSet.Unicode)]  
    public static extern int MessageBoxW(int hWnd, String text,   
        String caption, uint type);  
[DllImport("user32.dll", CharSet=CharSet.Auto)]  
    public static extern int MessageBox(int hWnd, String text,   
        String caption, uint type);  
```  
  
```cpp  
typedef void* HWND;  
  
//Can use MessageBox or MessageBoxA.  
[DllImport("user32")]  
extern "C" int MessageBox(HWND hWnd,  
                          String* pText,  
                          String* pCaption,  
                          unsigned int uType);  
  
//Can use MessageBox or MessageBoxW.  
[DllImport("user32", CharSet=CharSet::Unicode)]  
extern "C" int MessageBoxW(HWND hWnd,  
                          String* pText,  
                          String* pCaption,  
                          unsigned int uType);  
  
//Must use MessageBox.  
[DllImport("user32", CharSet=CharSet::Auto)]  
extern "C" int MessageBox(HWND hWnd,  
                          String* pText,  
                          String* pCaption,  
                          unsigned int uType);  
```  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [Tworzenie prototypów w kodzie zarządzanym](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)
- [Przykłady wywołań platformy](../../../docs/framework/interop/platform-invoke-examples.md)
- [Marshaling danych w wywołaniu platformy](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)
