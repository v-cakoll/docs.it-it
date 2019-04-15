---
title: PNRP nello sviluppo di applicazioni
ms.date: 03/30/2017
ms.assetid: 265615d6-4423-4b5d-8626-752e456f4f4e
ms.openlocfilehash: 4cd0d739e58cd252213e8d5c16d29cc612338df6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178139"
---
# <a name="pnrp-in-application-development"></a>PNRP nello sviluppo di applicazioni
In Windows Vista, le applicazioni di rete possono accedere alle funzioni di risoluzione e pubblicazione dei nomi tramite un'API PNRP semplificata.  
  
## <a name="implementing-the-peer-name-resolution-protocol"></a>Implementazione del protocollo PNRP (Peer Name Resolution Protocol)  
 Con l'API PNRP semplificata, non vengono specificati in modo esplicito i cloud per registrare il nome e gli indirizzi, ma è il componente PNRP a determinare automaticamente i cloud appropriati a cui connettersi e gli indirizzi da pubblicare all'interno dei cloud.  
  
 Per semplificare notevolmente la risoluzione dei nomi PNRP in Windows Vista, ora i nomi PNRP possono essere integrati nella funzione getaddrinfo() di Windows Sockets. Per usare PNRP per la risoluzione di un nome in un indirizzo IPv6, le applicazioni possono servirsi della funzione getaddrinfo() per risolvere il nome di dominio completo (FQDN) name.prnp.net, in cui name rappresenta il nome di peer risolto. Il dominio pnrp.net in Windows Vista è un dominio riservato per la risoluzione dei nomi PNRP.  
  
 Il passaggio di messaggi tra le applicazioni PeerToPeer viene ancora gestito da architetture sottostanti, ad esempio PeerChannel e [Dati di grandi dimensioni e flussi](https://go.microsoft.com/fwlink/?LinkID=179652) WCF.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Net.PeerToPeer>
