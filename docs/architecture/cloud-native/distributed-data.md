---
title: Dati distribuiti
description: Architettura di app .NET cloud native per Azure | Dati distribuiti per le app cloud native
ms.date: 06/30/2019
ms.openlocfilehash: 92086c52b02360e90461aea9ad23a2068224e187
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71183133"
---
# <a name="distributed-data-for-cloud-native-apps"></a>Dati distribuiti per app native del cloud

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Quando si crea un sistema nativo del cloud che è costituito da molti microservizi indipendenti, il modo in cui si pensa alle modifiche dell'archiviazione dei dati.

Le tradizionali applicazioni monolitiche favoriscono un archivio dati centralizzato illustrato nella figura 5-1. 

![Singolo database monolitico](./media/single-monolithic-database.png)

**Figura 5-1**. Singolo database monolitico

Si noti nella figura precedente il modo in cui tutti i componenti dell'applicazione utilizzano un solo database relazionale.

Questo approccio presenta molti vantaggi. È semplice eseguire query sui dati distribuiti in più tabelle ed è semplice implementare [transazioni ACID](https://docs.microsoft.com/windows/desktop/cossdk/acid-properties) che garantiscano la coerenza dei dati. Si finisce sempre con *coerenza immediata*, ovvero tutti gli aggiornamenti dei dati o nessuno di essi.

I sistemi nativi del cloud favoriscono un'architettura dei dati illustrata nella figura 5-2, in cui ogni microservizio è proprietario e incapsula i propri dati.

![Più database tra microservizi](./media/data-across-microservices.png)

**Figura 5-2**. Più database tra microservizi

Si noti come nella figura precedente ogni microservizio è proprietario e incapsula l'archivio dati it ed espone solo i dati al mondo esterno dall'API pubblica.
 
Questo modello consente a ogni microservizio di evolversi in modo indipendente senza dover coordinare le modifiche dello schema dei dati con altri microservizi. Ogni microservizio è libero di implementare il tipo di archivio dati (database relazionale, database di documenti, archivio chiave-valore) che meglio soddisfa le proprie esigenze. In fase di esecuzione, ogni microservizio può ridimensionare i propri dati di conseguenza. Questa operazione è illustrata nella figura 5-3:

![Persistenza dei dati poliglotta](./media/polyglot-data-persistence.png)

**Figura 5-3**. Persistenza dei dati poliglotta

Si noti che nella figura precedente i microservizi Catalogo prodotti e inventario adottano i database relazionali, il microservizio degli ordini, un database di documenti NoSql e il microservizio carrello acquisti, che è un archivio chiave-valore esterno. Sebbene i database relazionali rimangano rilevanti per i microservizi con dati complessi, i database NoSQL hanno acquisito una notevole popolarità, offrendo adattabilità, ricerca rapida e disponibilità elevata. La loro natura senza schema consente agli sviluppatori di uscire da un'architettura di classi di dati tipizzate e ORM che rendono la modifica costosa e dispendiosa in termini di tempo.

>[!div class="step-by-step"]
>[Precedente](service-mesh-communication-infrastructure.md)
>[Successivo](data-patterns.md)
