---
title: Appendice-gRPC per sviluppatori WCF
description: Discussione sulle transazioni distribuite e la relativa implementazione nelle architetture moderne di microservizi.
ms.date: 09/02/2019
ms.openlocfilehash: 061aef016fd0e4303e1bbcbf0e73cec2b0c54f74
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968211"
---
# <a name="appendix-a---transactions"></a>Appendice A-transazioni

Windows Communication Foundation (WCF) supportava le transazioni distribuite, consentendo l'esecuzione di operazioni atomiche su più servizi. Questa funzionalità è basata sul [Distributed Transaction Coordinator Microsoft](https://docs.microsoft.com/previous-versions/windows/desktop/ms684146(v=vs.85)).

Nel panorama dei microservizi moderni, questo tipo di elaborazione automatica delle transazioni distribuite non è possibile. Sono disponibili troppe tecnologie diverse, tra cui database relazionali, archivi dati NoSQL e sistemi di messaggistica, senza menzionare la combinazione di sistemi operativi, linguaggi di programmazione e Framework che possono essere utilizzati in un unico ambiente.

La transazione distribuita WCF è un'implementazione di ciò che è noto come [commit a due fasi (2PC)](https://en.wikipedia.org/wiki/Two-phase_commit_protocol). È possibile implementare manualmente le transazioni 2PC coordinando i messaggi tra i servizi, creando transazioni aperte all'interno di ogni servizio e inviando messaggi di "commit" o "rollback" a seconda dell'esito positivo o negativo. Tuttavia, la complessità interessata alla gestione di 2PC può aumentare in modo esponenziale con l'evolversi dei sistemi e le transazioni aperte contengono blocchi di database che possono influire negativamente sulle prestazioni o, peggio, causare deadlock tra servizi.

Se possibile, è preferibile evitare completamente le transazioni distribuite. Se due elementi di dati sono collegati in modo da richiedere aggiornamenti atomici, è consigliabile gestirli entrambi con lo stesso servizio e applicare tali modifiche atomiche utilizzando una singola richiesta o messaggio al servizio.

Se ciò non è possibile, un'alternativa consiste nell'usare il [modello saga](https://microservices.io/patterns/data/saga.html). In una saga gli aggiornamenti vengono elaborati in sequenza; Poiché ogni aggiornamento ha esito positivo, viene attivato quello successivo. Questi trigger possono essere propagati dal servizio al servizio o gestiti da un coordinatore della saga o da un "agente di orchestrazione". Se un aggiornamento non riesce in qualsiasi momento durante il processo, i servizi che hanno già completato gli aggiornamenti applicano una logica specifica per invertirli.

Un'altra opzione prevede l'uso della progettazione basata su domini (DDD) e della separazione di responsabilità di Command/query (CQRS), come descritto nell' [e-book di microservizi .NET](https://docs.microsoft.com/dotnet/architecture/microservices/microservice-ddd-cqrs-patterns/). In particolare, l'uso di eventi del dominio o di origine [eventi](https://martinfowler.com/eaaDev/EventSourcing.html) può contribuire a garantire che gli aggiornamenti siano costantemente&mdash;se non&mdash;applicati immediatamente.

>[!div class="step-by-step"]
>[Precedente](application-performance-management.md)
