---
title: Narzędzie klienta usługi danych WCF (DataSvcUtil.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, generating client data classes
- WCF Data Services, client library
- WCF Data Services, consuming
ms.assetid: 9d0af606-929b-4c03-b307-3ef5f705afce
ms.openlocfilehash: 3442142eb249d04dabba455a57f02f3cdc7f4b91
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54731754"
---
# <a name="wcf-data-service-client-utility-datasvcutilexe"></a>Narzędzie klienta usługi danych WCF (DataSvcUtil.exe)

DataSvcUtil.exe jest narzędziem wiersza polecenia, udostępniane przez usługi danych WCF, który wykorzystuje [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] źródła danych i generowanie klas usługi danych klienta, które są wymagane do uzyskania dostępu do usługi danych z aplikacji klienckiej .NET Framework. To narzędzie można wygenerować klas danych, korzystając z następujących źródeł metadanych:

-   Głównym identyfikatorem URI usługi danych. Narzędzie żądań dokumentu metadanych usługi, dla którego w tym artykule opisano model danych udostępnianych przez usługę danych. Aby uzyskać więcej informacji, zobacz [OData: Dokument metadanych usługi](https://go.microsoft.com/fwlink/?LinkId=186070).

-   Plik modelu danych (.csdl) zdefiniowane z użyciem języka definicji schematu koncepcyjnego (CSDL), zgodnie z definicją w [ \[MC CSDL\]: Koncepcyjny formatu pliku definicji schematu](https://go.microsoft.com/fwlink/?LinkID=159072) specyfikacji.

-   Plik edmx utworzone za pomocą narzędzia modelu Entity Data Model, które są dostarczane z programem Entity Framework. Aby uzyskać więcej informacji, zobacz [ \[MC EDMX\]: Model Entity Data Model do formatu pakietu usług danych](https://go.microsoft.com/fwlink/?LinkID=178833) specyfikacji.

Aby uzyskać więcej informacji, zobacz [jak: Ręczne Generowanie klas usługi danych klienta](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md).

Narzędzie DataSvcUtil.exe jest instalowane w [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] katalogu. W wielu przypadkach znajduje się on w *C:\Windows\Microsoft.NET\Framework\v4.0*. W 64-bitowych systemach znajduje się on w *C:\Windows\Microsoft.NET\Framework64\v4.0*. Można również przejść DataSvcUtil.exe narzędzie z wiersza polecenia dla deweloperów programu Visual Studio.

## <a name="syntax"></a>Składnia

```
datasvcutil /out:file [/in:file | /uri:serviceuri] [/dataservicecollection] [/language:devlang] [/nologo] [/version:ver] [/help]
```

### <a name="parameters"></a>Parametry

|Opcja|Opis|
|------------|-----------------|
|`/dataservicecollection`|Określa, że zostanie również wygenerowany kod wymagany do utworzenia powiązania obiektów do kontrolek.|
|`/help`<br /><br /> —lub—<br /><br /> `/?`|Wyświetla składnię polecenia i opcje narzędzia.|
|`/in:` *\<file>*|Określa plik .csdl lub edmx lub katalog, w którym znajduje się plik.|
|`/language:`[VB&#124;CSharp]|Określa język dla plików kodu wygenerowanego źródła. Wartością domyślną języka C#.|
|`/nologo`|Pomija komunikat o prawach autorskich były wyświetlane.|
|`/out:` *\<file>*|Określa nazwę pliku kodu źródłowego, który zawiera klas usługi danych wygenerowanego klienta.|
|`/uri:` *\<string>*|Identyfikator URI źródła danych OData.|
|`/version:`[1.0&#124;2.0]|Określa najwyższy numer wersji zaakceptowanych OData. Wersja jest określana na podstawie `DataServiceVersion` atrybutu elementu usługi danych w metadanych usługi zwracanych danych. Aby uzyskać więcej informacji, zobacz [przechowywanie wersji usługi danych](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md). Po określeniu `/dataservicecollection` parametru należy także określić `/version:2.0` umożliwiające powiązanie danych.|

## <a name="see-also"></a>Zobacz także

- [Generowanie biblioteki klienta usługi danych](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)
- [Instrukcje: Dodaj odwołanie do usługi danych](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)
