---
title: TCP-UDP
ms.date: 03/30/2017
helpviewer_keywords:
- protocols, TCP/UDP
- network resources, TCP/UDP
- sending data, TCP/UDP
- TCP/UDP
- TcpClient class, about TcpClient class
- application protocols, TCP/UDP
- receiving data, TCP/UDP
- TcpListener class, about TcpListener class
- Socket class, about Socket class
- UDP
- data requests, TCP/UDP
- requesting data from Internet, TCP/UDP
- Internet, TCP/UDP
ms.assetid: df29b4b0-49e8-4923-82b9-13150dfc40f5
ms.openlocfilehash: 261350349497168e3f41b2f6887838d167c3e977
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54692548"
---
# <a name="tcp-udp"></a>TCP-UDP
Aplikacje mogą używać usług Transmission Control Protocol (TCP) i protokołu UDP (User Datagram) za pomocą <xref:System.Net.Sockets.TcpClient>, <xref:System.Net.Sockets.TcpListener>, i <xref:System.Net.Sockets.UdpClient> klasy. W ramach tych zajęć protokołu są wbudowane w górnej części <xref:System.Net.Sockets.Socket?displayProperty=nameWithType> klasy i zadbać o szczegółach transferu danych.  
  
 Klasy protokołu Użyj metod synchronicznych **gniazda** klasy w celu zapewnienia niezwykle proste dostępu do usług sieciowych bez konieczności utrzymywania informacji o stanie lub wiedząc, szczegółowe informacje o konfigurowaniu gniazda specyficzne dla protokołu. Aby używać asynchronicznych **gniazda** metody, można użyć metod asynchronicznych, dostarczone przez <xref:System.Net.Sockets.NetworkStream> klasy. Dostępu do funkcji z **gniazda** klasy nie jest udostępniany przez protokół klasy, należy użyć **gniazda** klasy.  
  
 **TcpClient** i **TcpListener** reprezentują sieci za pomocą funkcji **Strumień NetworkStream** klasy. Możesz użyć <xref:System.Net.Sockets.TcpClient.GetStream%2A> metodę, aby zwrócić strumień sieci, a następnie wywołaj strumienia <xref:System.Net.Sockets.NetworkStream.Read%2A> i <xref:System.Net.Sockets.NetworkStream.Write%2A> metody. **Strumień NetworkStream** nie jest właścicielem gniazdo podstawowej z klas protokołu, zamykając go nie ma wpływu na gniazda.  
  
 **UdpClient** klasy wykorzystuje tablicę bajtów zawierającą UDP datagram. Możesz użyć <xref:System.Net.Sockets.UdpClient.Send%2A> metodę, aby wysyłać dane do sieci i <xref:System.Net.Sockets.UdpClient.Receive%2A> metodę, aby otrzymywać datagram przychodzących.  
  
## <a name="see-also"></a>Zobacz także
- [Stosowanie usług TCP](../../../docs/framework/network-programming/using-tcp-services.md)
- [Stosowanie usług UDP](../../../docs/framework/network-programming/using-udp-services.md)
- [Stosowanie strumieni w sieci](../../../docs/framework/network-programming/using-streams-on-the-network.md)
- [Używanie asynchronicznego gniazda serwera](../../../docs/framework/network-programming/using-an-asynchronous-server-socket.md)
- [Używanie asynchronicznego gniazda klienta](../../../docs/framework/network-programming/using-an-asynchronous-client-socket.md)
- [Korzystanie z protokołów aplikacji](../../../docs/framework/network-programming/using-application-protocols.md)
