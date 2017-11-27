---
title: Mesh del peer
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d93e312e-ac04-40f8-baea-5da1cacb546e
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1ca3d934564447018f44a423c36f26454588db4e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="peer-meshes"></a>Mesh del peer
Oggetto *mesh* è una raccolta denominata (un grafico interconnesso) di nodi peer che possono comunicare tra loro e sono identificati da un ID mesh univoco. Ogni nodo è connesso a più nodi. In una rete ben collegata, vi è un percorso tra due nodi qualsiasi, con un numero di hop relativamente basso tra i nodi situati alle estremità della rete e la rete rimarrà collegata anche se alcuni nodi o connessioni non vanno a buon fine. I nodi attivi nella mesh pubblicano le informazioni sugli endpoint con un ID mesh corrispondente così che gli altri peer possano trovarli.  
  
## <a name="characteristics-of-a-mesh-created-using-peer-channel"></a>Caratteristiche di una rete creata con il canale peer  
  
#### <a name="uniquely-identified"></a>Identificata in modo univoco.  
  
-   Un ID univoco identifica ogni rete. Il nome della mesh (o ID mesh) ha lo stesso formato di un nome host DNS (Domain Name System). L'ID mesh deve quindi essere univoco per il client di destinazione dell'applicazione entro l'ambito del resolver usato. Un nome comune quale "MyFamilysPeers" o "KevinsPokerTable" può facilmente collidere con gli altri nomi utente e restituire non intenzionalmente informazioni sugli endpoint del peer, provocando problemi di privacy o aumentando la latenza della connessione. Per evitare questi problemi è possibile aggiungere un ID univoco come suffisso al nome alternativo della rete, ad esempio "KevinsPokerTable90210".  
  
#### <a name="message-flooding"></a>Flood di messaggi  
  
-   La mesh consente la propagazione dei messaggi da uno o più mittenti a tutti gli altri nodi peer nella stessa mesh. Messaggi propagati da nodi peer usano intestazioni specificate nello spazio dei nomi in `http://schemas.microsoft.com/net/2006/05/peer`.  
  
#### <a name="optimized-connections"></a>Connessioni ottimizzate  
  
-   Una rete del canale peer viene automaticamente regolata in base alla connessione e alla disconnessione dei nodi, assicurando che tutti i nodi abbiano una buona connettività, con una bassa probabilità di creazione di partizioni (gruppi di nodi isolati gli uni dagli altri). Le connessioni nella mesh vengono inoltre dinamicamente ottimizzate in base a modelli di traffico correnti, così che la latenza dei messaggi dal mittente al destinatario sia quanto più breve possibile.  
  
#### <a name="popular-network-features-that-peer-channel-does-not-provide"></a>Le più note funzionalità di rete non fornite dal canale peer  
 È importante conoscere le più note funzionalità di rete non fornite dal canale peer. Queste funzionalità, che possono tutte essere integrate nel canale peer, includono:  
  
-   **Ordinamento dei messaggi:** i messaggi provenienti da un'unica origine potrebbero non arrivare a tutte le altre parti nello stesso ordine o nell'ordine di invio. Se ci sono applicazioni che richiedono che i messaggi vengano recapitati in un determinato ordine, è necessario definire tale ordine all'interno delle applicazioni in questione, ad esempio, includendo un ID a incremento progressivo costante con tutti i messaggi.  
  
-   **La messaggistica affidabile:** canale Peer non include un meccanismo per assicurare la ricezione dei messaggi da tutti i peer. Per garantire il recapito dei messaggi, è necessario scrivere un livello di affidabilità sul canale peer.
