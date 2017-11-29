---
title: Tracce significative
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 40a1770e-3b09-4142-b0dd-f9ef73642074
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 58322a472a59ee9d3ac9451ff1f20ed95405ac54
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="significant-traces"></a>Tracce significative
In questo argomento vengono elencate alcune delle tracce principali generate da [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].  
  
## <a name="significant-traces"></a>Tracce significative  
  
|Traccia|Descrizione|  
|-----------|-----------------|  
|Traccia log dei messaggi.|La traccia viene emessa alla registrazione di un messaggio [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] tramite la funzionalità di registrazione dei messaggi, se l'origine di traccia `System.ServiceModel.MessageLogging` è attivata. Facendo clic su questa traccia verrà visualizzato il messaggio. Esistono quattro punti di registrazione configurabili per un messaggio: `ServiceLevelSendRequest`, `TransportSend`, `TransportReceive`, `ServiceLevelReceiveRequest`, indicati anche dall'attributo dell'origine messaggio nella traccia del log dei messaggi.|  
|Traccia messaggio ricevuto|Questa traccia viene emessa quando viene ricevuto un messaggio [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)], se la l'origine di traccia `System.ServiceModel` è attivata al livello Informazioni o Dettagliato. Questa traccia è necessaria per la visualizzazione del tasto di direzione della correlazione tra i messaggi nella visualizzazione del grafico delle attività.|  
|Traccia messaggio inviato|Questa traccia viene emessa all'invio di un messaggio [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] se l'origine di traccia `System.ServiceModel` è attivata a livello di informazioni o di dettaglio. Questa traccia è necessaria per la visualizzazione del tasto di direzione della correlazione tra i messaggi nella visualizzazione del grafico delle attività.|  
|Ottiene ChannelEndpointElement|Questa traccia viene emessa quando si costruisce una channel factory, a livello di informazioni. Fornisce una descrizione dell'endpoint con cui sta comunicando il client, ad esempio l'indirizzo remoto, l'associazione o il nome del contratto.|  
|Ottiene ServiceElement|Questa traccia viene emessa quando si costruisce un host del servizio, a livello di informazioni. Fornisce una descrizione dell'associazione e del contratto di servizio.|  
|Creazione SocketConnection|Questa traccia viene emessa nella prima azione di elaborazione eseguita dal client e nell'attività di ricezione byte nel servizio. Fornisce gli indirizzi IP locali e remoti. Inoltre, viene generata al livello delle informazioni.|
