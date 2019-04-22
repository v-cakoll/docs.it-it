---
title: Routing IPv6
ms.date: 03/30/2017
ms.assetid: c98731b4-b542-46a2-9947-1cea63c186b2
ms.openlocfilehash: 0f0fbce84caf096770e49ab47fb1de5b23b44b33
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59136682"
---
# <a name="ipv6-routing"></a>Routing IPv6
Uno dei vantaggi di IPv6 è che fornisce un meccanismo di routing flessibile. A causa del modo in cui gli ID rete IPv4 venivano e vengono allocati, tabelle di routing di grandi dimensioni devono essere gestite dai router che si trovano sulle backbone Internet. Questi router devono conoscere tutte le route per poter inoltrare i pacchetti potenzialmente indirizzati a qualsiasi nodo in Internet. Grazie a questa capacità di aggregare indirizzi, IPv6 consente un indirizzamento flessibile e riduce drasticamente le dimensioni delle tabelle di routing. In questa nuova architettura di indirizzamento i router intermedi devono tenere traccia solo della parte locale della rete per poter inoltrare i messaggi nel modo appropriato.  
  
## <a name="neighbor-discovery"></a>Individuazione router adiacenti  
 Ecco alcune delle funzionalità offerte da Individuazione router adiacenti:  
  
-   Individuazione dei router. Permette agli host di identificare i router locali.  
  
-   Risoluzione degli indirizzi. Permette ai nodi di risolvere un indirizzo a livello di collegamento per un indirizzo dell'hop successivo corrispondente (in sostituzione ad Address Resolution Protocol, ARP).  
  
-   Configurazione automatica degli indirizzi. Permette agli host di configurare automaticamente gli indirizzi locali rispetto al sito e gli indirizzi globali.  
  
 Individuazione router adiacenti usa messaggi ICMPv6 (Internet Control Message Protocol for IPv6) che includono:  
  
-   Router Advertisement. Inviato da un router con una frequenza più o meno periodica o in risposta a un messaggio Router Solicitation. I router IPv6 usano messaggi Router Advertisement per comunicare la propria disponibilità, i prefissi di indirizzo e altri parametri.  
  
-   Router Solicitation. Inviato da un host per richiedere che i router nel collegamento inviino immediatamente un messaggio Router Solicitation.  
  
-   Neighbor Solicitation. Inviato dai nodi per la risoluzione degli indirizzi, il rilevamento di indirizzi duplicati o la verifica che un router adiacente sia ancora raggiungibile.  
  
-   Neighbor Advertisement. Inviato dai nodi per rispondere a un messaggio Neighbor Solicitation o per comunicare ai router adiacenti una modifica nell'indirizzo a livello di collegamento.  
  
-   Redirect. Inviato dai router per indicare un indirizzo dell'hop successivo migliore a una destinazione specifica per un nodo di invio.  
  
## <a name="see-also"></a>Vedere anche

- [Protocollo IPv6](../../../docs/framework/network-programming/internet-protocol-version-6.md)
- [Socket](../../../docs/framework/network-programming/sockets.md)
