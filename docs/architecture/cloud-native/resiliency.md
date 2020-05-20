---
title: Resilienza cloud nativa
description: Architettura di app .NET cloud native per Azure | Resilienza nativa del cloud
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: f3aa89e3ae21b13a31f65013b59636b3f931553c
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83613772"
---
# <a name="cloud-native-resiliency"></a>Resilienza cloud nativa

La resilienza è la capacità del sistema di reagire agli errori e rimane comunque funzionante. Non si tratta di evitare errori, ma di accettare un errore e costruire i servizi nativi del cloud per rispondervi. Si vuole tornare a uno stato completamente funzionante più rapidamente possibile.

Diversamente dalle tradizionali applicazioni monolitiche, in cui tutto viene eseguito insieme in un unico processo, i sistemi nativi del cloud adottano un'architettura distribuita, come illustrato nella figura 6-1:

![Ambiente nativo cloud distribuito](./media/distributed-cloud-native-environment.png)

**Figura 6-1.** Ambiente nativo cloud distribuito

Nella figura precedente ogni microservizio e [servizio di backup](https://12factor.net/backing-services) basato sul cloud vengono eseguiti in un processo separato, attraverso l'infrastruttura server, comunicando tramite chiamate basate su rete.

Operando in questo ambiente, un servizio deve essere sensibile a molti problemi diversi:

- Latenza di rete imprevista: tempo impiegato da una richiesta di servizio per il trasferimento al ricevitore e viceversa.

- Errori [temporanei](https://docs.microsoft.com/azure/architecture/best-practices/transient-faults) : errori di connettività di rete di breve durata.

- Blocco mediante un'operazione sincrona a esecuzione prolungata.

- Un processo host che si è arrestato in modo anomalo e verrà riavviato o spostato.

- Un microservizio di overload che non può rispondere per un breve periodo di tempo.

- Operazione dell'agente di orchestrazione in corso, ad esempio un aggiornamento in sequenza o lo scorrimento di un servizio da un nodo a un altro.

- Errori hardware.

Le piattaforme cloud possono rilevare e mitigare molti di questi problemi di infrastruttura. Il servizio può essere riavviato, ridimensionato e persino ridistribuito in un altro nodo.  Tuttavia, per sfruttare tutti i vantaggi di questa protezione incorporata, è necessario progettare i servizi in modo che reagisca e prosperino in questo ambiente dinamico.

Nelle sezioni seguenti verranno esaminate le tecniche difensive che il servizio e le risorse cloud gestite possono sfruttare per ridurre al minimo i tempi di inattività e le interruzioni.

>[!div class="step-by-step"]
>[Precedente](elastic-search-in-azure.md) 
> [Avanti](application-resiliency-patterns.md)
