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
# <a name="pnrp-in-application-development"></a><span data-ttu-id="3ea68-102">PNRP nello sviluppo di applicazioni</span><span class="sxs-lookup"><span data-stu-id="3ea68-102">PNRP in Application Development</span></span>
<span data-ttu-id="3ea68-103">In Windows Vista, le applicazioni di rete possono accedere alle funzioni di risoluzione e pubblicazione dei nomi tramite un'API PNRP semplificata.</span><span class="sxs-lookup"><span data-stu-id="3ea68-103">In Windows Vista, networking applications can access name publication and resolution functions through a simplified PNRP application programming interface (API).</span></span>  
  
## <a name="implementing-the-peer-name-resolution-protocol"></a><span data-ttu-id="3ea68-104">Implementazione del protocollo PNRP (Peer Name Resolution Protocol)</span><span class="sxs-lookup"><span data-stu-id="3ea68-104">Implementing the Peer Name Resolution Protocol</span></span>  
 <span data-ttu-id="3ea68-105">Con l'API PNRP semplificata, non vengono specificati in modo esplicito i cloud per registrare il nome e gli indirizzi, ma è il componente PNRP a determinare automaticamente i cloud appropriati a cui connettersi e gli indirizzi da pubblicare all'interno dei cloud.</span><span class="sxs-lookup"><span data-stu-id="3ea68-105">With the simplified PNRP API, clouds are not explicitly specified to register the name and addresses; the PNRP component automatically determines the appropriate clouds to join and the addresses to publish within the clouds.</span></span>  
  
 <span data-ttu-id="3ea68-106">Per semplificare notevolmente la risoluzione dei nomi PNRP in Windows Vista, ora i nomi PNRP possono essere integrati nella funzione getaddrinfo() di Windows Sockets.</span><span class="sxs-lookup"><span data-stu-id="3ea68-106">For highly simplified PNRP name resolution in Windows Vista, PNRP names are now integrated into the getaddrinfo() Windows Sockets function.</span></span> <span data-ttu-id="3ea68-107">Per usare PNRP per la risoluzione di un nome in un indirizzo IPv6, le applicazioni possono servirsi della funzione getaddrinfo() per risolvere il nome di dominio completo (FQDN) name.prnp.net, in cui name rappresenta il nome di peer risolto.</span><span class="sxs-lookup"><span data-stu-id="3ea68-107">To use PNRP to resolve a name to an IPv6 address, applications can use the getaddrinfo() function to resolve the Fully Qualified Domain Name (FQDN) name.prnp.net, in which name is peer name being resolved.</span></span> <span data-ttu-id="3ea68-108">Il dominio pnrp.net in Windows Vista è un dominio riservato per la risoluzione dei nomi PNRP.</span><span class="sxs-lookup"><span data-stu-id="3ea68-108">The pnrp.net domain is a reserved domain in Windows Vista for PNRP name resolution.</span></span>  
  
 <span data-ttu-id="3ea68-109">Il passaggio di messaggi tra le applicazioni PeerToPeer viene ancora gestito da architetture sottostanti, ad esempio PeerChannel e [Dati di grandi dimensioni e flussi](../wcf/feature-details/large-data-and-streaming.md) WCF.</span><span class="sxs-lookup"><span data-stu-id="3ea68-109">Message passing between PeerToPeer applications is still handled by underlying architectures such as PeerChannel and WCF [Large Data and Streaming](../wcf/feature-details/large-data-and-streaming.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ea68-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ea68-110">See also</span></span>

- <xref:System.Net.PeerToPeer>
