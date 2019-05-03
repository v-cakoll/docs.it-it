---
title: Tracce significative
ms.date: 03/30/2017
ms.assetid: 40a1770e-3b09-4142-b0dd-f9ef73642074
ms.openlocfilehash: c230c65b4d3fd45c4905d4ae5f4cbbf90e10faad
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61784951"
---
# <a name="significant-traces"></a>Tracce significative
Questo argomento elenca alcune delle tracce principali generate da Windows Communication Foundation (WCF).  
  
## <a name="significant-traces"></a>Tracce significative  
  
|Traccia|Descrizione|  
|-----------|-----------------|  
|Traccia log dei messaggi.|La traccia viene emessa quando viene registrato un messaggio WCF tramite la registrazione dei messaggi funzionalità quando i `System.ServiceModel.MessageLogging` origine di traccia è abilitata. Facendo clic su questa traccia verrà visualizzato il messaggio. Esistono quattro punti di registrazione configurabili per un messaggio: `ServiceLevelSendRequest`, `TransportSend`, `TransportReceive`, `ServiceLevelReceiveRequest`, indicati anche dall'attributo dell'origine messaggio nella traccia del log dei messaggi.|  
|Traccia messaggio ricevuto|Questa traccia viene emessa quando viene ricevuto un messaggio WCF se il `System.ServiceModel` origine di traccia è abilitata al livello informazioni o dettagliato. Questa traccia è necessaria per la visualizzazione del tasto di direzione della correlazione tra i messaggi nella visualizzazione del grafico delle attività.|  
|Traccia messaggio inviato|Questa traccia viene emessa quando viene inviato un messaggio WCF se il `System.ServiceModel` origine di traccia è abilitata al livello informazioni o dettagliato. Questa traccia è necessaria per la visualizzazione del tasto di direzione della correlazione tra i messaggi nella visualizzazione del grafico delle attività.|  
|Ottiene ChannelEndpointElement|Questa traccia viene emessa quando si costruisce una channel factory, a livello di informazioni. Fornisce una descrizione dell'endpoint con cui sta comunicando il client, ad esempio l'indirizzo remoto, l'associazione o il nome del contratto.|  
|Ottiene ServiceElement|Questa traccia viene emessa quando si costruisce un host del servizio, a livello di informazioni. Fornisce una descrizione dell'associazione e del contratto di servizio.|  
|Creazione SocketConnection|Questa traccia viene emessa nella prima azione di elaborazione eseguita dal client e nell'attività di ricezione byte nel servizio. Fornisce gli indirizzi IP locali e remoti. Inoltre, viene generata al livello delle informazioni.|
