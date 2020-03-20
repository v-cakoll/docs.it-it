---
title: Informazioni sullo spazio dei nomi System.Net.PeerToPeer.Collaboration
ms.date: 03/30/2017
ms.assetid: b5d8c1c1-6844-4947-9759-c7f1b564bded
ms.openlocfilehash: f0c9ecaacc1d875aac8eed61a85ca7579f5cb8a1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "64649518"
---
# <a name="about-the-systemnetpeertopeercollaboration-namespace"></a>Informazioni sullo spazio dei nomi System.Net.PeerToPeer.Collaboration
Lo spazio dei nomi <xref:System.Net.PeerToPeer.Collaboration> offre classi e API che consentono di implementare attività di collaborazione peer usando l'infrastruttura di collaborazione peer-to-peer.  
  
## <a name="classes"></a>Classi  
 Le principali classi usate nell'implementazione di un'attività di collaborazione peer-to-peer sono:  
  
- <xref:System.Net.PeerToPeer.Collaboration.ContactManager>, che consente di archiviare i contatti peer.  
  
- <xref:System.Net.PeerToPeer.Collaboration.PeerApplication>, in cui è possibile collaborare, ad esempio un gioco, un client di chat o una soluzione di gestione delle conferenze.  
  
- I peer che collaboreranno in un'attività  e che possono essere rappresentati come <xref:System.Net.PeerToPeer.Collaboration.PeerContact>, <xref:System.Net.PeerToPeer.Collaboration.PeerNearMe> o oggetti <xref:System.Net.PeerToPeer.Collaboration.PeerEndPoint>.  
  
- La stessa classe statica <xref:System.Net.PeerToPeer.Collaboration.PeerCollaboration>, che specifica le applicazioni disponibili e i peer partecipanti ad ognuna di esse.  
  
 Per invitare i peer a una sessione di collaborazione vengono usati i metodi <xref:System.Net.PeerToPeer.Collaboration.PeerContact.Invite%2A>.  Un peer chiamante può sottoscrivere un altro peer a eventi che segnalano aggiornamenti a un oggetto o a un'applicazione o forniscono informazioni di presenza associate alla sessione di collaborazione. Le classi di presenza specificano se un <xref:System.Net.PeerToPeer.Collaboration.Peer> è disponibile per la collaborazione, mentre la classe <xref:System.Net.PeerToPeer.Collaboration.PeerScope> consente di specificare il tipo partecipazione consentita per un peer: <xref:System.Net.PeerToPeer.Collaboration.PeerScope.Internet> (globale), <xref:System.Net.PeerToPeer.Collaboration.PeerScope.NearMe>, (subnet) o <xref:System.Net.PeerToPeer.Collaboration.PeerScope.None>.  
  
 Una sessione di collaborazione si articola in quattro passaggi:  
  
- Individuazione. Individuare o pubblicare le applicazioni, i peer e le informazioni di presenza.  Ad esempio, trovare altre persone nella subnet locale con lo stesso gioco installato.  
  
- Invito. Inviare e accettare inviti protetti a peer remoti per avviare o partecipare a sessioni <xref:System.Net.PeerToPeer.Collaboration.PeerCollaboration>.  
  
- Gestione dei contatti. Aggiungere i peer individuati come contatti a <xref:System.Net.PeerToPeer.Collaboration.ContactManager>.  
  
- Comunicazione. Quando viene stabilita la comunicazione, usare le API <xref:System.Net>, l'API <xref:System.Net.PeerToPeer> o le classi del canale peer di Windows Communication Foundation per le comunicazioni a più parti.  
  
 Il peer host, ad esempio, avvia una sessione di collaborazione e usa il metodo <xref:System.Net.PeerToPeer.Collaboration.ContactManager.CreateContact%2A> per aggiungere un peer remoto e uno relativi dei peer locali a Gestione contatti del peer host.  In questo caso, i tre utenti parteciperanno nella rispettiva sessione di collaborazione privata.  
  
 Le tipiche applicazioni P2P sono: conferenze telefoniche per la gestione collaborativa degli appunti, applicazioni chat senza server, annunci pubblicitari interattivi e sessioni di giochi online.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Net.PeerToPeer.Collaboration>
