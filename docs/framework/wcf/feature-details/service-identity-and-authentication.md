---
title: "Uwierzytelnianie i tożsamość usług"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: authentication [WCF], specifying the identity of a service
ms.assetid: a4c8f52c-5b30-45c4-a545-63244aba82be
caps.latest.revision: "32"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5ef2d71496a5a1268492fa7c3cb55019e969b709
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="service-identity-and-authentication"></a>Uwierzytelnianie i tożsamość usług
Usługa *tożsamość punktu końcowego*jest wartość wygenerowaną przez usługę sieci Web Services Description Language (WSDL). Ta wartość propagowane do dowolnego klienta jest używany do uwierzytelniania usługi. Po inicjowania przez klienta komunikatu do punktu końcowego i usługa samodzielnie przeprowadza uwierzytelnianie klienta, klient porównuje wartości tożsamości punktu końcowego z wartością rzeczywistą zwrócił procesu uwierzytelniania punktu końcowego. Jeśli są zgodne, klient jest pewność, że ma nawiązać kontaktu z punktem końcowym usługi oczekiwanego. Funkcja ta działa jako ochrony przed *phishing* zapobiegając nastąpi przekierowanie do punktu końcowego hostowanej przez usługę złośliwego klienta.  
  
 Przykładową aplikację prezentującą ustawienie tożsamości, zobacz [tożsamość usług — przykład](../../../../docs/framework/wcf/samples/service-identity-sample.md). [!INCLUDE[crabout](../../../../includes/crabout-md.md)]punkty końcowe i adresy punktów końcowych, zobacz [adresy](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md).  
  
> [!NOTE]
>  Jeśli LanMan NT (NTLM) używany do uwierzytelniania, tożsamość usługi nie jest zaznaczone, ponieważ w obszarze NTLM, klient jest w stanie uwierzytelniania serwera. Uwierzytelnianie NTLM jest używany, gdy komputery są częścią grupy roboczej systemu Windows lub zainstalowana starsza wersja systemu Windows, która nie obsługuje uwierzytelniania Kerberos.  
  
 Gdy klient jest inicjowany przez bezpieczny kanał do wysłania komunikatu do usługi, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] infrastruktury uwierzytelnia usługi i wysyła wiadomość tylko, jeśli określono adres punktu końcowego, klient korzysta z tożsamości pasuje do tożsamości usługi.  
  
 Tożsamość przetwarzania składa się z następujących etapów:  
  
-   W czasie projektowania deweloperowi klienta określa tożsamość usługi z punktu końcowego metadanych (za pośrednictwem WSDL).  
  
-   W czasie wykonywania aplikacja klienta sprawdza oświadczenia poświadczenia zabezpieczeń przed wysłaniem komunikaty do usługi.  
  
 Tożsamość przetwarzania na kliencie jest analogiczna do uwierzytelniania klientów w usłudze. Usługa bezpiecznego nie wykonuje kodu, dopóki nie zostały uwierzytelnione poświadczenia klienta. Podobnie klient nie wysyła komunikaty do usługi, dopóki poświadczenia zostały uwierzytelnione oparte na wcześniej określane z metadanych usługi.  
  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A> Właściwość <xref:System.ServiceModel.EndpointAddress> klasa reprezentuje tożsamość usługi o nazwie przez klienta. Opis usługi <xref:System.ServiceModel.EndpointAddress.Identity%2A> w metadanych. Jeśli jest uruchomiony deweloperowi klienta [narzędzie narzędzia metadanych elementu ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) względem punktu końcowego usługi wygenerowanego konfiguracji zawiera wartość usługi <xref:System.ServiceModel.EndpointAddress.Identity%2A> właściwości. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Infrastruktury (jeśli jest skonfigurowane z zabezpieczeniami) sprawdza, czy usługa posiada określono tożsamości.  
  
> [!IMPORTANT]
>  Metadane zawiera oczekiwaną tożsamość usługi, w związku z czym zaleca się uwidaczniać metadane usługi w sposób bezpieczny, na przykład, tworząc punkt końcowy HTTPS dla usługi. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Porady: bezpieczne punkty końcowe metadanych](../../../../docs/framework/wcf/feature-details/how-to-secure-metadata-endpoints.md).  
  
## <a name="identity-types"></a>Typów tożsamości  
 Usługa może zapewnić pięć typów tożsamości. Każdy typ tożsamości odnosi się do elementu, który może zostać umieszczony w `<identity>` element w konfiguracji. Typ użyty, zależy od scenariusza i wymagań dotyczących zabezpieczeń usługi. W poniższej tabeli opisano każdy typ tożsamości.  
  
|Typ tożsamości|Opis|Typowy scenariusz|  
|-------------------|-----------------|----------------------|  
|System nazw domen (DNS)|Użyj tego elementu z certyfikatami X.509 lub konta systemu Windows. Porównuje nazwa DNS określona w poświadczeniu z wartością określoną w tym elemencie.|Sprawdź DNS umożliwia korzystanie z certyfikatów w usłudze DNS lub nazwy podmiotu. Jeśli certyfikat jest utworzony ponownie z tym samym DNS lub nazwy podmiotu, sprawdzić tożsamości jest nadal ważny. Gdy certyfikat jest ponownie, pobiera nowego klucza RSA, ale zachowuje tego samego DNS lub nazwy podmiotu. Oznacza to, że klienci nie muszą zaktualizować swoje informacje o tożsamości o usłudze.|  
|Certyfikat. Domyślnie gdy `ClientCredentialType` ma wartość Certificate.|Ten element Określa certyfikat X.509 z kodowaniem Base64 wartość do porównania z klienta.<br /><br /> Ten element służy również, korzystając z [!INCLUDE[infocard](../../../../includes/infocard-md.md)] jako poświadczeń do uwierzytelniania usługi.|Ten element ogranicza uwierzytelniania jeden certyfikat na podstawie jego wartości odcisku palca. Umożliwia użycie uwierzytelniania bardziej restrykcyjne, ponieważ wartości odcisku palca są unikatowe. To jest dostarczany z jedno zastrzeżenie:: Jeśli certyfikat jest utworzony ponownie z taką samą nazwę podmiotu, ma także nowy odcisk palca. W związku z tym klienci nie będą mogli zweryfikować usługę, chyba że jest on znany nowy odcisk palca. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Znajdowanie odcisk palca certyfikatu, zobacz [porady: Pobieranie odcisku palca certyfikatu](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).|  
|Odwołanie do certyfikatu|Taki sam jak opcja certyfikat opisanych powyżej. Jednak ten element umożliwia Określ nazwę certyfikatu i przechowywać lokalizację, z której można pobrać certyfikatu.|Taka sama jak w scenariuszu certyfikatu opisanych powyżej.<br /><br /> Korzyścią jest to, że można zmienić lokalizacji magazynu certyfikatów.|  
|RSA|Ten element określa wartość klucza RSA do porównania z klienta. Przypomina to opcja certyfikat, ale zamiast przy użyciu odcisku palca certyfikatu, klucza RSA certyfikatu zamiast niego jest używana.|Sprawdź RSA umożliwia w szczególności ograniczyć uwierzytelnianie oparte na jego klucza RSA jeden certyfikat. Umożliwia to bardziej restrykcyjne uwierzytelnianie przy użyciu określonego klucza RSA kosztem usługi, która nie działa z istniejących klientów, jeśli zmieni się wartość klucza RSA.|  
|Główna nazwa użytkownika (UPN). Domyślnie gdy `ClientCredentialType` jest ustawiony do systemu Windows i usługi procesu nie działa w ramach jednego z konta system.|Ten element Określa nazwę UPN, która jest uruchomiona w obszarze. Zobacz sekcję protokołu Kerberos i tożsamość [przesłanianie tożsamości usługi na potrzeby uwierzytelniania](../../../../docs/framework/wcf/extending/overriding-the-identity-of-a-service-for-authentication.md).|Dzięki temu, że usługa jest uruchomiona przy użyciu określonego konta użytkownika systemu Windows. Konto użytkownika może być bieżącego zalogowanego użytkownika lub usługę do uruchamiania konta określonego użytkownika.<br /><br /> To ustawienie korzysta z zabezpieczeń systemu Windows, jeśli usługa jest uruchomiona w ramach konta domeny w środowisku usługi Active Directory.|  
|Główna nazwa usługi (SPN). Domyślnie gdy `ClientCredentialType` jest ustawiony do systemu Windows i usługi jest uruchomiony proces jedno z kont systemu — Usługa lokalna, LocalSystem lub NetworkService.|Ten element określa główną nazwę usługi skojarzone z kontem usługi. Zobacz sekcję protokołu Kerberos i tożsamość [przesłanianie tożsamości usługi na potrzeby uwierzytelniania](../../../../docs/framework/wcf/extending/overriding-the-identity-of-a-service-for-authentication.md).|Dzięki temu, że nazwa SPN i określonego konta systemu Windows, skojarzone z główną nazwę usługi identyfikowania usługi.<br /><br /> Narzędzie Setspn.exe skojarzyć konto komputera dla konta użytkownika usługi.<br /><br /> To ustawienie korzysta z protokołu Kerberos systemu Windows, zabezpieczenia, jeśli usługa jest uruchomiona, zgodnie z jednym z kont systemowych lub przy użyciu konta domeny, które ma nazwę SPN skojarzone z go i komputer jest członkiem domeny w środowisku usługi Active Directory.|  
  
## <a name="specifying-identity-at-the-service"></a>Określanie tożsamości w usłudze  
 Zazwyczaj nie trzeba ustawić tożsamość w usłudze, ponieważ typ tożsamości w metadanych usługi nakazują wybór typu poświadczeń klienta. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]jak zastąpienie lub określ tożsamość usługi, zobacz [przesłanianie tożsamości usługi na potrzeby uwierzytelniania](../../../../docs/framework/wcf/extending/overriding-the-identity-of-a-service-for-authentication.md).  
  
## <a name="using-the-identity-element-in-configuration"></a>Przy użyciu \<tożsamości > Element w konfiguracji  
 Jeśli zmienisz typ poświadczeń klienta w powiązaniu wcześniej wyświetlany `Certificate,` wygenerowanego WSDL zawiera seryjnych Base64 certyfikatu X.509 do wartości tożsamości, jak pokazano w poniższym kodzie. Jest to wartość domyślna dla wszystkich typów poświadczeń klienta innych niż Windows.  
  
  
  
 Możesz zmienić wartość domyślną tożsamość usługi lub zmień typ tożsamości za pomocą `<identity>` element w konfiguracji lub ustawiając tożsamość w kodzie. Poniższy kod konfiguracji ustawia tożsamość systemu (nazw domen DNS) nazwy domeny, z wartością `contoso.com`.  
  
  
  
## <a name="setting-identity-programmatically"></a>Ustawienie programowo tożsamości  
 Usługi nie trzeba jawnie określać tożsamości, ponieważ [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] automatycznie określa go. Jednak [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] służy do określania tożsamości dla punktu końcowego, jeśli jest to wymagane. Poniższy kod dodaje nowy punkt końcowy usługi o określonej tożsamości DNS.  
  
 [!code-csharp[C_Identity#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_identity/cs/source.cs#5)]
 [!code-vb[C_Identity#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_identity/vb/source.vb#5)]  
  
## <a name="specifying-identity-at-the-client"></a>Określanie tożsamości po stronie klienta  
 W czasie projektowania, zwykle wykorzystuje deweloperowi klienta [narzędzie narzędzia metadanych elementu ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) do wygenerowania konfiguracji klienta. Wygenerowano plik konfiguracyjny (przeznaczone do użytku przez klienta) zawiera tożsamości serwera. Na przykład następujący kod jest generowany z usługą, która określa tożsamość DNS, jak pokazano w poprzednim przykładzie. Należy pamiętać, że wartość tożsamości punktu końcowego klienta jest zgodny ze usługi. W takim przypadku, gdy klient odbierze poświadczeń systemu Windows (Kerberos) dla usługi, oczekuje, że wartość na `contoso.com`.  
  
  
  
 Jeśli, zamiast systemu Windows, usługi Określa certyfikat jako typu poświadczeń klienta, a następnie DNS we właściwości certyfikatu powinien być wartością `contoso.com`. (Lub jeśli właściwość DNS jest `null`, nazwa podmiotu certyfikatu musi być `contoso.com`.)  
  
#### <a name="using-a-specific-value-for-identity"></a>Przy użyciu określonej wartości tożsamości  
 Następujący plik konfiguracji klienta pokazuje, jak powinna być określona wartość tożsamości usługi. W poniższym przykładzie klient może komunikować się z dwoma punktami końcowymi. Pierwszy jest odcisk palca certyfikatu i drugiej identyfikowane za pomocą klucza RSA certyfikatu. Oznacza to, że certyfikat, który zawiera tylko publiczny klucz/prywatnej parę kluczy, ale nie jest wystawiony przez zaufany urząd.  
  
  
  
## <a name="identity-checking-at-run-time"></a>Tożsamość sprawdzenie w czasie wykonywania  
 W czasie projektowania deweloperowi klienta określa tożsamość serwera za pomocą jego metadanych. W czasie wykonywania sprawdzić tożsamości jest wykonywane przed wywołaniem żadnych punktów końcowych w usłudze.  
  
 Wartość tożsamości jest powiązany typ uwierzytelniania, określony przez metadane; innymi słowy typ poświadczenia używane przez usługę.  
  
 Jeśli kanał jest skonfigurowany do uwierzytelniania za pomocą wiadomości lub poziomu transportu Secure Sockets Layer (SSL) za pomocą certyfikatów X.509 do uwierzytelniania, obowiązują następujące wartości tożsamości:  
  
-   W SYSTEMIE DNS. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]zapewnia, że certyfikat podczas uzgadniania protokołu SSL zawiera DNS lub `CommonName` atrybutu (CN) wartość określona w tożsamości DNS na kliencie. Należy pamiętać, że te testy są wykonywane dodatkowo do określania okres ważności certyfikatu serwera. Domyślnie [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sprawdza, czy certyfikat serwera jest wystawiony przez zaufany główny urząd.  
  
-   Certyfikat. Podczas uzgadniania protokołu SSL [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] gwarantuje, że zdalny punkt końcowy zapewnia dokładną certyfikatu wybrana w tożsamości.  
  
-   Odwołanie do certyfikatu. Wartość taka sama jak w przypadku certyfikatu.  
  
-   RSA. Podczas uzgadniania protokołu SSL [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] gwarantuje, że zdalny punkt końcowy zapewnia dokładną klucza RSA, określona w tożsamości.  
  
 Jeśli usługa jest uwierzytelniany przy użyciu poziomu transportu lub komunikat protokołu SSL z poświadczeniami systemu Windows do uwierzytelniania i negocjuje poświadczeń, obowiązują następujące wartości tożsamości:  
  
-   W SYSTEMIE DNS. Negocjacji przekazuje usługi SPN, dzięki czemu można sprawdzić nazwę DNS. Nazwa SPN jest w formie `host/<dns name>`.  
  
-   NAZWA SPN. Jawne usługi SPN jest zwracany, na przykład `host/myservice`.  
  
-   NAZWA UPN. Nazwa UPN konta usługi. Nazwa UPN jest w formie `username` @ `domain`. Na przykład, gdy usługa jest uruchomiona na koncie użytkownika, może być `username@contoso.com`.  
  
 Programowo określanie tożsamości (przy użyciu <xref:System.ServiceModel.EndpointAddress.Identity%2A> właściwości) jest opcjonalna. Jeśli tożsamości nie został określony i typu poświadczeń klienta jest systemu Windows, wartością domyślną jest nazwa SPN wartość nazwy hosta część adres punktu końcowego usługi jest poprzedzony prefiksem "host /" literału. Jeśli tożsamości nie został określony i typu poświadczeń klienta jest certyfikat, wartością domyślną jest `Certificate`. Dotyczy to zarówno zabezpieczenia na poziomie komunikatu i transportu.  
  
## <a name="identity-and-custom-bindings"></a>Tożsamość i powiązania niestandardowe  
 Ponieważ tożsamość usługi zależy od typu powiązania, używany, upewnij się, że odpowiednie tożsamości jest narażony, podczas tworzenia niestandardowego powiązania. Na przykład w poniższym przykładzie kodu tożsamości widoczne nie jest zgodny z typem zabezpieczeń, ponieważ tożsamość ładowania początkowego powiązania bezpiecznej konwersacji nie pasuje do tożsamości dla powiązania w punkcie końcowym. Powiązania bezpiecznej konwersacji ustawia tożsamość DNS, podczas gdy <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement> ustawia tożsamość nazwy UPN lub nazwy SPN.  
  
 [!code-csharp[C_Identity#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_identity/cs/source.cs#8)]
 [!code-vb[C_Identity#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_identity/vb/source.vb#8)]  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]stack — wiązanie elementów poprawnie dla niestandardowego powiązania, zobacz [powiązania Creating User-Defined](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md). [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Tworzenie niestandardowego powiązania z <xref:System.ServiceModel.Channels.SecurityBindingElement>, zobacz [porady: Tworzenie elementu SecurityBindingElement dla trybu uwierzytelniania określone](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md).  
  
## <a name="see-also"></a>Zobacz też  
 [Porady: Tworzenie niestandardowego wiązania za pomocą elementu SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [Porady: Tworzenie elementu SecurityBindingElement dla określonego trybu uwierzytelniania](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)  
 [Porady: tworzenie weryfikatora tożsamości niestandardowego klienta](../../../../docs/framework/wcf/extending/how-to-create-a-custom-client-identity-verifier.md)  
 [Wybieranie typu poświadczeń](../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [Praca z certyfikatami](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [Narzędzie do obsługi metadanych elementu ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [Tworzenie powiązań zdefiniowanych przez użytkownika](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md)  
 [Porady: Pobieranie odcisku palca certyfikatu](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)