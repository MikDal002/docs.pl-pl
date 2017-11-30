---
title: Programowanie dla sieci w .NET Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Networking
- Internet
- Internet, .NET Framework Internet services
- Network Resources
ms.assetid: 8d455610-67a0-4fa8-a62f-7747064a9256
caps.latest.revision: "24"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 76b747624a22212fb7b9ba1a6353956a99ed1559
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="network-programming-in-the-net-framework"></a><span data-ttu-id="ee476-102">Programowanie dla sieci w .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ee476-102">Network Programming in the .NET Framework</span></span>
<span data-ttu-id="ee476-103">Środowisko Microsoft .NET Framework oferuje warstwowe, rozszerzalne i zarządzane wdrożenia usług internetowych, które można szybko i łatwo zintegrować ze swoimi aplikacjami.</span><span class="sxs-lookup"><span data-stu-id="ee476-103">The Microsoft .NET Framework provides a layered, extensible, and managed implementation of Internet services that can be quickly and easily integrated into your applications.</span></span> <span data-ttu-id="ee476-104">Aplikacje sieciowe mogą za pomocą podłączanych protokołów automatycznie wykorzystywać nowe protokoły internetowe albo za pośrednictwem zarządzanej implementacji interfejsu gniazd systemu Windows współpracować z siecią na poziomie gniazd.</span><span class="sxs-lookup"><span data-stu-id="ee476-104">Your network applications can build on pluggable protocols to automatically take advantage of new Internet protocols, or they can use a managed implementation of the Windows socket interface to work with the network on the socket level.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ee476-105">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="ee476-105">In This Section</span></span>  
 [<span data-ttu-id="ee476-106">Wprowadzenie podłączany protokołów</span><span class="sxs-lookup"><span data-stu-id="ee476-106">Introducing Pluggable Protocols</span></span>](../../../docs/framework/network-programming/introducing-pluggable-protocols.md)  
 <span data-ttu-id="ee476-107">Opis sposobów uzyskiwania dostępu do zasobu internetowego bez względu na protokół dostępu, którego wymaga zasób.</span><span class="sxs-lookup"><span data-stu-id="ee476-107">Describes how to access an Internet resource without regard to the access protocol that it requires.</span></span>  
  
 [<span data-ttu-id="ee476-108">Żądanie danych</span><span class="sxs-lookup"><span data-stu-id="ee476-108">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)  
 <span data-ttu-id="ee476-109">Wyjaśnienie, jak za pomocą podłączanych protokołów przekazywać i pobierać dane z zasobów internetowych.</span><span class="sxs-lookup"><span data-stu-id="ee476-109">Explains how to use pluggable protocols to upload and download data from Internet resources.</span></span>  
  
 [<span data-ttu-id="ee476-110">Protokoły podłączany programowania</span><span class="sxs-lookup"><span data-stu-id="ee476-110">Programming Pluggable Protocols</span></span>](../../../docs/framework/network-programming/programming-pluggable-protocols.md)  
 <span data-ttu-id="ee476-111">Wyjaśnienie, jak utworzyć pochodne klasy specyficzne dla protokołów w celu zaimplementowania podłączanych protokołów.</span><span class="sxs-lookup"><span data-stu-id="ee476-111">Explains how to derive protocol-specific classes to implement pluggable protocols.</span></span>  
  
 [<span data-ttu-id="ee476-112">Przy użyciu protokołów aplikacji</span><span class="sxs-lookup"><span data-stu-id="ee476-112">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)  
 <span data-ttu-id="ee476-113">Opis zasad programowania aplikacji wykorzystujących protokoły sieciowe, takie jak TCP, UDP i HTTP.</span><span class="sxs-lookup"><span data-stu-id="ee476-113">Describes programming applications that take advantage of network protocols such as TCP, UDP, and HTTP.</span></span>  
  
 [<span data-ttu-id="ee476-114">Protokół internetowy w wersji 6</span><span class="sxs-lookup"><span data-stu-id="ee476-114">Internet Protocol Version 6</span></span>](../../../docs/framework/network-programming/internet-protocol-version-6.md)  
 <span data-ttu-id="ee476-115">Opis zalet protokołu Internet Protocol w wersji 6 (IPv6) w porównaniu z obecną wersją pakietu Internet Protocol (IPv4), a także mechanizmów adresowania, routingu i automatycznej konfiguracji w protokole IPv6 oraz sposobów włączania i wyłączania protokołu.</span><span class="sxs-lookup"><span data-stu-id="ee476-115">Describes the advantages of Internet Protocol version 6 (IPv6) over the current version of the Internet Protocol suite (IPv4), describes IPv6 addressing, routing and auto-configuration, and how to enable and disable IPv6.</span></span>  
  
 [<span data-ttu-id="ee476-116">Konfigurowanie aplikacji internetowych</span><span class="sxs-lookup"><span data-stu-id="ee476-116">Configuring Internet Applications</span></span>](../../../docs/framework/network-programming/configuring-internet-applications.md)  
 <span data-ttu-id="ee476-117">Wyjaśnienie zasad konfigurowania aplikacji internetowych za pomocą plików konfiguracyjnych środowiska .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ee476-117">Explains how to use the .NET Framework configuration files to configure Internet applications.</span></span>  
  
 [<span data-ttu-id="ee476-118">Śledzenie sieci w programie .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ee476-118">Network Tracing in the .NET Framework</span></span>](../../../docs/framework/network-programming/network-tracing.md)  
 <span data-ttu-id="ee476-119">Wyjaśnienie, jak za pomocą mechanizmu śledzenia sieci uzyskiwać informacje o wywołaniach metod i ruchu sieciowym generowanym przez zarządzaną aplikację.</span><span class="sxs-lookup"><span data-stu-id="ee476-119">Explains how to use network tracing to get information about method invocations and network traffic generated by a managed application.</span></span>  
  
 [<span data-ttu-id="ee476-120">Zarządzanie pamięci podręcznej dla aplikacji sieciowych</span><span class="sxs-lookup"><span data-stu-id="ee476-120">Cache Management for Network Applications</span></span>](../../../docs/framework/network-programming/cache-management-for-network-applications.md)  
 <span data-ttu-id="ee476-121">Informacje dotyczące używania buforowania dla aplikacji, które używają <xref:System.Net.WebClient?displayProperty=nameWithType>, <xref:System.Net.WebRequest?displayProperty=nameWithType>, i <xref:System.Net.HttpWebRequest?displayProperty=nameWithType> klasy.</span><span class="sxs-lookup"><span data-stu-id="ee476-121">Describes how to use caching for applications that use the <xref:System.Net.WebClient?displayProperty=nameWithType>, <xref:System.Net.WebRequest?displayProperty=nameWithType>, and <xref:System.Net.HttpWebRequest?displayProperty=nameWithType> classes.</span></span>  
  
 [<span data-ttu-id="ee476-122">Zabezpieczenia w programowaniu usługi sieciowej</span><span class="sxs-lookup"><span data-stu-id="ee476-122">Security in Network Programming</span></span>](../../../docs/framework/network-programming/security-in-network-programming.md)  
 <span data-ttu-id="ee476-123">Opis używania standardowych technik zabezpieczania i uwierzytelniania w Internecie.</span><span class="sxs-lookup"><span data-stu-id="ee476-123">Describes how to use standard Internet security and authentication techniques.</span></span>  
  
 [<span data-ttu-id="ee476-124">Najlepsze rozwiązania dotyczące klas System.Net</span><span class="sxs-lookup"><span data-stu-id="ee476-124">Best Practices for System.Net Classes</span></span>](../../../docs/framework/network-programming/best-practices-for-system-net-classes.md)  
 <span data-ttu-id="ee476-125">Porady i wskazówki dotyczące optymalnego wykorzystania możliwości aplikacji internetowych.</span><span class="sxs-lookup"><span data-stu-id="ee476-125">Provides tips and tricks for getting the most out of your Internet applications.</span></span>  
  
 [<span data-ttu-id="ee476-126">Dostęp do Internetu za pośrednictwem serwera Proxy</span><span class="sxs-lookup"><span data-stu-id="ee476-126">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)  
 <span data-ttu-id="ee476-127">Opis konfigurowania serwerów proxy.</span><span class="sxs-lookup"><span data-stu-id="ee476-127">Describes how to configure proxies.</span></span>  
  
 [<span data-ttu-id="ee476-128">NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="ee476-128">NetworkInformation</span></span>](../../../docs/framework/network-programming/networkinformation.md)  
 <span data-ttu-id="ee476-129">Opisano sposób zebrać informacje dotyczące zdarzenia sieci, zmiany statystyk i właściwości oraz wyjaśniono również sposób określania, czy zdalny host jest dostępny, za pomocą <xref:System.Net.NetworkInformation.Ping?displayProperty=nameWithType> klasy.</span><span class="sxs-lookup"><span data-stu-id="ee476-129">Describes how to gather information about network events, changes, statistics, and properties and also explains how to determine whether a remote host is reachable by using the <xref:System.Net.NetworkInformation.Ping?displayProperty=nameWithType> class.</span></span>  
  
 [<span data-ttu-id="ee476-130">Zmiany w przestrzeni nazw System.Uri w wersji 2.0</span><span class="sxs-lookup"><span data-stu-id="ee476-130">Changes to the System.Uri namespace in Version 2.0</span></span>](../../../docs/framework/network-programming/changes-to-the-system-uri-namespace-in-version-2-0.md)  
 <span data-ttu-id="ee476-131">W tym artykule opisano kilka zmian <xref:System.Uri?displayProperty=nameWithType> klasy w stałej nieprawidłowe zachowanie w wersji 2.0, zwiększają użyteczność i zwiększyć bezpieczeństwo.</span><span class="sxs-lookup"><span data-stu-id="ee476-131">Describes several changes made to the <xref:System.Uri?displayProperty=nameWithType> class in Version 2.0 to fixed incorrect behavior, enhance usability, and enhance security.</span></span>  
  
 [<span data-ttu-id="ee476-132">Obsługa identyfikatora zasobu międzynarodowe w System.Uri</span><span class="sxs-lookup"><span data-stu-id="ee476-132">International Resource Identifier Support in System.Uri</span></span>](../../../docs/framework/network-programming/international-resource-identifier-support-in-system-uri.md)  
 <span data-ttu-id="ee476-133">Opisuje rozszerzenia <xref:System.Uri?displayProperty=nameWithType> obsługuje klasy w wersji 3.5, 3.0 z dodatkiem SP1 i 2.0 z dodatkiem SP1 międzynarodowej identyfikator zasobów (IRI) oraz międzynarodowych nazw domen (IDN).</span><span class="sxs-lookup"><span data-stu-id="ee476-133">Describes enhancements to the <xref:System.Uri?displayProperty=nameWithType> class in Version 3.5, 3.0 SP1, and 2.0 SP1 for International Resource Identifier (IRI) and Internationalized Domain Name (IDN) support.</span></span>  
  
 [<span data-ttu-id="ee476-134">Ulepszenia wydajności gniazda w wersji 3.5</span><span class="sxs-lookup"><span data-stu-id="ee476-134">Socket Performance Enhancements in Version 3.5</span></span>](../../../docs/framework/network-programming/socket-performance-enhancements-in-version-3-5.md)  
 <span data-ttu-id="ee476-135">Opisuje zestaw rozszerzeń <xref:System.Net.Sockets.Socket?displayProperty=nameWithType> klasy w wersji 3.5, 3.0 z dodatkiem SP1 i podaj alternatywną wzorca asynchronicznego, które mogą być używane przez aplikacje specjalistyczne gniazda wysokiej wydajności 2.0 z dodatkiem SP1.</span><span class="sxs-lookup"><span data-stu-id="ee476-135">Describes a set of enhancements to the <xref:System.Net.Sockets.Socket?displayProperty=nameWithType> class in Version 3.5, 3.0 SP1, and 2.0 SP1 that provide an alternative asynchronous pattern that can be used by specialized high-performance socket applications.</span></span>  
  
 [<span data-ttu-id="ee476-136">Protokół PNRP</span><span class="sxs-lookup"><span data-stu-id="ee476-136">Peer Name Resolution Protocol</span></span>](../../../docs/framework/network-programming/peer-name-resolution-protocol.md)  
 <span data-ttu-id="ee476-137">Opis mechanizmu dodanego w wersji 3.5 do obsługi protokołu PNRP (Peer Name Resolution Protocol), bezserwerowego i dynamicznego rejestrowania nazw oraz protokołu rozpoznawania nazw.</span><span class="sxs-lookup"><span data-stu-id="ee476-137">Describes support added in Version 3.5 to support the Peer Name Resolution Protocol (PNRP), a serverless and dynamic name registration and name resolution protocol.</span></span> <span data-ttu-id="ee476-138">Te nowe funkcje są obsługiwane przez <xref:System.Net.PeerToPeer?displayProperty=nameWithType> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="ee476-138">These new features are supported by the <xref:System.Net.PeerToPeer?displayProperty=nameWithType> namespace.</span></span>  
  
 [<span data-ttu-id="ee476-139">Współpraca peer-to-Peer</span><span class="sxs-lookup"><span data-stu-id="ee476-139">Peer-to-Peer Collaboration</span></span>](../../../docs/framework/network-programming/peer-to-peer-collaboration.md)  
 <span data-ttu-id="ee476-140">Opis mechanizmu dodanego w wersji 3.5 do obsługi współpracy między równorzędnymi urządzeniami w oparciu o protokół PNRP.</span><span class="sxs-lookup"><span data-stu-id="ee476-140">Describes support added in Version 3.5 to support the Peer-to-Peer Collaboration that builds on PNRP.</span></span> <span data-ttu-id="ee476-141">Te nowe funkcje są obsługiwane przez <xref:System.Net.PeerToPeer.Collaboration?displayProperty=nameWithType> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="ee476-141">These new features are supported by the <xref:System.Net.PeerToPeer.Collaboration?displayProperty=nameWithType> namespace.</span></span>  
  
 [<span data-ttu-id="ee476-142">Zmiany do uwierzytelniania NTLM dla HttpWebRequest w wersji 3.5 z dodatkiem SP1</span><span class="sxs-lookup"><span data-stu-id="ee476-142">Changes to NTLM authentication for HttpWebRequest in Version 3.5 SP1</span></span>](../../../docs/framework/network-programming/changes-to-ntlm-authentication-for-httpwebrequest-in-version-3-5-sp1.md)  
 <span data-ttu-id="ee476-143">W tym artykule opisano zmiany zabezpieczeń wprowadzone w wersji 3.5 z dodatkiem SP1, które mają wpływ na sposób zintegrowane z systemem Windows uwierzytelnianie jest obsługiwane przez <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>, <xref:System.Net.HttpListener?displayProperty=nameWithType>, <xref:System.Net.Security.NegotiateStream?displayProperty=nameWithType>, i powiązanych klas w przestrzeni nazw System.Net.</span><span class="sxs-lookup"><span data-stu-id="ee476-143">Describes security changes made in Version 3.5 SP1 that affect how integrated Windows authentication is handled by the <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>, <xref:System.Net.HttpListener?displayProperty=nameWithType>, <xref:System.Net.Security.NegotiateStream?displayProperty=nameWithType>, and related classes in the System.Net namespace.</span></span>  
  
 [<span data-ttu-id="ee476-144">Zintegrowane uwierzytelnianie systemu Windows z ochrony rozszerzonej</span><span class="sxs-lookup"><span data-stu-id="ee476-144">Integrated Windows Authentication with Extended Protection</span></span>](../../../docs/framework/network-programming/integrated-windows-authentication-with-extended-protection.md)  
 <span data-ttu-id="ee476-145">Opisuje rozszerzenia rozszerzonej ochrony, które mają wpływ na sposób zintegrowane uwierzytelnianie systemu Windows jest obsługiwany przez <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>, <xref:System.Net.HttpListener?displayProperty=nameWithType>, <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>, <xref:System.Net.Security.SslStream?displayProperty=nameWithType>, <xref:System.Net.Security.NegotiateStream?displayProperty=nameWithType>, i powiązanych klas w <xref:System.Net?displayProperty=nameWithType> i pokrewne przestrzenie nazw.</span><span class="sxs-lookup"><span data-stu-id="ee476-145">Describes enhancements for extended protection that affect how integrated Windows authentication is handled by the <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>, <xref:System.Net.HttpListener?displayProperty=nameWithType>, <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>, <xref:System.Net.Security.SslStream?displayProperty=nameWithType>, <xref:System.Net.Security.NegotiateStream?displayProperty=nameWithType>, and related classes in the <xref:System.Net?displayProperty=nameWithType> and related namespaces.</span></span>  
  
 [<span data-ttu-id="ee476-146">Przechodzenie translatora adresów Sieciowych przy użyciu protokołu IPv6 i Teredo</span><span class="sxs-lookup"><span data-stu-id="ee476-146">NAT Traversal using IPv6 and Teredo</span></span>](../../../docs/framework/network-programming/nat-traversal-using-ipv6-and-teredo.md)  
 <span data-ttu-id="ee476-147">Opisuje rozszerzenia dodane do <xref:System.Net?displayProperty=nameWithType>, <xref:System.Net.NetworkInformation?displayProperty=nameWithType>, i <xref:System.Net.Sockets?displayProperty=nameWithType> obszarów nazw do obsługi przechodzenia translatora adresów Sieciowych przy użyciu protokołu IPv6 i Teredo.</span><span class="sxs-lookup"><span data-stu-id="ee476-147">Describes enhancements added to the <xref:System.Net?displayProperty=nameWithType>, <xref:System.Net.NetworkInformation?displayProperty=nameWithType>, and <xref:System.Net.Sockets?displayProperty=nameWithType> namespaces to support NAT traversal using IPv6 and Teredo.</span></span>  
  
 [<span data-ttu-id="ee476-148">Izolacja sieci dla aplikacji ze Sklepu Windows</span><span class="sxs-lookup"><span data-stu-id="ee476-148">Network Isolation for Windows Store Apps</span></span>](../../../docs/framework/network-programming/network-isolation-for-windows-store-apps.md)  
 <span data-ttu-id="ee476-149">Opis wpływu izolacji sieci podczas klas w <xref:System.Net>, <xref:System.Net.Http>, i <xref:System.Net.Http.Headers> przestrzenie nazw są używane w [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] aplikacji.</span><span class="sxs-lookup"><span data-stu-id="ee476-149">Describes the impact of network isolation when classes in the <xref:System.Net>, <xref:System.Net.Http>, and <xref:System.Net.Http.Headers> namespaces are used in [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span>  
  
 [<span data-ttu-id="ee476-150">Przykłady programowania w języku sieci</span><span class="sxs-lookup"><span data-stu-id="ee476-150">Network Programming Samples</span></span>](../../../docs/framework/network-programming/network-programming-samples.md)  
 <span data-ttu-id="ee476-151">Przykłady programowania, korzystających z klas w sieci łącza do pobrania <xref:System.Net>, <xref:System.Net.Cache>, <xref:System.Net.Configuration>, <xref:System.Net.Mail>, <xref:System.Net.Mime>, <xref:System.Net.NetworkInformation>, <xref:System.Net.PeerToPeer>, <xref:System.Net.Security>, <xref:System.Net.Sockets> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="ee476-151">Links to downloadable network programming samples that use classes in the <xref:System.Net>, <xref:System.Net.Cache>, <xref:System.Net.Configuration>, <xref:System.Net.Mail>, <xref:System.Net.Mime>, <xref:System.Net.NetworkInformation>, <xref:System.Net.PeerToPeer>, <xref:System.Net.Security>, <xref:System.Net.Sockets> namespaces.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ee476-152">Tematy pomocy</span><span class="sxs-lookup"><span data-stu-id="ee476-152">Reference</span></span>  
 <xref:System.Net?displayProperty=nameWithType>  
 <span data-ttu-id="ee476-153">Prosty interfejs programistyczny dla wielu protokołów używanych obecnie w sieciach.</span><span class="sxs-lookup"><span data-stu-id="ee476-153">Provides a simple programming interface for many of the protocols used on networks today.</span></span> <span data-ttu-id="ee476-154"><xref:System.Net.WebRequest?displayProperty=nameWithType> i <xref:System.Net.WebResponse?displayProperty=nameWithType> podstawą podłączany protokołów występują następujące klasy w tej przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="ee476-154">The <xref:System.Net.WebRequest?displayProperty=nameWithType> and <xref:System.Net.WebResponse?displayProperty=nameWithType> classes in this namespace are the basis for pluggable protocols.</span></span>  
  
 <xref:System.Net.Cache?displayProperty=nameWithType>  
 <span data-ttu-id="ee476-155">Określa typy oraz wyliczenia używane do definiowania zasad buforowania zasobów uzyskany przy użyciu <xref:System.Net.WebRequest?displayProperty=nameWithType> i <xref:System.Net.HttpWebRequest?displayProperty=nameWithType> klasy.</span><span class="sxs-lookup"><span data-stu-id="ee476-155">Defines the types and enumerations used to define cache policies for resources obtained using the <xref:System.Net.WebRequest?displayProperty=nameWithType> and <xref:System.Net.HttpWebRequest?displayProperty=nameWithType> classes.</span></span>  
  
 <xref:System.Net.Configuration?displayProperty=nameWithType>  
 <span data-ttu-id="ee476-156">Klasy, za pomocą których aplikacje programistycznie uzyskują dostęp i aktualizują ustawienia konfiguracyjne w przestrzeni nazw System.Net.</span><span class="sxs-lookup"><span data-stu-id="ee476-156">Classes that applications use to programmatically access and update configuration settings for the System.Net namespaces.</span></span>  
  
 <xref:System.Net.Http?displayProperty=nameWithType>  
 <span data-ttu-id="ee476-157">Klasy tworzące interfejs programistyczny dla nowoczesnych aplikacji wykorzystujących protokół HTTP.</span><span class="sxs-lookup"><span data-stu-id="ee476-157">Classes that provides a programming interface for modern HTTP applications.</span></span>  
  
 <xref:System.Net.Http.Headers?displayProperty=nameWithType>  
 <span data-ttu-id="ee476-158">Zapewnia obsługę kolekcje nagłówków HTTP używanych przez <xref:System.Net.Http?displayProperty=nameWithType> przestrzeni nazw</span><span class="sxs-lookup"><span data-stu-id="ee476-158">Provides support for collections of HTTP headers used by the <xref:System.Net.Http?displayProperty=nameWithType> namespace</span></span>  
  
 <xref:System.Net.Mail?displayProperty=nameWithType>  
 <span data-ttu-id="ee476-159">Klasy do redagowania i wysyłania poczty przy użyciu protokołu SMTP.</span><span class="sxs-lookup"><span data-stu-id="ee476-159">Classes to compose and send mail using the SMTP protocol.</span></span>  
  
 <xref:System.Net.Mime?displayProperty=nameWithType>  
 <span data-ttu-id="ee476-160">Określa typy, które są używane do reprezentowania nagłówków poczty programu Exchange MIME (Multipurpose Internet) używany przez klas w <xref:System.Net.Mail?displayProperty=nameWithType> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="ee476-160">Defines types that are used to represent Multipurpose Internet Mail Exchange (MIME) headers used by classes in the <xref:System.Net.Mail?displayProperty=nameWithType> namespace.</span></span>  
  
 <xref:System.Net.NetworkInformation?displayProperty=nameWithType>  
 <span data-ttu-id="ee476-161">Klasy umożliwiające programistyczne gromadzenie informacji o zdarzeniach, zmianach, statystykach i właściwościach sieci.</span><span class="sxs-lookup"><span data-stu-id="ee476-161">Classes to programmatically gather information about network events, changes, statistics, and properties.</span></span>  
  
 <xref:System.Net.PeerToPeer?displayProperty=nameWithType>  
 <span data-ttu-id="ee476-162">Umożliwia zarządzaną implementację protokołu PNRP (Peer Name Resolution Protocol) dla programistów.</span><span class="sxs-lookup"><span data-stu-id="ee476-162">Provides a managed implementation of the Peer Name Resolution Protocol (PNRP) for developers.</span></span>  
  
 <xref:System.Net.PeerToPeer.Collaboration?displayProperty=nameWithType>  
 <span data-ttu-id="ee476-163">Umożliwia zarządzaną implementację interfejsu współpracy elementów równorzędnych dla programistów.</span><span class="sxs-lookup"><span data-stu-id="ee476-163">Provides a managed implementation of the Peer-to-Peer Collaboration interface for developers.</span></span>  
  
 <xref:System.Net.Security?displayProperty=nameWithType>  
 <span data-ttu-id="ee476-164">Klasy zapewniające strumienie sieciowe umożliwiające bezpieczną komunikację między hostami.</span><span class="sxs-lookup"><span data-stu-id="ee476-164">Classes to provide network streams for secure communications between hosts.</span></span>  
  
 <xref:System.Net.Sockets?displayProperty=nameWithType>  
 <span data-ttu-id="ee476-165">Umożliwia zarządzaną implementację interfejsu Windows Sockets (Winsock) dla programistów, którzy muszą wprowadzić mechanizm kontroli dostępu do sieci.</span><span class="sxs-lookup"><span data-stu-id="ee476-165">Provides a managed implementation of the Windows Sockets (Winsock) interface for developers who need to help control access to the network.</span></span>  
  
 <xref:System.Net.WebSockets?displayProperty=nameWithType>  
 <span data-ttu-id="ee476-166">Umożliwia zarządzaną implementację interfejsu WebSocket dla programistów.</span><span class="sxs-lookup"><span data-stu-id="ee476-166">Provides a managed implementation of the WebSocket interface for developers.</span></span>  
  
 <xref:System.Uri?displayProperty=nameWithType>  
 <span data-ttu-id="ee476-167">Umożliwia reprezentowanie obiektów za pomocą jednolitych identyfikatorów zasobów (URI) oraz łatwy dostęp do elementów identyfikatorów URI.</span><span class="sxs-lookup"><span data-stu-id="ee476-167">Provides an object representation of a uniform resource identifier (URI) and easy access to the parts of the URI.</span></span>  
  
 <xref:System.Security.Authentication.ExtendedProtection?displayProperty=nameWithType>  
 <span data-ttu-id="ee476-168">Umożliwia obsługę uwierzytelniania przy użyciu mechanizmu rozszerzonej ochrony aplikacji.</span><span class="sxs-lookup"><span data-stu-id="ee476-168">Provides support for authentication using extended protection for applications.</span></span>  
  
 <xref:System.Security.Authentication.ExtendedProtection.Configuration?displayProperty=nameWithType>  
 <span data-ttu-id="ee476-169">Umożliwia konfigurowanie uwierzytelniania przy użyciu mechanizmu rozszerzonej ochrony aplikacji.</span><span class="sxs-lookup"><span data-stu-id="ee476-169">Provides support for configuration of authentication using extended protection for applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee476-170">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ee476-170">See Also</span></span>  
 [<span data-ttu-id="ee476-171">Sieci programowania — tematy porad</span><span class="sxs-lookup"><span data-stu-id="ee476-171">Network Programming How-to Topics</span></span>](../../../docs/framework/network-programming/network-programming-how-to-topics.md)  
 [<span data-ttu-id="ee476-172">Przykłady programowania w języku sieci</span><span class="sxs-lookup"><span data-stu-id="ee476-172">Network Programming Samples</span></span>](../../../docs/framework/network-programming/network-programming-samples.md)  
 [<span data-ttu-id="ee476-173">Przykłady sieci dla platformy .NET w galerii kodu MSDN</span><span class="sxs-lookup"><span data-stu-id="ee476-173">Networking Samples for .NET on MSDN Code Gallery</span></span>](http://code.msdn.microsoft.com/Wiki/View.aspx?ProjectName=nclsamples)  
 [<span data-ttu-id="ee476-174">Przykładowe HttpClient</span><span class="sxs-lookup"><span data-stu-id="ee476-174">HttpClient Sample</span></span>](http://go.microsoft.com/fwlink/?LinkId=242550)