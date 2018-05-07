---
title: Tracce significative
ms.date: 03/30/2017
ms.assetid: 40a1770e-3b09-4142-b0dd-f9ef73642074
ms.openlocfilehash: 2dc5010874285ba14dae625fcbf92740eb1707b0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="significant-traces"></a>Tracce significative
In questo argomento vengono elencate alcune delle tracce principali generate da Windows Communication Foundation (WCF).  
  
## <a name="significant-traces"></a>Tracce significative  
  
|Traccia|Descrizione|  
|-----------|-----------------|  
|Traccia log dei messaggi.|La traccia viene emessa alla registrazione di un messaggio [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] tramite la funzionalità di registrazione dei messaggi, se l'origine di traccia `System.ServiceModel.MessageLogging` è attivata. Facendo clic su questa traccia verrà visualizzato il messaggio. Esistono quattro punti di registrazione configurabili per un messaggio: `ServiceLevelSendRequest`, `TransportSend`, `TransportReceive`, `ServiceLevelReceiveRequest`, indicati anche dall'attributo dell'origine messaggio nella traccia del log dei messaggi.|  
|Traccia messaggio ricevuto|Questa traccia viene emessa quando viene ricevuto un messaggio [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)], se la l'origine di traccia `System.ServiceModel` è attivata al livello Informazioni o Dettagliato. Questa traccia è necessaria per la visualizzazione del tasto di direzione della correlazione tra i messaggi nella visualizzazione del grafico delle attività.|  
|Traccia messaggio inviato|Questa traccia viene emessa all'invio di un messaggio [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] se l'origine di traccia `System.ServiceModel` è attivata a livello di informazioni o di dettaglio. Questa traccia è necessaria per la visualizzazione del tasto di direzione della correlazione tra i messaggi nella visualizzazione del grafico delle attività.|  
|Ottiene ChannelEndpointElement|Questa traccia viene emessa quando si costruisce una channel factory, a livello di informazioni. Fornisce una descrizione dell'endpoint con cui sta comunicando il client, ad esempio l'indirizzo remoto, l'associazione o il nome del contratto.|  
|Ottiene ServiceElement|Questa traccia viene emessa quando si costruisce un host del servizio, a livello di informazioni. Fornisce una descrizione dell'associazione e del contratto di servizio.|  
|Creazione SocketConnection|Questa traccia viene emessa nella prima azione di elaborazione eseguita dal client e nell'attività di ricezione byte nel servizio. Fornisce gli indirizzi IP locali e remoti. Inoltre, viene generata al livello delle informazioni.|
