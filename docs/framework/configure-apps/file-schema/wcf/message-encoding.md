---
title: Kodowanie komunikatu
ms.date: 03/30/2017
ms.assetid: f30ee941-aca9-4c67-82a5-421568496f07
ms.openlocfilehash: d797b810af5df5fc1acf31e0ab6338689da9f55c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54734016"
---
# <a name="message-encoding"></a>Kodowanie komunikatu
Kodowanie jest procesem przekształcania zestawu znaków Unicode do sekwencji bajtów. Dekodowanie jest procesu. Windows Communication Foundation (WCF) obejmuje trzy typy kodowania dla protokołu SOAP wiadomości: Tekst pliku binarnego i mechanizmu optymalizacji transmisji wiadomości (MTOM).  
  
 `binaryMessageEncoding` Sekcji konfiguracji określa znak kodowanie i wersjonowanie wiadomości używanych dla wiadomości XML na podstawie pliku binarnego. Koder komunikatu binarnego koduje komunikatów Windows Communication Foundation (WCF) w pliku binarnego podczas transmisji. Podczas tego kodowania skutkuje bardzo szybkie transmisję wiadomości, współdziałanie oparte na WS-* standardów zostaną utracone.  
  
 `mtomMessageEncoding` Sekcji konfiguracji określa znak kodowanie i wersjonowanie wiadomości używanych dla wiadomości przy użyciu kodowania komunikatu transmisji optymalizacji mechanizm (MTOM). (MTOM) to technologia wydajne przekazywania danych binarnych w komunikatach usługi Windows Communication Foundation (WCF). Koder MTOM próbuje zachować równowagę pomiędzy współdziałania i wydajność. Kodowanie MTOM przesyła większość kodu XML w postaci tekstowej, ale optymalizuje dużych bloków danych binarnych, przekazywania ich jako — jest bez konwersji na tekst.  
  
 `textMessageEncoding` Sekcji konfiguracji określa koder tekstu, używany do tworzenia opartych na tekst wiadomości na łączu. Komunikaty generowane przez ten koder nadają się dla protokołu WS-* na podstawie międzyoperacyjności. Klient usługi sieci Web lub usługa sieci Web zazwyczaj może zrozumieć tekstowych XML. Jednak przesyłania dużych bloków danych binarnych jako tekst jest najmniej efektywną metodę kodowania wiadomości XML  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- [Powiązania](../../../../../docs/framework/wcf/bindings.md)
- [Rozszerzanie powiązań](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [Powiązania niestandardowe](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [Wybieranie kodera komunikatów](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
