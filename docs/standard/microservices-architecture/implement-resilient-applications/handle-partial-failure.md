---
title: Gestione degli errori parziali
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Gestione degli errori parziali
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 957a0b1b8b4d217fac591db54e4ee053098bc7da
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2018
ms.locfileid: "37105195"
---
# <a name="handling-partial-failure"></a>Gestione degli errori parziali

Nei sistemi distribuiti come le applicazioni basate su microservizi, esiste un onnipresente rischio di errore parziale. Ad esempio, può verificarsi un errore in un singolo microservizio/contenitore oppure questo potrebbe non essere disponibile per rispondere per un breve periodo di tempo oppure può verificarsi un arresto anomalo di una macchina virtuale o di un server. Poiché i client e i servizi sono processi separati, un servizio potrebbe non riuscire a rispondere tempestivamente a una richiesta del client. Il servizio potrebbe essere sovraccarico e rispondere alle richieste con estrema lentezza oppure potrebbe semplicemente non essere accessibile per un breve periodo di tempo a causa di problemi di rete.

Si consideri ad esempio la pagina dei dettagli dell'ordine dell'applicazione di esempio eShopOnContainers. Se il microservizio degli ordini non risponde quando l'utente tenta di inviare un ordine, un'implementazione non corretta del processo client (l'applicazione Web MVC), se ad esempio il codice client usasse RPC sincrone senza timeout, bloccherebbe i thread a tempo indefinito in attesa di una risposta. Oltre a creare un'esperienza utente non corretta, ogni attesa senza risposta utilizza o blocca un thread e i thread sono estremamente preziosi nelle applicazioni a scalabilità elevata. Se molti thread sono bloccati, il runtime dell'applicazione alla fine li esaurirà. In questo caso, l'applicazione potrebbe non rispondere a livello globale anziché solo parzialmente, come mostrato nella figura 10-1.

![](./media/image1.png)

**Figura 10-1**. Errori parziali dovuti a dipendenze che influiscono sulla disponibilità dei thread del servizio

In applicazioni basate su microservizi di grandi dimensioni, ogni errore parziale può risultare amplificato, in particolare se la maggior parte dell'interazione tra i microservizi interni è basata su chiamate HTTP sincrone (scenario definito come antipattern). Si pensi a un sistema che riceve milioni di chiamate in ingresso al giorno. Se il sistema presenta una progettazione scarsa basata su lunghe catene di chiamate HTTP sincrone, le chiamate in ingresso potrebbero generare molti milioni di chiamate in uscita, si supponga un rapporto di 1:4, a dozzine di microservizi interni come dipendenze sincrone. La situazione è mostrata nella figura 10-2, in particolare per la dipendenza \#3.

![](./media/image2.png)

**Figura 10-2**. L'impatto di una progettazione non corretta che prevede lunghe catene di richieste HTTP

L'errore intermittente è virtualmente garantito in un sistema distribuito basato sul cloud, anche se ogni dipendenza presenta una disponibilità eccellente. Questo è un aspetto da prendere in considerazione.

Se non si progettano e implementano tecniche in grado di garantire la tolleranza di errore, anche brevi periodi di inattività possono risultare amplificati. Ad esempio, 50 dipendenze ognuna con una disponibilità del 99,99% genererebbero diverse ore di inattività al mese a causa dell'effetto domino. Quando si verifica un errore nella dipendenza di un microservizio durante la gestione di un volume elevato di richieste, l'errore può saturare velocemente tutti i thread delle richieste disponibili in ogni servizio e determinare un arresto anomalo dell'intera applicazione.

![](./media/image3.png)

**Figura 10-3**. Errore parziale amplificato da microservizi con lunghe catene di chiamate HTTP sincrone

Per ridurre al minimo l'impatto del problema, nella sezione "*L'integrazione di microservizi asincroni impone l'autonomia del microservizio*" del capitolo relativo all'architettura, si incoraggia l'uso della comunicazione asincrona tra i microservizi interni. Verranno fornite ulteriori spiegazioni nella sezione successiva.

Inoltre, è essenziale progettare i microservizi e le applicazioni client per la gestione degli errori parziali, ovvero creare microservizi e applicazioni client resilienti.


>[!div class="step-by-step"]
[Precedente](index.md)
[Successivo](partial-failure-strategies.md)
