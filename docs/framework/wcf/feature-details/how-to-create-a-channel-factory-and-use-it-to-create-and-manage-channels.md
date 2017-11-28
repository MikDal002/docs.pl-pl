---
title: "Instrukcje: Tworzenie fabryki kanałów i używanie jej do tworzenia kanałów oraz zarządzania nimi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 018dcc30-9f61-419e-af8e-412a85e8d282
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: cb2e8384fca96149babb5df01e25a1b890db6ad3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-create-a-channel-factory-and-use-it-to-create-and-manage-channels"></a>Instrukcje: Tworzenie fabryki kanałów i używanie jej do tworzenia kanałów oraz zarządzania nimi
<xref:System.ServiceModel.DuplexChannelFactory%601> Klasa umożliwia tworzenie i zarządzanie nimi kanałach dupleksowych różnych typów używanych przez klientów do wysyłania i odbierania wiadomości do i z punktów końcowych usługi.  
  
## <a name="example"></a>Przykład  
 Poniższy kod przedstawia sposób utworzyć fabryki kanałów i użyć go do tworzenia i zarządzania kanałów.  
  
 [!code-csharp[S_CustomAuthentication#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_customauthentication/cs/instance.cs#1)]  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.ServiceModel.DuplexChannelFactory%601>