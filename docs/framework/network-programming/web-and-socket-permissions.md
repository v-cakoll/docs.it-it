---
title: Autorizzazioni Web e socket
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Networking
- positions [.NET Framework], accepting
- sockets, permissions
- network, permissions
- Internet, permissions
- Network Resources
- SocketPermission class, about SocketPermission class
- positions [.NET Framework], connecting
- WebPermission class, about WebPermission class
- permissions [.NET Framework], sockets
- security [.NET Framework], Internet
- positions [.NET Framework], granting
ms.assetid: d51ad8cb-03ae-4a51-bfcd-cfcf6b98afa9
caps.latest.revision: 9
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 6071c69799cf289ad0ecf163dc2de038efefecc1
ms.contentlocale: it-it
ms.lasthandoff: 08/21/2017

---
# <a name="web-and-socket-permissions"></a>Autorizzazioni Web e socket
La sicurezza Internet per le applicazioni che usano lo spazio dei nomi <xref:System.Net> viene fornita dalle classi <xref:System.Net.WebPermission> e <xref:System.Net.SocketPermission>. La classe **WebPermission** controlla il diritto di un'applicazione di richiedere i dati da un URI o di servire un URI in Internet. La classe **SocketPermission** controlla il diritto di un'applicazione di usare un oggetto <xref:System.Net.Sockets.Socket> per accettare i dati su una porta locale o di contattare i dispositivi remoti usando un protocollo di trasporto in un altro indirizzo, in base all'host, al numero di porta e al protocollo di trasporto del socket.  
  
 La classe di autorizzazioni da usare dipende dal tipo di applicazione. Le applicazioni che usano <xref:System.Net.WebRequest> e i relativi discendenti devono usare la classe **WebPermission** per gestire le autorizzazioni. Le applicazioni che usano l'accesso a livello di socket devono usare la classe **SocketPermission** per gestire le autorizzazioni.  
  
 **WebPermission** e **SocketPermission** definiscono due autorizzazioni: accettazione e connessione. L'autorizzazione di accettazione concede all'applicazione il diritto di rispondere a una connessione in ingresso da un'altra entità. L'autorizzazione di connessione concede all'applicazione il diritto di avviare una connessione a un'altra entità.  
  
 Per le istanze di **SocketPermission**, autorizzazione di accettazione significa che un'applicazione può accettare le connessioni in ingresso su un indirizzo di trasporto locale, mentre autorizzazione di connessione significa che un'applicazione può connettersi a un indirizzo di trasporto remoto (o locale).  
  
 Per le istanze di **WebPermission**, autorizzazione di accettazione significa che un'applicazione può esportare l'URI controllato da **WebPermission**, mentre autorizzazione di connessione significa che un'applicazione può accedere a tale URI (che sia locale o remoto).  
  
## <a name="see-also"></a>Vedere anche  
 [Sicurezza](../../../docs/standard/security/index.md)   
 [Sicurezza nella programmazione di rete](../../../docs/framework/network-programming/security-in-network-programming.md)

