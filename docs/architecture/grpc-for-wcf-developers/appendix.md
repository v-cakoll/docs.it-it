---
title: Appendice-gRPC per sviluppatori WCF
description: Discussione sulle transazioni distribuite e la relativa implementazione nelle architetture moderne di microservizi.
ms.date: 09/02/2019
ms.openlocfilehash: 9931681727f921e007c2f80852ad0e69cd7288de
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711475"
---
# <a name="appendix-a---transactions"></a>Appendice A-transazioni

Windows Communication Foundation (WCF) supporta le transazioni distribuite, consentendo di eseguire operazioni atomiche su più servizi. Questa funzionalità è basata sul [Distributed Transaction Coordinator Microsoft](https://docs.microsoft.com/previous-versions/windows/desktop/ms684146(v=vs.85)).

Nel panorama dei microservizi più recenti, questo tipo di elaborazione automatica delle transazioni distribuite non è possibile. Sono presenti troppe tecnologie diverse, tra cui database relazionali, archivi dati NoSQL e sistemi di messaggistica. Potrebbe inoltre essere presente una combinazione di sistemi operativi, linguaggi di programmazione e Framework in uso in un unico ambiente.

La transazione distribuita WCF è un'implementazione di ciò che è noto come [commit a due fasi (2PC)](https://en.wikipedia.org/wiki/Two-phase_commit_protocol). È possibile implementare le transazioni 2PC manualmente coordinando i messaggi tra i servizi, creando transazioni aperte all'interno di ogni servizio e inviando messaggi di commit o rollback, a seconda dell'esito positivo o negativo. Tuttavia, la complessità legata alla gestione di 2PC può aumentare esponenzialmente Man mano che i sistemi evolvono. Le transazioni aperte contengono blocchi di database che possono influire negativamente sulle prestazioni o, peggio, causare deadlock tra servizi.

Se possibile, è preferibile evitare completamente le transazioni distribuite. Se due elementi di dati sono collegati in modo da richiedere aggiornamenti atomici, è consigliabile gestirli entrambi con lo stesso servizio. Applicare tali modifiche atomiche utilizzando una singola richiesta o messaggio al servizio.

Se ciò non è possibile, un'alternativa consiste nell'usare il [modello saga](https://microservices.io/patterns/data/saga.html). In una saga gli aggiornamenti vengono elaborati in sequenza; Quando ogni aggiornamento ha esito positivo, viene attivato quello successivo. Questi trigger possono essere propagati dal servizio al servizio o gestiti da un coordinatore della saga o da un agente di orchestrazione. Se un aggiornamento non riesce in qualsiasi momento durante il processo, i servizi che hanno già completato gli aggiornamenti applicano una logica specifica per invertirli.

Un'altra opzione prevede l'uso della progettazione basata su domini (DDD) e della separazione di responsabilità di Command/query (CQRS), come descritto nell' [e-book di microservizi .NET](https://docs.microsoft.com/dotnet/architecture/microservices/microservice-ddd-cqrs-patterns/). In particolare, l'uso di eventi del dominio o di origine [eventi](https://martinfowler.com/eaaDev/EventSourcing.html) può contribuire a garantire che gli aggiornamenti siano coerenti, se non immediatamente applicati.

>[!div class="step-by-step"]
>[Precedente](application-performance-management.md)
