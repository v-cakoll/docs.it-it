---
title: 'Procedura: Creare un socket'
description: Informazioni su come inizializzare un socket per comunicare con i dispositivi remoti. Usare la classe Socket per specificare la famiglia di indirizzi, il tipo di socket e il tipo di protocollo.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- Networking
- sending data, sockets
- data requests, sockets
- requesting data from Internet, sockets
- Socket class, creating sockets
- Network Resources
- receiving data, sockets
- protocols, sockets
- Internet, sockets
- sockets, creating
ms.assetid: c64a049c-5981-43bc-a2dc-1851473589c7
ms.openlocfilehash: 1d56ddea721b54192a7dd47d144b6c41bbb9a5d7
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502548"
---
# <a name="how-to-create-a-socket"></a>Procedura: Creare un socket
Prima di usare un socket per comunicare con dispositivi remoti, è necessario inizializzare il socket con informazioni su protocollo e indirizzo di rete. Il costruttore per la classe <xref:System.Net.Sockets.Socket> dispone di parametri che specificano la famiglia di indirizzi, il tipo di socket e il tipo di protocollo usato per stabilire connessioni.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente crea un socket che può essere usato per comunicare in una rete basata su TCP/IP, come Internet.  
  
```csharp  
Socket s = new Socket(AddressFamily.InterNetwork,
   SocketType.Stream, ProtocolType.Tcp);  
```  
  
```vb  
Dim s as New Socket(AddressFamily.InterNetwork, _  
   SocketType.Stream, ProtocolType.Tcp)  
```  
  
 Per usare UDP anziché TCP, modificare il tipo di protocollo, come nell'esempio seguente:  
  
```csharp  
Socket s = new Socket(AddressFamily.InterNetwork,
   SocketType.Dgram, ProtocolType.Udp);  
```  
  
```vb  
Dim s as New Socket(AddressFamily.InterNetwork, _  
   SocketType.Dgram, ProtocolType.Udp)  
```  
  
 L'enumerazione <xref:System.Net.Sockets.AddressFamily> specifica le famiglie di indirizzi standard usate dalla classe **Socket** per risolvere gli indirizzi di rete (ad esempio, il membro **AddressFamily.InterNetwork** specifica la famiglia di indirizzi IP versione 4).  
  
 L'enumerazione <xref:System.Net.Sockets.SocketType> specifica il tipo di socket (ad esempio, il membro **SocketType.Stream** indica un socket standard per l'invio e la ricezione di dati con il controllo di flusso).  
  
 L'enumerazione <xref:System.Net.Sockets.ProtocolType> specifica il protocollo di rete da usare durante la comunicazione sul **Socket** (ad esempio, **ProtocolType.Tcp** indica che il socket usa TCP e **ProtocolType.Udp** indica che il socket usa il protocollo UDP).  
  
 Dopo la creazione di un **Socket** è possibile avviare una connessione a un endpoint remoto o ricevere connessioni da dispositivi remoti.  
  
## <a name="see-also"></a>Vedere anche

- [Uso di socket client](using-client-sockets.md)
- [Attesa con socket](listening-with-sockets.md)
