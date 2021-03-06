---
title: IMetaDataEmit::MergeEnd — Metoda
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.MergeEnd
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::MergeEnd
helpviewer_keywords:
- MergeEnd method [.NET Framework metadata]
- IMetaDataEmit::MergeEnd method [.NET Framework metadata]
ms.assetid: 2d64315a-1af1-4c60-aedf-f8a781914aea
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 45d85be4e4987e5a5234ca2d57c85a56f9f544bc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54657028"
---
# <a name="imetadataemitmergeend-method"></a>IMetaDataEmit::MergeEnd — Metoda
Scala do bieżącego zakresu zakresy metadanych określone przez co najmniej jeden poprzedniego wywołania [IMetaDataEmit::Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md).  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT MergeEnd ();  
```  
  
#### <a name="parameters"></a>Parametry  
 Ta metoda nie przyjmuje żadnych parametrów.  
  
## <a name="remarks"></a>Uwagi  
 Ta procedura wyzwala rzeczywiste Scalanie metadanych, wszystkich Importuj zakresy określone w tym celu przed wywołania `IMetaDataEmit::Merge`, w bieżącym zakresie danych wyjściowych.  
  
 Scalenie stosują się następujące warunki specjalne:  
  
-   Identyfikator wersji modułu (identyfikatorem MVID) nigdy nie jest importowany, ponieważ jest on unikatowy dla metadanych w zakresie importowania.  
  
-   Nie istniejących właściwości całego modułu zostaną zastąpione.  
  
     Jeśli moduł właściwości zostały skonfigurowane dla bieżącego zakresu, zostaną zaimportowane żadnych właściwości modułu. Jednakże jeśli nie ustawiono właściwości modułu w bieżącym zakresie, zaimportowaniu tylko raz, po ich pierwszym napotkaniu. Jeśli te właściwości modułu wystąpi ponownie, są one duplikaty. Jeśli są porównywane wartości wszystkich właściwości modułu (z wyjątkiem identyfikatora MVID) i duplikaty nie zostaną znalezione, zgłaszany jest błąd.  
  
-   Aby uzyskać definicje typów (`TypeDef`), bez duplikatów są scalane w bieżącym zakresie. `TypeDef` obiekty są sprawdzane duplikatów w odniesieniu do każdego *obiektu w pełni kwalifikowana nazwa* + *GUID* + *numer wersji*. Jeśli są zgodne na nazwę lub identyfikator GUID i inne elementy są różne, zgłaszany jest błąd. W przeciwnym razie, jeśli wszystkie trzy elementy są zgodne, `MergeEnd` wykonuje sprawdzenie pobieżną, aby upewnić się, wpisy są rzeczywiście duplikaty; w przeciwnym razie występuje błąd. To sprawdzenie pobieżną szuka:  
  
    -   Ten sam element członkowski deklaracji, pojawiają się w tej samej kolejności. Elementy członkowskie, które są oznaczane jako `mdPrivateScope` (zobacz [cormethodattr —](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) wyliczenie) nie są uwzględnione w tym wyboru; są one scalane specjalnie.  
  
    -   Taki sam układ klasy.  
  
     Oznacza to, że `TypeDef` obiektu muszą zawsze być spójnie i w pełni zdefiniowana w każdym zakresie metadanych w której jest zadeklarowana; jeśli jego implementacji elementu członkowskiego (dla klasy) są rozmieszczone w wielu jednostkach kompilacji, pełna definicja zakłada się, że obecny w każdym zakresie, a nie przyrostowa każdego zakresu. Na przykład jeśli nazwy parametrów są istotne dla kontraktu, ich musi być emitowane taki sam sposób do każdego zakresu; Jeśli nie są istotne, nie należy ich wydane do metadanych.  
  
     Wyjątkiem jest to, że `TypeDef` obiekt może mieć przyrostowe składowe oznaczone jako `mdPrivateScope`. Po wystąpieniu, `MergeEnd` przyrostowo dodaje je do bieżącego zakresu, bez względu na duplikaty. Ponieważ kompilator rozpoznaje zakres prywatnych, kompilator musi być odpowiedzialne za wymuszanie stosowania zasad.  
  
-   Względnych adresów wirtualnych (RVA) nie są importowane lub scalić; kompilator powinien ponownie wyemitować tych informacji.  
  
-   Atrybuty niestandardowe są scalane, tylko wtedy, gdy jest scalany elementu, do której są dołączone. Na przykład niestandardowe atrybuty powiązane z klasą zostaną scalone, po pierwszym napotkaniu klasy. Jeśli atrybutów niestandardowych, które są skojarzone z `TypeDef` lub `MemberDef` jest specyficzne dla jednostki kompilacji (takich jak sygnatura czasowa kompilacji elementu członkowskiego), nie są one scalane i zależy od kompilator, aby usunąć lub zaktualizować takie metadane.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** COR.h  
  
 **Biblioteka:** Używany jako zasób w MSCorEE.dll  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [IMetaDataEmit, interfejs](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2, interfejs](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
