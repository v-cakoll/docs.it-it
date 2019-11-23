---
title: Dati distribuiti
description: Architettura di app .NET cloud native per Azure | Dati distribuiti per le app cloud native
ms.date: 06/30/2019
ms.openlocfilehash: b715ae5203264a023bc9f911aa74ee222afe3d68
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73087445"
---
# <a name="distributed-data-for-cloud-native-apps"></a><span data-ttu-id="cea61-103">Dati distribuiti per app native del cloud</span><span class="sxs-lookup"><span data-stu-id="cea61-103">Distributed data for cloud-native apps</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="cea61-104">Quando si crea un sistema nativo del cloud che è costituito da molti microservizi indipendenti, il modo in cui si pensa alle modifiche dell'archiviazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="cea61-104">When constructing a cloud-native system that consists of many independent microservices, the way you think about data storage changes.</span></span>

<span data-ttu-id="cea61-105">Le tradizionali applicazioni monolitiche favoriscono un archivio dati centralizzato illustrato nella figura 5-1.</span><span class="sxs-lookup"><span data-stu-id="cea61-105">Traditional monolithic applications favor a centralized data store shown in Figure 5-1.</span></span>

![Singolo database monolitico](./media/single-monolithic-database.png)

<span data-ttu-id="cea61-107">**Figura 5-1**.</span><span class="sxs-lookup"><span data-stu-id="cea61-107">**Figure 5-1**.</span></span> <span data-ttu-id="cea61-108">Singolo database monolitico</span><span class="sxs-lookup"><span data-stu-id="cea61-108">Single monolithic database</span></span>

<span data-ttu-id="cea61-109">Si noti nella figura precedente il modo in cui tutti i componenti dell'applicazione utilizzano un solo database relazionale.</span><span class="sxs-lookup"><span data-stu-id="cea61-109">Note in the previous figure how all of the application components consume a single relational database.</span></span>

<span data-ttu-id="cea61-110">Questo approccio presenta molti vantaggi.</span><span class="sxs-lookup"><span data-stu-id="cea61-110">There are many benefits to this approach.</span></span> <span data-ttu-id="cea61-111">È semplice eseguire query sui dati distribuiti in più tabelle ed è semplice implementare [transazioni ACID](https://docs.microsoft.com/windows/desktop/cossdk/acid-properties) che garantiscano la coerenza dei dati.</span><span class="sxs-lookup"><span data-stu-id="cea61-111">It's straightforward to query data spread across  multiple tables, and it's straightforward to implement [ACID transactions](https://docs.microsoft.com/windows/desktop/cossdk/acid-properties) that ensure data consistency.</span></span> <span data-ttu-id="cea61-112">Si finisce sempre con *coerenza immediata*, ovvero tutti gli aggiornamenti dei dati o nessuno di essi.</span><span class="sxs-lookup"><span data-stu-id="cea61-112">You always end up with *immediate consistency*: either all your data updates or none of it does.</span></span>

<span data-ttu-id="cea61-113">I sistemi nativi del cloud favoriscono un'architettura dei dati illustrata nella figura 5-2, in cui ogni microservizio è proprietario e incapsula i propri dati.</span><span class="sxs-lookup"><span data-stu-id="cea61-113">Cloud-native systems favor a data architecture shown in Figure 5-2 in which each microservice owns and encapsulates its own data.</span></span>

![Più database tra microservizi](./media/data-across-microservices.png)

<span data-ttu-id="cea61-115">**Figura 5-2**.</span><span class="sxs-lookup"><span data-stu-id="cea61-115">**Figure 5-2**.</span></span> <span data-ttu-id="cea61-116">Più database tra microservizi</span><span class="sxs-lookup"><span data-stu-id="cea61-116">Multiple databases across microservices</span></span>

<span data-ttu-id="cea61-117">Si noti come nella figura precedente ogni microservizio è proprietario e incapsula l'archivio dati it ed espone solo i dati al mondo esterno dall'API pubblica.</span><span class="sxs-lookup"><span data-stu-id="cea61-117">Note how in the previous figure each microservice owns and encapsulates it data store and only exposes data to the outside world from its public API.</span></span>

<span data-ttu-id="cea61-118">Questo modello consente a ogni microservizio di evolversi in modo indipendente senza dover coordinare le modifiche dello schema dei dati con altri microservizi.</span><span class="sxs-lookup"><span data-stu-id="cea61-118">This model enables each microservice to evolve independently without having to coordinate data schema changes with other microservices.</span></span> <span data-ttu-id="cea61-119">Ogni microservizio è libero di implementare il tipo di archivio dati (database relazionale, database di documenti, archivio chiave-valore) che meglio soddisfa le proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="cea61-119">Each microservice is free to implement the data store (relational database, document database, key-value store) type that best matches its needs.</span></span> <span data-ttu-id="cea61-120">In fase di esecuzione, ogni microservizio può ridimensionare i propri dati di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="cea61-120">At runtime, each microservice can scale its data accordingly.</span></span> <span data-ttu-id="cea61-121">Questa operazione è illustrata nella figura 5-3:</span><span class="sxs-lookup"><span data-stu-id="cea61-121">This is shown in Figure 5-3:</span></span>

![Persistenza dei dati poliglotta](./media/polyglot-data-persistence.png)

<span data-ttu-id="cea61-123">**Figura 5-3**.</span><span class="sxs-lookup"><span data-stu-id="cea61-123">**Figure 5-3**.</span></span> <span data-ttu-id="cea61-124">Persistenza dei dati poliglotta</span><span class="sxs-lookup"><span data-stu-id="cea61-124">Polyglot data persistence</span></span>

<span data-ttu-id="cea61-125">Si noti che nella figura precedente i microservizi Catalogo prodotti e inventario adottano i database relazionali, il microservizio degli ordini, un database di documenti NoSql e il microservizio carrello acquisti, che è un archivio chiave-valore esterno.</span><span class="sxs-lookup"><span data-stu-id="cea61-125">Note how in the previous figure the product catalog and inventory microservices adopt relational databases, the ordering microservice, a NoSql document database, and the shopping cart microservice, which is an external key-value store.</span></span> <span data-ttu-id="cea61-126">Sebbene i database relazionali rimangano rilevanti per i microservizi con dati complessi, i database NoSQL hanno acquisito una notevole popolarità, offrendo adattabilità, ricerca rapida e disponibilità elevata.</span><span class="sxs-lookup"><span data-stu-id="cea61-126">While relational databases remain relevant for microservices with complex data, NoSQL databases have gained considerable popularity, providing adaptability, fast lookup, and high availability.</span></span> <span data-ttu-id="cea61-127">La loro natura senza schema consente agli sviluppatori di uscire da un'architettura di classi di dati tipizzate e ORM che rendono la modifica costosa e dispendiosa in termini di tempo.</span><span class="sxs-lookup"><span data-stu-id="cea61-127">Their schemaless nature allows developers to move away from an architecture of typed data classes and ORMs that make change expensive and time-consuming.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="cea61-128">[Precedente](service-mesh-communication-infrastructure.md)
>[Successivo](data-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="cea61-128">[Previous](service-mesh-communication-infrastructure.md)
[Next](data-patterns.md)</span></span>
