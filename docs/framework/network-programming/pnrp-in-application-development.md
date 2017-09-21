---
title: PNRP nello sviluppo di applicazioni
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
ms.assetid: 265615d6-4423-4b5d-8626-752e456f4f4e
caps.latest.revision: 6
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9f20dd62b5b872b932639a10df1e1636798ba963
ms.contentlocale: it-it
ms.lasthandoff: 08/21/2017

---
# <a name="pnrp-in-application-development"></a>PNRP nello sviluppo di applicazioni
In Windows Vista, le applicazioni di rete possono accedere alle funzioni di risoluzione e pubblicazione dei nomi tramite un'API PNRP semplificata.  
  
## <a name="implementing-the-peer-name-resolution-protocol"></a>Implementazione del protocollo PNRP (Peer Name Resolution Protocol)  
 Con l'API PNRP semplificata, non vengono specificati in modo esplicito i cloud per registrare il nome e gli indirizzi, ma è il componente PNRP a determinare automaticamente i cloud appropriati a cui connettersi e gli indirizzi da pubblicare all'interno dei cloud.  
  
 Per semplificare notevolmente la risoluzione dei nomi PNRP in Windows Vista, ora i nomi PNRP possono essere integrati nella funzione getaddrinfo() di Windows Sockets. Per usare PNRP per la risoluzione di un nome in un indirizzo IPv6, le applicazioni possono servirsi della funzione getaddrinfo() per risolvere il nome di dominio completo (FQDN) name.prnp.net, in cui name rappresenta il nome di peer risolto. Il dominio pnrp.net in Windows Vista è un dominio riservato per la risoluzione dei nomi PNRP.  
  
 Il passaggio di messaggi tra le applicazioni PeerToPeer viene ancora gestito da architetture sottostanti, ad esempio PeerChannel e [Dati di grandi dimensioni e flussi](http://go.microsoft.com/fwlink/?LinkID=179652) WCF.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Net.PeerToPeer>

