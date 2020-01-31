---
title: Resilienza cloud nativa
description: Architettura di app .NET cloud native per Azure | Resilienza nativa del cloud
ms.date: 06/30/2019
ms.openlocfilehash: 427405d95534c4467ab519c2188fe88e2f18e2b2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76781091"
---
# <a name="cloud-native-resiliency"></a>Resilienza cloud nativa

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

La resilienza è la capacità del sistema di reagire agli errori e rimane comunque funzionante. Non è per evitare errori. Tuttavia, l'accettazione di tale errore è inevitabile nei sistemi basati sul cloud e la creazione dell'applicazione per rispondere. L'obiettivo finale della resilienza consiste nel riportare l'applicazione a uno stato completamente funzionante dopo un errore.

Diversamente dalle tradizionali applicazioni monolitiche, in cui tutto viene eseguito insieme in un unico processo, i sistemi nativi del cloud adottano l'architettura distribuita, come illustrato nella figura 6-1:

![Ambiente nativo cloud distribuito](./media/distributed-cloud-native-environment.png)

**Figura 6-1.** Ambiente nativo cloud distribuito

Nella figura precedente si noti come ogni client, microservizio e [servizio di backup](https://12factor.net/backing-services) basato su cloud viene eseguito come processo separato, in esecuzione su server diversi, tutti comunicanti tramite chiamate basate su rete.

Quindi, cosa potrebbe andare male?

- [Latenza di rete](https://www.techopedia.com/definition/8553/network-latency)imprevista.
- Errori [temporanei (errori](https://docs.microsoft.com/azure/architecture/best-practices/transient-faults) di connettività di rete temporanei).
- Blocco mediante un'operazione sincrona a esecuzione prolungata.
- Un processo host che si è arrestato in modo anomalo e verrà riavviato o spostato.
- Un microservizio di overload che non può rispondere per un breve periodo di tempo.
- Operazione DevOps in corso, ad esempio un'operazione di aggiornamento o di ridimensionamento.
- Operazione dell'agente di orchestrazione, ad esempio lo trasferimento di un servizio da un nodo a un altro.
- Errori hardware dall'hardware di base.

Quando si distribuiscono servizi distribuiti nell'infrastruttura basata su cloud, i fattori dell'elenco precedente diventano molto reali ed è necessario progettare e sviluppare in modo difensivo per gestirli.

In un sistema distribuito su scala ridotta, l'errore sarà meno frequente, ma con l'aumentare delle prestazioni del sistema, è possibile che si verifichino più problemi a un punto in cui un errore parziale diventa il normale funzionamento.

Pertanto, l'applicazione e l'infrastruttura devono essere resilienti. Nelle sezioni seguenti verranno illustrate le tecniche difensive che è possibile aggiungere all'applicazione e le funzionalità cloud integrate che è possibile utilizzare per consentire l'uso dell'esperienza utente da parte di Bullet.

>[!div class="step-by-step"]
>[Precedente](elastic-search-in-azure.md)
>[Successivo](application-resiliency-patterns.md)
