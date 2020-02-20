---
title: Confronto tra i servizi di streaming e i campi ripetuti-gRPC per sviluppatori WCF
description: Confrontare i campi ripetuti con i servizi di streaming come modi per passare raccolte di dati tramite gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: 0e717df57ba2bb52d63a063072d8a45bf0f7e395
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503379"
---
# <a name="grpc-streaming-services-vs-repeated-fields"></a>confronto tra i servizi di streaming gRPC e i campi ripetuti

i servizi gRPC forniscono due modi per restituire set di impostazioni o elenchi di oggetti. La specifica del messaggio buffer del protocollo utilizza la parola chiave `repeated` per dichiarare elenchi o matrici di messaggi all'interno di un altro messaggio. La specifica del servizio gRPC usa la parola chiave `stream` per dichiarare una connessione persistente con esecuzione prolungata. Su tale connessione, vengono inviati più messaggi e possono essere elaborati singolarmente. 

È anche possibile usare la funzionalità `stream` per i dati temporali con esecuzione prolungata, ad esempio notifiche o messaggi di log. In questo capitolo verrà tuttavia considerato l'utilizzo per la restituzione di un singolo set di dati.

Da usare dipende da fattori quali:

- Dimensioni complessive del set di dati.
- Tempo impiegato per creare il set di dati a livello di client o server.
- Indica se il consumer del set di dati può iniziare a agire su di esso non appena il primo elemento è disponibile o se è necessario che il set di dati completo esegua operazioni utili.

## <a name="when-to-use-repeated-fields"></a>Quando usare campi di `repeated`

Per tutti i set di dati di dimensioni limitate e che possono essere generati interamente in un breve periodo di tempo, ad indicare, in un secondo momento, è consigliabile usare un campo `repeated` in un messaggio protobuf normale. Ad esempio, in un sistema di e-commerce, per compilare un elenco di elementi all'interno di un ordine è probabile che l'elenco non sia molto grande. La restituzione di un singolo messaggio con un campo `repeated` è un ordine di grandezza più veloce rispetto all'uso di `stream` e comporta un minor sovraccarico di rete.

Se il client richiede tutti i dati prima di iniziare a elaborarli e il set di dati è sufficientemente piccolo da costruire in memoria, provare a usare un campo `repeated`. Considerarlo anche se la creazione del set di dati in memoria nel server è più lenta.

## <a name="when-to-use-stream-methods"></a>Quando usare i metodi `stream`

Quando gli oggetti Message nei set di impostazioni sono potenzialmente di grandi dimensioni, è consigliabile trasferirli usando le richieste di streaming o le risposte. È più efficiente costruire un oggetto di grandi dimensioni in memoria, scriverlo nella rete e quindi liberare le risorse. Questo approccio migliorerà la scalabilità del servizio.

Analogamente, è necessario inviare set di elementi di dimensioni non vincolate sui flussi per evitare di esaurire la memoria durante la costruzione.

Per i set di impostazioni in cui il consumer può elaborare separatamente ogni elemento, è consigliabile usare un flusso se significa che lo stato di avanzamento può essere indicato all'utente. L'uso di un flusso può migliorare la velocità di risposta di un'applicazione, ma è necessario bilanciare il rapporto con le prestazioni complessive dell'applicazione.

Un altro scenario in cui i flussi possono essere utili è la posizione in cui un messaggio viene elaborato tra più servizi. Se ogni servizio in una catena restituisce un flusso, il servizio Terminal, ovvero l'ultimo nella catena, può iniziare a restituire messaggi. Questi messaggi possono essere elaborati e passati di nuovo lungo la catena al richiedente originale. Il richiedente può restituire un flusso o aggregare i risultati in un singolo messaggio di risposta. Questo approccio si presta bene a modelli come MapReduce.

>[!div class="step-by-step"]
>[Precedente](migrate-duplex-services.md)
>[Successivo](client-libraries.md)
