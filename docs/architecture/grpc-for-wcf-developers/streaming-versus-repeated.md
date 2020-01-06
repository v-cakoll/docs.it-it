---
title: Confronto tra i servizi di streaming e i campi ripetuti-gRPC per sviluppatori WCF
description: Confrontare i campi ripetuti con i servizi di streaming come modi per passare raccolte di dati con gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: 46586ab08df6b136cdafb990ce8be75435a6bf6c
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337860"
---
# <a name="grpc-streaming-services-versus-repeated-fields"></a>Servizi di streaming gRPC rispetto ai campi ripetuti

i servizi gRPC forniscono due modi per restituire set di impostazioni o elenchi di oggetti. La specifica del messaggio buffer del protocollo utilizza la parola chiave `repeated` per dichiarare elenchi o matrici di messaggi all'interno di un altro messaggio. La specifica del servizio gRPC usa la parola chiave `stream` per dichiarare una connessione persistente con esecuzione prolungata in cui vengono inviati più messaggi e può essere elaborato singolarmente. La funzionalità `stream` può essere usata anche per dati temporali con esecuzione prolungata, ad esempio notifiche o messaggi di log, ma in questo capitolo viene considerato l'utilizzo per la restituzione di un singolo set di dati.

È necessario utilizzare dipende da diversi fattori, ad esempio la dimensione complessiva del set di dati, il tempo necessario per creare il set di dati a livello di client o server e se il consumer del set di dati può iniziare a operare su di esso non appena il primo elemento è disponibile o necessita del set di dati completo per eseguire operazioni utili.

## <a name="when-to-use-repeated-fields"></a>Quando usare campi di `repeated`

Per qualsiasi set di dati vincolato a dimensioni e che può essere generato interamente in un breve periodo di tempo, ad indicare in un secondo, è necessario usare un campo `repeated` in un messaggio protobuf normale. Ad esempio, in un sistema di e-commerce, per compilare un elenco di elementi all'interno di un ordine è probabile che l'elenco non sia molto grande. La restituzione di un singolo messaggio con un campo `repeated` è un ordine di grandezza più veloce rispetto all'utilizzo di un `stream` e comporta un minor sovraccarico di rete.

Se il client richiede tutti i dati prima di iniziare a elaborarli e il set di dati è sufficientemente piccolo da costruire in memoria, provare a usare un campo `repeated` anche se la creazione effettiva del set di dati in memoria nel server è più lenta.

## <a name="when-to-use-stream-methods"></a>Quando usare i metodi `stream`

I set di impostazioni in cui gli oggetti messaggio sono potenzialmente molto grandi vengono trasferiti in modo ottimale tramite richieste di streaming o risposte. È più efficiente costruire un oggetto di grandi dimensioni in memoria, scriverlo nella rete e quindi liberare le risorse. Questo approccio migliorerà la scalabilità del servizio.

Analogamente, i set di dati di dimensioni non vincolate devono essere inviati attraverso i flussi per evitare di esaurire la memoria durante la loro costruzione.

Per i set di impostazioni in cui ogni singolo elemento può essere elaborato separatamente dal consumer, è consigliabile usare un flusso se significa che lo stato di avanzamento può essere indicato all'utente finale. Questo potrebbe migliorare la velocità di risposta apparente di un'applicazione, sebbene questo debba essere bilanciato in base alle prestazioni complessive dell'applicazione.

Un altro scenario in cui i flussi possono essere utili è la posizione in cui un messaggio viene elaborato tra più servizi. Se ogni servizio in una catena restituisce un flusso, il servizio Terminal, ovvero l'ultimo nella catena, può iniziare a restituire messaggi che possono essere elaborati e passati di nuovo lungo la catena al richiedente originale, che può restituire un flusso o aggregare Restituisce un singolo messaggio di risposta. Questo approccio si presta bene a modelli come map/reduce.

>[!div class="step-by-step"]
>[Precedente](migrate-duplex-services.md)
>[Successivo](client-libraries.md)
