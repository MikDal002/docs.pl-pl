---
title: 'Instrukcje: Przywracanie stref czasowych z zasobu osadzonego'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], deserializing
- time zones [.NET Framework], restoring
ms.assetid: 6b7b4de9-da07-47e3-8f4c-823f81798ee7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 71fc4e04c87dfa3b83eabb06361d1da94a512a5e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54656808"
---
# <a name="how-to-restore-time-zones-from-an-embedded-resource"></a>Instrukcje: Przywracanie stref czasowych z zasobu osadzonego

W tym temacie opisano przywracanie stref czasowych, które zostały zapisane w pliku zasobów. Aby uzyskać informacje i instrukcje dotyczące zapisywanie stref czasowych, zobacz [jak: Zapisywanie stref czasowych w zasobie osadzonym](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md).

### <a name="to-deserialize-a-timezoneinfo-object-from-an-embedded-resource"></a>Do deserializacji obiektów TimeZoneInfo z zasobu osadzonego

1. Jeśli strefa czasowa do pobrania jest niestandardowa strefa czasowa, spróbuj utworzyć przy użyciu <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> metody.

2. Utwórz wystąpienie <xref:System.Resources.ResourceManager> obiektu przez przekazanie w pełni kwalifikowana nazwa pliku zasobu osadzonego i odwołania do zestawu, który zawiera plik zasobów.

   Jeśli nie można określić w pełni kwalifikowaną nazwę pliku zasobów osadzonych, użyj [Ildasm.exe (dezasembler IL)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) zbadanie manifest zestawu. `.mresource` Wpis identyfikuje zasób. W tym przykładzie, jest w pełni kwalifikowaną nazwę zasobu `SerializeTimeZoneData.SerializedTimeZones`.

   Plik zasobów jest osadzony w tym samym zestawie, który zawiera kod podczas tworzenia wystąpienia strefy czasowej, możesz pobrać odwołanie do niej przez wywołanie metody `static` (`Shared` w języku Visual Basic) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> metody.

3. Jeśli wywołanie <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> metoda kończy się niepowodzeniem, lub jeśli niestandardowa strefa czasowa ma zostać utworzona, należy pobrać ciąg, który zawiera Zserializowany strefy czasowej przez wywołanie metody <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> metody.

4. Deserializowanie danych strefy czasowej przez wywołanie metody <xref:System.TimeZoneInfo.FromSerializedString%2A> metody.

## <a name="example"></a>Przykład

Poniższy przykład deserializuje <xref:System.TimeZoneInfo> obiektu przechowywanego w plik osadzony zasób XML platformy .NET.

[!code-csharp[TimeZone2.Serialization#3](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#3)]
[!code-vb[TimeZone2.Serialization#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#3)]

Ten kod ilustruje wyjątków, aby upewnić się, że <xref:System.TimeZoneInfo> obiektu wymagane przez aplikację jest obecny. Najpierw próbuje utworzyć wystąpienie <xref:System.TimeZoneInfo> obiektu, pobierając go z rejestru przy użyciu <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> metody. Jeśli nie można utworzyć wystąpienia strefy czasowej, kod pobiera z pliku zasobu osadzonego.

Ponieważ dane dla niestandardowych stref czasowych (stref czasowych za pomocą <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> metoda) nie są przechowywane w rejestrze, kod nie wywołuje <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> utworzyć strefę czasową dla Palmer, Antarktyda. Zamiast tego należy od razu wygląda na to do pliku zasobów osadzonych, by pobrać ciąg, który zawiera dane strefę czasową, przed wywołaniem <xref:System.TimeZoneInfo.FromSerializedString%2A> metody.

## <a name="compiling-the-code"></a>Kompilowanie kodu

Ten przykład wymaga:

* Odwołanie do System.Windows.Forms.dll i System.Core.dll dodania do projektu.

* Czy następujących przestrzeni nazw można zaimportować:

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a>Zobacz także

- [Daty, godziny i strefy czasowe](../../../docs/standard/datetime/index.md)
- [Strefy czasowe — omówienie](../../../docs/standard/datetime/time-zone-overview.md)
- [Instrukcje: Zapisywanie stref czasowych w zasobie osadzonym](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
