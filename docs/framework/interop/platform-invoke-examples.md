---
title: Przykłady wywołań platformy
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [.NET Framework], platform invoke
- unmanaged functions
- COM interop, platform invoke
- platform invoke, examples
- interoperation with unmanaged code, platform invoke
- DLL functions
ms.assetid: 15926806-f0b7-487e-93a6-4e9367ec689f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 612cd108e37d6f072bafed919c14532498352e4f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54628932"
---
# <a name="platform-invoke-examples"></a>Przykłady wywołań platformy
W poniższych przykładach pokazano, jak definiować i wywoływać **MessageBox** funkcji w bibliotece User32.dll, przekazując prostego ciągu jako argument. W przykładach <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> pole jest ustawione na **automatycznie** umożliwiające platformę docelową określić szerokość znaków i ciągów marshaling.  
  
 [!code-cpp[Conceptual.Interop.PInvoke#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.Interop.PInvoke/cpp/Example.cpp#1)] 
 [!code-csharp[Conceptual.Interop.PInvoke#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.Interop.PInvoke/cs/Example1.cs#1)] 
 [!code-vb[Conceptual.Interop.PInvoke#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.Interop.PInvoke/vb/Example1.vb#1)]  
  
 Aby uzyskać więcej przykładów, zobacz [Marshaling danych za pomocą wywołania platformy](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md).  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [Tworzenie prototypów w kodzie zarządzanym](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)
- [Określanie zestawu znaków](../../../docs/framework/interop/specifying-a-character-set.md)
