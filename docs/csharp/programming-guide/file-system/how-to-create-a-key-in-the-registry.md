---
title: 'Instrukcje: Utwórz klucz rejestru (Visual C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- registry, adding keys and values [C#]
- registry keys, creating [C#]
- keys, creating in registry
ms.assetid: 8fa475b0-e01f-483a-9327-fd03488fdf5d
ms.openlocfilehash: af796affa669d0f21e9d503f5263ad26b537fb91
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54553775"
---
# <a name="how-to-create-a-key-in-the-registry-visual-c"></a>Instrukcje: Utwórz klucz rejestru (Visual C#)
Ten przykład dodaje parę wartości "Name" i "Isabella" do rejestru bieżącego użytkownika, pod kluczem "Nazwy".  
  
## <a name="example"></a>Przykład  
  
```csharp  
Microsoft.Win32.RegistryKey key;  
key = Microsoft.Win32.Registry.CurrentUser.CreateSubKey("Names");  
key.SetValue("Name", "Isabella");  
key.Close();  
```  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  
  
-   Skopiuj kod i wklej go w `Main` metoda aplikacji konsoli.  
  
-   Zastąp `Names` parametr o nazwie klucza znajdującą się bezpośrednio pod węzłem rejestru HKEY_CURRENT_USER.  
  
-   Zastąp `Name` parametr z nazwą wartości znajdującą się bezpośrednio pod węzłem nazw.  
  
## <a name="robust-programming"></a>Niezawodne programowanie  
 Zbadaj strukturę rejestru w celu znalezienia odpowiedniej lokalizacji dla klucza. Na przykład możesz otworzyć klucz oprogramowania bieżącego użytkownika, a następnie utworzyć klucz z nazwą Twojej firmy. Następnie dodaj wartości rejestru do klucza Twojej firmy.  
  
 Następujące warunki mogłyby spowodować wyjątek:  
  
-   Nazwa klucza ma wartość null.  
  
-   Użytkownik nie ma uprawnień do tworzenia kluczy rejestru.  
  
-   Nazwa klucza przekracza limit 255 znaków.  
  
-   Klucz jest zamknięty.  
  
-   Klucz rejestru jest tylko do odczytu.  
  
## <a name="net-framework-security"></a>Zabezpieczenia.NET Framework  
 Bezpieczniej jest do zapisywania danych w folderze użytkownika — `Microsoft.Win32.Registry.CurrentUser` — a nie na komputerze lokalnym — `Microsoft.Win32.Registry.LocalMachine`.  
  
 Kiedy tworzysz wartość rejestru, musisz zdecydować, co należy zrobić, jeśli ta wartość już istnieje. Inny proces, fałszywy, być może już utworzył wartość i masz do niego dostęp. Dane są umieszczane w wartości rejestru, dane są dostępne dla innego procesu. Aby tego uniknąć, należy użyć.`Overload:Microsoft.Win32.RegistryKey.GetValue` Metoda. Zwraca wartość null, jeśli klucz już istnieje.  
  
 Nie jest bezpieczne przechowywanie wpisów tajnych, takich jak hasła, w rejestrze jako zwykłego tekstu, nawet jeśli klucz rejestru jest chroniony przez listy kontroli dostępu (ACL).  
  
## <a name="see-also"></a>Zobacz także

- <xref:System.IO?displayProperty=nameWithType>
- [Przewodnik programowania w języku C#](../../../csharp/programming-guide/index.md)
- [System plików i rejestr (C# Programming Guide)](../../../csharp/programming-guide/file-system/index.md)
- [Odczyt, zapis i usuwanie z rejestru z C#](https://www.codeproject.com/Articles/3389/Read-write-and-delete-from-registry-with-C)
