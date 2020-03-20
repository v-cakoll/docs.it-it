---
title: PNRP nello sviluppo di applicazioni
ms.date: 03/30/2017
ms.assetid: 265615d6-4423-4b5d-8626-752e456f4f4e
ms.openlocfilehash: f9a408fbd7fbbb77c0fd5208926f4b06fcf23b38
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "74428202"
---
# <a name="pnrp-in-application-development"></a>PNRP nello sviluppo di applicazioni
In Windows Vista, le applicazioni di rete possono accedere alle funzioni di risoluzione e pubblicazione dei nomi tramite un'API PNRP semplificata.  
  
## <a name="implementing-the-peer-name-resolution-protocol"></a>Implementazione del protocollo PNRP (Peer Name Resolution Protocol)  
 Con l'API PNRP semplificata, non vengono specificati in modo esplicito i cloud per registrare il nome e gli indirizzi, ma è il componente PNRP a determinare automaticamente i cloud appropriati a cui connettersi e gli indirizzi da pubblicare all'interno dei cloud.  
  
 Per semplificare notevolmente la risoluzione dei nomi PNRP in Windows Vista, ora i nomi PNRP possono essere integrati nella funzione getaddrinfo() di Windows Sockets. Per usare PNRP per la risoluzione di un nome in un indirizzo IPv6, le applicazioni possono servirsi della funzione getaddrinfo() per risolvere il nome di dominio completo (FQDN) name.prnp.net, in cui name rappresenta il nome di peer risolto. Il dominio pnrp.net in Windows Vista è un dominio riservato per la risoluzione dei nomi PNRP.  
  
 Il passaggio di messaggi tra le applicazioni PeerToPeer viene ancora gestito da architetture sottostanti, ad esempio PeerChannel e [Dati di grandi dimensioni e flussi](../wcf/feature-details/large-data-and-streaming.md) WCF.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Net.PeerToPeer>
