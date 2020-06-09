---
title: 'CustomPeerResolverService: registrazioni client'
ms.date: 03/30/2017
ms.assetid: 40236953-a916-4236-84a6-928859e1331a
ms.openlocfilehash: ce694408edbb40309d1750be49b8414ebcbce3f7
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596838"
---
# <a name="inside-the-custompeerresolverservice-client-registrations"></a>CustomPeerResolverService: registrazioni client
Ogni nodo della rete pubblica le informazioni sull'endpoint relative nel servizio resolver tramite la funzione `Register`. Il servizio resolver archivia queste informazioni come record di registrazione. Questo record contiene un identificatore univoco (RegistrationID) e informazioni sull'endpoint (PeerNodeAddress) per il nodo.  
  
## <a name="stale-records-and-expiration-time"></a>Record non aggiornati e data di scadenza  
 Idealmente, quando un nodo abbandona la rete, chiama la funzione `Unregister` affinché il servizio resolver rimuova la voce di registrazione. Talvolta, i nodi vengono arrestati o diventano inaccessibili prima della chiamata alla funzione `Unregister`, lasciando un record di registrazione non aggiornato.  
  
 I record non aggiornati nel servizio resolver possono causare problemi di connessione. Se un nodo che tenta di connettersi a una rete riceve informazioni di connessione non aggiornate dal servizio resolver, potrebbe richiedere più tempo per connettersi alla rete in modo corretto. I record non aggiornati occupano memoria. Senza un processo di pulizia efficiente, la cache utilizzata per archiviare le registrazioni potrebbe alla fine causare un overflow o un arresto anomalo del servizio resolver.  
  
 <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService> contrassegna ogni record con una data di scadenza (Datetime) e archivia tali informazioni come parte del record. Il servizio utilizza la data di scadenza per identificare i record non aggiornati. Le implementazioni personalizzate dovrebbero offrire un comportamento simile.  
  
## <a name="refreshinterval-and-cleanupinterval"></a>RefreshInterval e CleanupInterval  
 La proprietà `RefreshInterval` di <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService> definisce il periodo di validità dei record di registrazione nella tabella di ricerca della registrazione del servizio. Superata la quantità di tempo fornita a questa proprietà per un determinato record, tale record non risulta più aggiornato e viene contrassegnato per l'eliminazione.  
  
 La proprietà `CleanupInterval` di <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService> specifica al servizio la frequenza con la quale cercare ed eliminare i record di registrazione non aggiornati. È necessario impostare la proprietà `CleanupInterval` su un valore superiore o uguale al valore `RefreshInterval` impostato nel servizio.  
  
 Per implementare il proprio servizio resolver, è necessario scrivere una funzione di manutenzione per rimuovere i record di registrazione non aggiornati. Sono disponibili diversi modi per eseguire questa operazione:  
  
- **Manutenzione periodica**: impostare un timer in modo che venga disattivato periodicamente e scorrere l'archivio dati per eliminare i record obsoleti. Questo approccio è utilizzato da <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>.  
  
- **Eliminazione passiva**: anziché eseguire attivamente la ricerca di record non aggiornati a intervalli regolari, è possibile identificare ed eliminare i record non aggiornati quando il servizio sta già eseguendo un'altra funzione. Questo approccio potrebbe potenzialmente rallentare i tempi di risposta alle richieste dei client resolver, ma elimina la necessità di un timer e potrebbe rivelarsi più efficiente qualora si preveda che un numero ridotto di nodi abbandoni la rete senza chiamare `Unregister`.  
  
## <a name="registrationlifetime-and-refresh"></a>RegistrationLifetime e Refresh  
 Quando un nodo effettua la registrazione con un servizio resolver, riceve un oggetto <xref:System.ServiceModel.PeerResolvers.RegisterResponseInfo> dal servizio. La proprietà `RegistrationLifetime` di questo oggetto indica al nodo il tempo a sua disposizione prima che scada la registrazione e venga rimosso dal servizio resolver. Se, ad esempio, `RegistrationLifetime` è pari a 2 minuti, il nodo deve chiamare `Refresh` in meno di 2 minuti per assicurarsi che il record rimanga aggiornato e non venga eliminato. Quando il servizio resolver riceve una richiesta `Refresh`, cerca il record e reimposta la data di scadenza. Refresh restituisce un oggetto <xref:System.ServiceModel.PeerResolvers.RefreshResponseInfo> con una proprietà `RegistrationLifetime`.  
  
## <a name="see-also"></a>Vedere anche

- [Resolver del peer](peer-resolvers.md)
