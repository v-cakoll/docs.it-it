---
title: protocollo IPv6
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IPv6, improvements
- IPv4
- IPv6
- Internet Protocol version 6, improvements
- Internet Protocol version 6
ms.assetid: e6fa8ebd-010a-4c48-a5ec-a5102c53c06f
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 333fbb452cb1f24b5e62d1106eff4560b26267b6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="internet-protocol-version-6"></a>protocollo IPv6
IPv6 (Internet Protocol version 6) è una nuova famiglia di protocolli standard per il livello di rete di Internet. IPv6 è progettato per risolvere molti dei problemi riscontrati nell'attuale versione della famiglia di protocolli IP (chiamata IPv4), relativi a esaurimento di indirizzi, sicurezza, configurazione automatica, estendibilità e così via. IPv6 estende le funzionalità di Internet in modo da permettere nuovi tipi di applicazioni, tra cui applicazioni peer-to-peer e per dispositivi mobili. Di seguito sono elencati i problemi principali dell'attuale protocollo IPv4:  
  
-   Esaurimento rapido dello spazio di indirizzi.  
  
     Questo problema ha comportato l'uso di convertitori NAT (Network Address Translator) che eseguono il mapping di più indirizzi privati in un unico indirizzo IP pubblico. I problemi principali creati da questo meccanismo sono il sovraccarico di elaborazione e la mancanza di connettività end-to-end.  
  
-   Mancanza di supporto delle gerarchie.  
  
     A causa della sua tipica organizzazione predefinita delle classi, il protocollo IPv4 è privo di vero supporto delle gerarchie. È impossibile strutturare gli indirizzi IP in modo da eseguire un mapping effettivo della topologia di rete. Questo notevole difetto di progettazione crea la necessità di tabelle di routing di grandi dimensioni per distribuire pacchetti IPv4 in qualsiasi posizione in Internet.  
  
-   Configurazione di rete complessa.  
  
     Con IPv4, gli indirizzi devono essere assegnati in modo statico o tramite un protocollo di configurazione come DHCP. In una situazione ideale, gli host non dovrebbero dipendere dall'amministrazione di un'infrastruttura DHCP. Al contrario, dovrebbero essere in grado di configurare se stessi in base al segmento di rete in cui si trovano.  
  
-   Mancanza di autenticazione e riservatezza integrate.  
  
     IPv4 non richiede il supporto di meccanismi che forniscono l'autenticazione o la crittografia dei dati scambiati. Questo problema è stato risolto con IPv6. Internet Protocol security (IPSec) è un requisito del supporto di IPv6.  
  
 Una nuova famiglia di protocolli deve soddisfare i requisiti di base seguenti:  
  
-   Routing e indirizzamento su larga scala con sovraccarico ridotto.  
  
-   Configurazione automatica per diverse situazione di connessione.  
  
-   Autenticazione e riservatezza integrate.  
  
 Per altre informazioni, vedere [Indirizzamento IPv6](../../../docs/framework/network-programming/ipv6-addressing.md), [Routing IPv6](../../../docs/framework/network-programming/ipv6-routing.md), [Configurazione automatica di IPv6](../../../docs/framework/network-programming/ipv6-auto-configuration.md), [Abilitazione e disabilitazione di IPv6](../../../docs/framework/network-programming/enabling-and-disabling-ipv6.md) e [Procedura: Modificare il file di configurazione del computer per abilitare il supporto IPv6](../../../docs/framework/network-programming/how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md).  
  
## <a name="references"></a>Riferimenti  
 Di seguito sono elencati alcuni documenti RFC selezionati disponibili nel sito Internet Engineering Task Force ([http://www.ietf.org](http://www.ietf.org/)):  
  
-   RFC 1287, Towards the Future Internet Architecture (Verso il futuro dell'architettura di Internet).  
  
-   RFC 1454, Comparison of Proposals for Next Version of IP (Confronto tra proposte per la prossima versione di IP).  
  
-   RFC 2373, IP Version 6 Addressing Architecture (Architettura di indirizzamento di IPv6).  
  
-   RFC 2374, An IPv6 Aggregatable Global Unicast Address Format (Formato di indirizzi unicast globali aggregabile a IPv6).  
  
 Informazioni su IPv6 sono disponibili anche nell'[area relativa a IPv6 su Technet](http://go.microsoft.com/fwlink/?LinkID=179658).  
  
## <a name="see-also"></a>Vedere anche  
 [IPv6 Sockets Sample](http://go.microsoft.com/fwlink/?LinkID=179568) (Esempio di socket IPv6)  
 [Esempi di programmazione di rete](../../../docs/framework/network-programming/network-programming-samples.md)  
 [Socket](../../../docs/framework/network-programming/sockets.md)
