---
title: Gestione degli errori parziali
description: Informazioni su come gestire correttamente gli errori parziali. Un microservizio potrebbe non essere completamente funzionale, ma essere comunque in grado di eseguire operazioni utili.
ms.date: 10/16/2018
ms.openlocfilehash: 0300719360e1a2500db0af8454c91fdfe2e5b09b
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "80988870"
---
# <a name="handle-partial-failure"></a>Gestire gli errori parziali

Nei sistemi distribuiti, come le applicazioni basate su microservizi, esiste sempre un rischio di errori parziali. Ad esempio, può verificarsi un errore in un singolo microservizio/contenitore oppure questo potrebbe non essere disponibile per rispondere per un breve periodo di tempo oppure può verificarsi un arresto anomalo di una macchina virtuale o di un server. Poiché i client e i servizi sono processi separati, un servizio potrebbe non essere in grado di rispondere in modo tempestivo alla richiesta di un client. Il servizio potrebbe essere sovraccarico e rispondere molto lentamente alle richieste oppure potrebbe semplicemente non essere accessibile per un breve periodo di tempo a causa di problemi di rete.

Si consideri ad esempio la pagina dei dettagli dell'ordine dell'applicazione di esempio eShopOnContainers. Se il microservizio degli ordini non risponde quando l'utente tenta di inviare un ordine, un'implementazione non corretta del processo client (l'applicazione Web MVC), se ad esempio il codice client usasse RPC sincrone senza timeout, bloccherebbe i thread a tempo indefinito in attesa di una risposta. Oltre a creare un'esperienza utente non corretta, ogni attesa senza risposta usa o blocca un thread e i thread sono estremamente preziosi nelle applicazioni a scalabilità elevata. Se sono presenti molti thread bloccati, il runtime dell'applicazione può esaurire i thread. In questo caso l'applicazione potrebbe non rispondere a livello globale anziché solo parzialmente, come illustrato nella figura 8-1.

![Diagramma che mostra gli errori parziali.](./media/handle-partial-failure/partial-failures-diagram.png)

**Figura 8-1**. Errori parziali dovuti a dipendenze che influiscono sulla disponibilità dei thread del servizio

In applicazioni basate su microservizi di grandi dimensioni, ogni errore parziale può risultare amplificato, in particolare se la maggior parte dell'interazione tra i microservizi interni è basata su chiamate HTTP sincrone (scenario definito come antipattern). Si pensi a un sistema che riceve milioni di chiamate in ingresso al giorno. Se il sistema ha una progettazione errata basata su lunghe catene di chiamate HTTP sincrone, queste chiamate in ingresso potrebbero comportare molti più milioni di chiamate in uscita (supponiamo un rapporto di 1:4) a decine di microservizi interni come dipendenze sincrone. Questa situazione è illustrata nella figura \#8-2, in particolare la dipendenza 3, che avvia una catena, chiamando le dipendenze #4. chiamate #5.

![Diagramma che mostra più dipendenze distribuite.](./media/handle-partial-failure/multiple-distributed-dependencies.png)

**Figura 8-2**. L'impatto di una progettazione non corretta che prevede lunghe catene di richieste HTTP

L'errore intermittente è garantito in un sistema distribuito basato sul cloud, anche se ogni dipendenza presenta una disponibilità eccellente. Questo è un aspetto da prendere in considerazione.

Se non si progettano e implementano tecniche in grado di garantire la tolleranza di errore, anche brevi periodi di inattività possono risultare amplificati. Ad esempio, 50 dipendenze ognuna con una disponibilità del 99,99% genererebbero diverse ore di inattività al mese a causa dell'effetto domino. Quando si verifica un errore nella dipendenza di un microservizio durante la gestione di un volume elevato di richieste, l'errore può saturare velocemente tutti i thread delle richieste disponibili in ogni servizio e determinare un arresto anomalo dell'intera applicazione.

![Diagramma che mostra un errore parziale amplificato nei microservizi.](./media/handle-partial-failure/partial-failure-amplified-microservices.png)

**Figura 8-3**. Errore parziale amplificato da microservizi con lunghe catene di chiamate HTTP sincrone

Per ridurre al minimo questo problema, nella sezione [L'integrazione asincrona dei microservizi impone l'autonomia dei microservizi,](../architect-microservice-container-applications/communication-in-microservice-architecture.md#asynchronous-microservice-integration-enforces-microservices-autonomy)questa guida incoraggia a utilizzare la comunicazione asincrona tra i microservizi interni.

È anche essenziale progettare i microservizi e le applicazioni client per la gestione degli errori parziali, ovvero creare microservizi e applicazioni client resilienti.

>[!div class="step-by-step"]
>[Successivo](index.md)
>[precedente](partial-failure-strategies.md)
