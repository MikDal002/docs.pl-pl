---
title: 'Instrukcje: Wyłączanie bezpiecznej sesji przy użyciu klasy WSFederationHttpBinding'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
ms.assetid: 675fa143-6a4e-4be3-8afc-673334ab55ec
ms.openlocfilehash: 8c03bb9601ecbaaf8694d1df26ba43e34434ac47
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54720031"
---
# <a name="how-to-disable-secure-sessions-on-a-wsfederationhttpbinding"></a>Instrukcje: Wyłączanie bezpiecznej sesji przy użyciu klasy WSFederationHttpBinding
Niektóre usługi może wymagać poświadczeń federacyjnych, ale nie obsługują bezpiecznej sesji. W takiej sytuacji należy wyłączyć funkcję bezpiecznej sesji. W odróżnieniu od <xref:System.ServiceModel.WSHttpBinding>, <xref:System.ServiceModel.WSFederationHttpBinding> klasa nie umożliwia wyłączanie bezpiecznej sesji podczas komunikacji z usługą. Zamiast tego należy utworzyć niestandardowego powiązania, który zastępuje ustawienia bezpiecznej sesji za pomocą narzędzi bootstrap.  
  
 W tym temacie przedstawiono sposób modyfikowania elementów wiązania zawartych w <xref:System.ServiceModel.WSFederationHttpBinding> do tworzenia niestandardowego powiązania. Wynik jest taka sama jak <xref:System.ServiceModel.WSFederationHttpBinding> z tą różnicą, że nie używa bezpiecznych sesji.  
  
### <a name="to-create-a-custom-federated-binding-without-secure-session"></a>Aby utworzyć niestandardową federacyjnego powiązania bez bezpiecznej sesji  
  
1.  Utwórz wystąpienie obiektu <xref:System.ServiceModel.WSFederationHttpBinding> klasy obowiązkowo w kodzie lub przez załadowanie go z pliku konfiguracji.  
  
2.  Klonuj <xref:System.ServiceModel.WSFederationHttpBinding> do <xref:System.ServiceModel.Channels.CustomBinding>.  
  
3.  Znajdź <xref:System.ServiceModel.Channels.SecurityBindingElement> w <xref:System.ServiceModel.Channels.CustomBinding>.  
  
4.  Znajdź <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters> w <xref:System.ServiceModel.Channels.SecurityBindingElement>.  
  
5.  Zastąp oryginalny <xref:System.ServiceModel.Channels.SecurityBindingElement> przy użyciu elementu powiązania zabezpieczeń dla uruchamiania z <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters>.  
  
## <a name="example"></a>Przykład  
 Ten poniższy przykład obejmuje tworzenie niestandardowego powiązania federacyjnego bez bezpiecznej sesji.  
  
 [!code-csharp[c_CustomFederationBinding#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customfederationbinding/cs/c_customfederationbinding.cs#0)]
 [!code-vb[c_CustomFederationBinding#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customfederationbinding/vb/c_customfederationbinding.vb#0)]  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  
  
-   Aby skompilować przykład kodu, Utwórz projekt, który odwołuje się do zestawu System.ServiceModel.dll.  
  
## <a name="see-also"></a>Zobacz także
- [Powiązania i zabezpieczenia](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)
