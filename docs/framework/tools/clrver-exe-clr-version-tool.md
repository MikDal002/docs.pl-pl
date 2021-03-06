---
title: Clrver.exe (Narzędzie wersji środowiska CLR)
ms.date: 03/30/2017
helpviewer_keywords:
- Clrver.exe
- CLR Version tool
ms.assetid: cbc2ee86-bdc8-4a65-a8f1-ba23bce3a699
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e5543e49ea44c20a536a7097277b246d4041522a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54735438"
---
# <a name="clrverexe-clr-version-tool"></a>Clrver.exe (Narzędzie wersji środowiska CLR)
Narzędzia wersji środowiska CLR (Clrver.exe) raportuje wszystkie wersje środowiska uruchomieniowego języka wspólnego (CLR) zainstalowane na komputerze.  
  
 To narzędzie jest instalowane automatycznie z programem Visual Studio. Aby uruchomić narzędzie, należy użyć wiersz polecenia programisty dla programu Visual Studio (lub wiersza polecenia programu Visual Studio Windows 7). Aby uzyskać więcej informacji, zobacz [wiersz polecenia](../../../docs/framework/tools/developer-command-prompt-for-vs.md).  
  
 W wierszu polecenia wpisz następujące polecenie:  
  
## <a name="syntax"></a>Składnia  
  
```  
clrver [option]  
```  
  
## <a name="options"></a>Opcje  
  
|Opcja|Opis|  
|------------|-----------------|  
|`-all`|Wyświetla wszystkie procesy na komputerze używające środowiska CLR.|  
|*Identyfikator PID*|Wyświetla wersje środowiska CLR używane przez proces, który ma określony identyfikator procesu (PID).|  
|`-?`|Wyświetla składnię polecenia i opcje narzędzia.|  
  
## <a name="remarks"></a>Uwagi  
 Wywołanie procesu Clrver.exe bez opcji powoduje wyświetlenie wszystkich zainstalowanych wersji środowiska CLR. Jeśli określisz PID dla innego użytkownika, musisz mieć uprawnienia administracyjne, aby uzyskać informacje o wersji.  
  
> [!NOTE]
>  W systemie Windows Vista i nowszych Kontrola konta użytkownika (UAC) określa uprawnienia użytkownika. Jeśli jesteś członkiem wbudowanej grupy Administratorzy, masz przypisane dwa tokeny dostępu w czasie wykonywania: token dostępu użytkownika standardowego i token dostępu administratora. Domyślnie jesteś w roli użytkownika standardowego. Aby wykonać kod wymagający uprawnień administracyjnych, musisz najpierw podwyższenie swoje uprawnienia z użytkownika standardowego do administratora. Możesz to zrobić podczas uruchamiania wiersza polecenia, klikając prawym przyciskiem myszy ikonę wiersza polecenia i wskazując, że chcesz procować jako administrator.  
  
 Próba ustalenia wersji środowiska CLR dla procesów SYSTEM, USŁUGA LOKALNA i USŁUGA SIECIOWA powoduje wyświetlenie komunikatu, że PID nie istnieje.  
  
## <a name="examples"></a>Przykłady  
 Następujące polecenie wyświetla listę wszystkich wersji środowiska CLR zainstalowanych na komputerze.  
  
 `clrver`  
  
 Następujące polecenie wyświetla wersję środowiska CLR używanego przez proces 128.  
  
 `clrver 128`  
  
 Następujące polecenie wyświetla wszystkie zarządzane procesy i wersję używanego przez nie środowiska CLR.  
  
 `Clrver -all`  
  
## <a name="see-also"></a>Zobacz także
- [Narzędzia](../../../docs/framework/tools/index.md)
- [Wiersze polecenia](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
