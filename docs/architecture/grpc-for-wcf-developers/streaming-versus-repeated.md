---
title: Servizi di streaming e campi ripetuti - gRPC per gli sviluppatori WCF
description: Confronta i campi ripetuti con i servizi di streaming come modalità di passaggio di raccolte di dati tramite gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: 542ebc393f9c9c1ad717d02d01fab33d85c18917
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147750"
---
# <a name="grpc-streaming-services-vs-repeated-fields"></a>Servizi di streaming gRPC a confronto con i campi ripetuti

I servizi gRPC offrono due modi per restituire set di dati o elenchi di oggetti. La specifica del messaggio `repeated` Protocol Buffers utilizza la parola chiave per dichiarare elenchi o matrici di messaggi all'interno di un altro messaggio. La specifica del servizio `stream` gRPC utilizza la parola chiave per dichiarare una connessione permanente a esecuzione prolungata. Tramite tale connessione, vengono inviati più messaggi e possono essere elaborati singolarmente.

È inoltre possibile `stream` utilizzare la funzionalità per i dati temporali a esecuzione prolungata, ad esempio notifiche o messaggi di log. Ma questo capitolo prenderà in considerazione il suo utilizzo per la restituzione di un singolo set di dati.

La che è consigliabile utilizzare dipende da fattori quali:

- Dimensioni complessive del set di dati.
- Tempo impiegato per creare il set di dati alla fine del client o del server.
- Se il consumer del set di dati può iniziare a agire su di esso non appena il primo elemento è disponibile o ha bisogno dell'intero set di dati per eseguire qualsiasi operazione utile.

## <a name="when-to-use-repeated-fields"></a>Quando utilizzare `repeated` i campi

Per qualsiasi set di dati che è vincolato in dimensioni e che può essere generato nella `repeated` sua interezza in un breve periodo di tempo, ad esempio, in meno di un secondo, è necessario utilizzare un campo in un normale messaggio Protobuf. Ad esempio, in un sistema di e-commerce, per creare un elenco di elementi all'interno di un ordine è probabilmente veloce e l'elenco non sarà molto grande. La restituzione di `repeated` un singolo messaggio con un campo `stream` è un ordine di grandezza più veloce rispetto all'utilizzo e comporta un sovraccarico di rete inferiore.

Se il client necessita di tutti i dati prima di iniziare a elaborarli `repeated` e il set di dati è sufficientemente piccolo da costruire in memoria, è consigliabile usare un campo. Considerarlo anche se la creazione del set di dati in memoria sul server è più lenta.

## <a name="when-to-use-stream-methods"></a>Quando usare `stream` i metodi

Quando gli oggetti messaggio nei set di dati sono potenzialmente molto grandi, è consigliabile trasferirli tramite richieste di streaming o risposte. È più efficiente costruire un oggetto di grandi dimensioni in memoria, scriverlo nella rete e quindi liberare le risorse. Questo approccio migliorerà la scalabilità del servizio.

Analogamente, è consigliabile inviare set di dati di dimensioni non vincolate su flussi per evitare di esaurire la memoria durante la costruzione.

Per i set di dati in cui il consumer può elaborare separatamente ogni elemento, è consigliabile usare un flusso se significa che lo stato di avanzamento può essere indicato all'utente. L'uso di un flusso può migliorare la velocità di risposta di un'applicazione, ma è consigliabile bilanciarla con le prestazioni complessive dell'applicazione.

Un altro scenario in cui i flussi possono essere utili è il punto in cui un messaggio viene elaborato tra più servizi. Se ogni servizio in una catena restituisce un flusso, il servizio terminal (ovvero l'ultimo nella catena) può iniziare a restituire messaggi. Questi messaggi possono essere elaborati e passati lungo la catena al richiedente originale. Il richiedente può restituire un flusso o aggregare i risultati in un singolo messaggio di risposta. Questo approccio si presta bene a modelli come MapReduce.This approach preends itself well to patterns like MapReduce.

>[!div class="step-by-step"]
>[Successivo](migrate-duplex-services.md)
>[precedente](client-libraries.md)
