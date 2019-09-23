---
title: Servizi di streaming gRPC rispetto a campi ripetuti-gRPC per sviluppatori WCF
description: Confronto tra campi ripetuti e servizi di streaming come modalità di passaggio di raccolte di dati con gRPC.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 7dc3c8f5bf2efc304da7d50661ba47db500e67a0
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71184071"
---
# <a name="grpc-streaming-services-versus-repeated-fields"></a>Servizi di streaming gRPC rispetto ai campi ripetuti

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

i servizi gRPC forniscono due modi per restituire set di impostazioni o elenchi di oggetti. La specifica del messaggio buffer del protocollo utilizza `repeated` la parola chiave per dichiarare elenchi o matrici di messaggi all'interno di un altro messaggio. La specifica del servizio gRPC utilizza `stream` la parola chiave per dichiarare una connessione persistente con esecuzione prolungata su cui vengono inviati più messaggi e che può essere elaborata singolarmente. La `stream` funzionalità può essere usata anche per dati temporali con esecuzione prolungata, ad esempio notifiche o messaggi di log, ma in questo capitolo viene considerato l'uso per la restituzione di un singolo set di dati.

È necessario utilizzare dipende da diversi fattori, ad esempio la dimensione complessiva del set di dati, il tempo necessario per creare il set di dati a livello di client o server e se il consumer del set di dati può iniziare a operare su di esso non appena il primo elemento è disponibile o necessita del set di dati completo per eseguire operazioni utili.

## <a name="when-to-use-repeated-fields"></a>Quando usare `repeated` i campi

Per qualsiasi set di dati vincolato a dimensioni e che può essere generato interamente in un breve periodo di tempo, ad indicare in un secondo, è necessario usare un `repeated` campo in un normale messaggio protobuf. Ad esempio, in un sistema di e-commerce, per compilare un elenco di elementi all'interno di un ordine è probabile che l'elenco non sia molto grande. La restituzione di un singolo `repeated` messaggio con un campo è un ordine di grandezza più `stream` veloce rispetto all'utilizzo di un e comporta un minor sovraccarico di rete.

Se il client richiede tutti i dati prima di iniziare a elaborarli e il set di dati è sufficientemente piccolo da costruire in memoria, provare `repeated` a usare un campo anche se la creazione effettiva del set di dati in memoria nel server è più lenta.

## <a name="when-to-use-stream-methods"></a>Quando usare `stream` i metodi

I set di impostazioni in cui gli oggetti messaggio sono potenzialmente molto grandi vengono trasferiti in modo ottimale tramite richieste di streaming o risposte. È più efficiente costruire un oggetto di grandi dimensioni in memoria, scriverlo nella rete e quindi liberare le risorse. Questo approccio migliorerà la scalabilità del servizio.

Analogamente, i set di dati di dimensioni non vincolate devono essere inviati attraverso i flussi per evitare di esaurire la memoria durante la loro costruzione.

Per i set di impostazioni in cui ogni singolo elemento può essere elaborato separatamente dal consumer, è consigliabile usare un flusso se significa che lo stato di avanzamento può essere indicato all'utente finale. Questo potrebbe migliorare la velocità di risposta apparente di un'applicazione, sebbene questo debba essere bilanciato in base alle prestazioni complessive dell'applicazione.

Un altro scenario in cui i flussi possono essere utili è la posizione in cui un messaggio viene elaborato tra più servizi. Se ogni servizio in una catena restituisce un flusso, il servizio Terminal, ovvero l'ultimo nella catena, può iniziare a restituire messaggi che possono essere elaborati e passati di nuovo lungo la catena al richiedente originale, che può restituire un flusso o aggregare Restituisce un singolo messaggio di risposta. Questo approccio si presta bene a modelli come map/reduce.

>[!div class="step-by-step"]
>[Precedente](migrate-duplex-services.md)
>[Successivo](client-libraries.md)
