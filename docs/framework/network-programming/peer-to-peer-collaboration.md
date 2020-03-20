---
title: Collaborazione peer-to-peer
ms.date: 03/30/2017
ms.assetid: b6216d88-bccb-4a59-9f1c-9f751708e811
ms.openlocfilehash: 7cf92f6bf3c269e584cb8b3cdcf910be5b89fd7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "71047389"
---
# <a name="peer-to-peer-collaboration"></a>Collaborazione peer-to-peer

Il termine rete peer-to-peer si riferisce all'utilizzo di computer relativamente potenti (PC) esistenti ai margini di Internet per attività di elaborazione più estese rispetto a quelle solamente basate su client. I PC moderni hanno processori molto veloci, tanta memoria e dischi rigidi di grandi dimensioni e nessuna di queste risorse viene usata appieno per l'esecuzione di attività di elaborazione comuni, come ad esempio posta elettronica ed esplorazione del Web. I PC moderni possono fungere facilmente sia da client che da server (peer) per molti tipi di applicazioni.  
  
L'infrastruttura di collaborazione peer-to-peer è un'implementazione semplificata dell'infrastruttura peer-to-peer di Microsoft Windows che sfrutta il servizio Persone nelle vicinanze in Windows Vista e piattaforme successive. Si tratta di una funzionalità particolarmente adatta alle applicazioni abilitate per reti peer all'interno di una subnet per cui è attivo il servizio Persone nelle vicinanze, sebbene possa essere usata anche per endpoint o contatti Internet. Incorpora la funzione di gestione dei contatti comuni usata da Live Messenger e altre applicazioni in grado di riconoscere Live per determinare l'endpoint di contatto, la disponibilità e la presenza.  
  
## <a name="collaboration-applications"></a>Applicazioni di collaborazione

 Un'applicazione di collaborazione peer-to-peer tipica include i passaggi seguenti:  
  
- Il peer determina l'identità di un peer interessato a ospitare una sessione di collaborazione  
  
- Viene inviata una richiesta per ospitare una sessione, in qualche modo, e il peer host accetta di gestire l'attività di collaborazione.  
  
- L'host invita i contatti nella subnet (incluso il richiedente) a una sessione.  
  
- Tutti i peer che vogliono collaborare possono aggiungere l'host ai relativi strumenti di gestione dei contatti.  
  
- La maggior parte dei peer invierà risposte all'invito al peer host in modo tempestivo, indicando se accettano o rifiutano l'invito.  
  
- Tutti i peer che vogliono collaborare sottoscriveranno il peer host.  
  
- Mentre i peer eseguono le attività di collaborazione iniziali, il peer host può aggiungere peer remoti allo strumento di gestione dei contatti. Elabora inoltre tutte le risposte agli inviti per stabilire chi ha accettato, chi ha rifiutato e chi non ha risposto.  Può annullare gli inviti per coloro che non hanno risposto oppure eseguire un'altra attività.  
  
- A questo punto, il peer host può avviare una sessione di collaborazione con tutti i peer invitati o registrare un'applicazione nell'infrastruttura di collaborazione.  Le applicazioni P2P usano l'infrastruttura di collaborazione peer-to-peer e lo spazio dei nomi <xref:System.Net.PeerToPeer.Collaboration> per coordinare le comunicazioni per giochi, BBS, conferenze e altre applicazioni per la presenza senza server.  
  
## <a name="peer-to-peer-networking-security"></a>Sicurezza delle reti peer-to-peer  

 In un dominio di Active Directory, i controller di dominio offrono i servizi di autenticazione tramite Kerberos. In un ambiente peer senza server, i peer devono implementare un sistema di autenticazione proprio. In una rete peer-to-peer qualsiasi nodo può fungere da Autorità di certificazione, eliminando la necessità di un certificato radice nell'archivio radice attendibile di ogni peer. L'autenticazione viene fornita mediante certificati autofirmati, formattati come certificati X.509. Questi sono i certificati creati da ogni peer, che genera la coppia di chiavi pubblica/privata e il certificato che viene firmato con la chiave privata. Il certificato autofirmato viene usato per l'autenticazione e per fornire informazioni sull'entità peer. Come per l'autenticazione X.509, l'autenticazione di una rete di peer si basa su una catena di certificati riconducibili a una chiave pubblica attendibile.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Net.PeerToPeer.Collaboration>
- [Informazioni sullo spazio dei nomi System.Net.PeerToPeer.Collaboration](about-the-system-net-peertopeer-collaboration-namespace.md)
