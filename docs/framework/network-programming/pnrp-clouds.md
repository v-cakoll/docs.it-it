---
title: Cloud PNRP
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a82e2bf1-62ab-4c2d-83f3-3217a6aead2e
caps.latest.revision: "4"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 1b9769d4e3936e127407f68de81f9b5b5da4fbc0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="pnrp-clouds"></a>Cloud PNRP
Un "cloud" PNRP rappresenta un set di nodi che possono comunicare tra loro attraverso la rete. Il termine "cloud" è sinonimo di "rete di peer" e "grafico peer-to-peer".  
  
 Le comunicazioni tra i nodi non devono mai attraversare un cloud per raggiungerne un altro. Un'istanza di <xref:System.Net.PeerToPeer.Cloud> viene identificata in modo univoco in base al relativo nome, con distinzione tra maiuscole e minuscole. Un singolo peer o nodo può essere connesso a più di un cloud.  
  
 I cloud sono strettamente legati alle interfacce di rete.  In un computer multihomed con due schede di rete collegate a subnet diverse, verranno restituiti tre cloud (uno per ognuno degli indirizzi locali al collegamento per ogni interfaccia) e un singolo cloud con ambito globale.  
  
 PNRP usa tre "ambiti" di cloud. In questo contesto l'ambito è un raggruppamento di computer in grado di individuarsi reciprocamente:  
  
-   Il cloud globale corrisponde all'ambito globale di indirizzi IPv6 e indirizzi globali; rappresenta tutti i computer sull'intera Internet IPv6. Esiste solo un unico cloud globale.  
  
-   Il cloud locale al collegamento corrisponde all'ambito di indirizzi IPv6 locali al collegamento e di indirizzi locali al collegamento. Un cloud locale al collegamento riguarda un collegamento specifico, che generalmente coincide con la subnet collegata localmente. Sono possibili più cloud locali al collegamento.  
  
 Un terzo cloud specifico del sito corrisponde all'ambito di indirizzi IPv6 del sito e indirizzi locali di sito. Questo cloud è deprecato, ma è ancora supportato in PNRP.  
  
## <a name="clouds"></a>Cloud  
 I cloud PNRP sono rappresentati da istanze della classe <xref:System.Net.PeerToPeer.Cloud>. I gruppi di cloud usati come peer sono rappresentati da istanze della classe enumerabile <xref:System.Net.PeerToPeer.CloudCollection>. Le raccolte di cloud PNRP note al peer corrente possono essere ottenute chiamando il metodo statico <xref:System.Net.PeerToPeer.Cloud.GetAvailableClouds%2A>.  
  
 I singoli cloud hanno nomi univoci, rappresentati come una stringa Unicode di 256 caratteri. Questi nomi, insieme all'ambito sopra indicato, vengono usati per costruire istanze univoche della classe Cloud. Queste istanze possono essere serializzate e ricostruite per un utilizzo permanente.  
  
 Dopo aver creato e ottenuto un'istanza di Cloud, i nomi di peer possono essere registrati per tale istanza per creare una rete di peer noti.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Net.PeerToPeer.Cloud>  
 [Protocollo PNRP (Peer Name Resolution Protocol)](../../../docs/framework/network-programming/peer-name-resolution-protocol.md)
