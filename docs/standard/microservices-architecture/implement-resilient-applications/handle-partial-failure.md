---
title: Gestione degli errori parziali
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Gestione degli errori parziali
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: b7d16acf3de2d395da70e8f46e59c129dec24f71
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="handling-partial-failure"></a>Gestione degli errori parziali

In sistemi distribuiti, ad esempio le applicazioni basate su microservizi, c'è un rischio più di un errore parziale. Ad esempio, un singolo microservizio/contenitore può avere esito negativo o potrebbe non essere disponibile per rispondere per un breve periodo di tempo oppure una singola macchina virtuale o server può arrestarsi in modo anomalo. Poiché i client e servizi sono processi separati, un servizio potrebbe non essere in grado di rispondere in modo tempestivo a una richiesta del client. Il servizio potrebbe essere in overload e che risponde solo molto lentamente a richieste o può non essere accessibile per un breve periodo di tempo a causa di problemi di rete.

Si consideri ad esempio la pagina Dettagli ordine il eShopOnContainers applicazione di esempio. Se l'ordinamento microservizio non risponde quando l'utente tenta di inviare un ordine, un'implementazione non valida del processo client (l'applicazione web MVC), ad esempio, se il codice client utilizza RPC sincrona senza alcun timeout, ovvero Blocca thread per un periodo illimitato in attesa di una risposta. Oltre a creare un'esperienza utente errati, ogni attesa risponda utilizza o blocca un thread e i thread sono estremamente utili per applicazioni estremamente scalabili. Se sono presenti numerosi thread bloccati, il runtime dell'applicazione può eseguire esaurimento. In tal caso, l'applicazione potrebbe smettere di rispondere a livello globale anziché solo parzialmente non risponde, come illustrato nella figura 10-1.

![](./media/image1.png)

**Nella figura 10-1**. Le conversioni non riuscite a causa delle dipendenze impatto sulla disponibilità di thread del servizio

In un'applicazione basata su microservizi grandi dimensioni, qualsiasi errore parziale può essere ampliate, soprattutto se la maggior parte dell'interazione microservizi interno si basa sulle chiamate HTTP sincrone (che è considerata un anti-pattern). Considerare un sistema che riceve milioni di chiamate in ingresso al giorno. Se il sistema dispone di una struttura non valida che si basa sul lunghe catene di chiamate HTTP sincrone, queste chiamate in ingresso potrebbero comportare molti milioni di chiamate in uscita (si supponga un rapporto 1:4) a decine di microservizi interno come dipendenze sincrone. Questa situazione è illustrata nella figura 10-2, soprattutto dipendenza \#3.

![](./media/image2.png)

**Figura 10-2**. L'impatto della presenza di una progettazione corretta con lunghe catene di richieste HTTP

Interruzione intermittente è praticamente garantita in distribuito e cloud sistema basato su, anche se dispone di tutte le dipendenze stesso disponibilità eccellente. Deve trattarsi di un fatto, che è necessario prendere in considerazione.

Se non si progettare e implementare le tecniche per garantire la tolleranza di errore, è possibile amplificate anche tempi di inattività. Ad esempio, 50 dipendenze ogni con 99,99% di disponibilità comporta diverse ore di inattività ogni mese a causa di questo effetto ripple. Quando una dipendenza microservizio ha esito negativo durante la gestione di un volume elevato di richieste, questo tipo di errore possono rapidamente saturare tutti i thread di richiesta disponibili in ogni servizio e di arresto anomalo dell'intera applicazione.

![](./media/image3.png)

**Nella figura 10-3**. Errore parziale amplificato da microservizi con lunghe catene di chiamate HTTP sincrone

Per ridurre al minimo questo problema, nella sezione "*microservizio asincrona integrazione imporre l'autonomia del microservizio*" (nel capitolo architecture), è possibile usare la comunicazione asincrona tra interno è sconsigliato microservizi. Viene brevemente descritto più nella sezione successiva.

Inoltre, è fondamentale progettare le applicazioni di microservizi e client per gestire gli errori parziali, vale a dire, delle applicazioni microservizi resilienti e client.


>[!div class="step-by-step"]
[Precedente] [Avanti] (parziale-errore-strategies.md) (index.md)
