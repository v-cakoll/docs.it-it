---
title: Panoramica della programmazione asincrona
description: Informazioni che illustrano che la programmazione asincrona è una tecnica fondamentale che semplifica la gestione di pesanti operazioni I/O simultanee su diversi core.
author: cartermp
ms.author: wiwagn
ms.date: 06/20/2016
ms.technology: dotnet-standard
ms.assetid: 1e38e9d9-8284-46ee-a15f-199adc4f26f4
ms.openlocfilehash: d649bc3a92d3bb834b3bc4f7d3c1bcb0f9417375
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "78159728"
---
# <a name="async-overview"></a><span data-ttu-id="162fe-103">Panoramica della programmazione asincrona</span><span class="sxs-lookup"><span data-stu-id="162fe-103">Async Overview</span></span>

<span data-ttu-id="162fe-104">Fino a non molto tempo fa, per avere app più veloci bastava acquistare un nuovo PC o server. Ad un certo punto, però, questa tendenza si è fermata.</span><span class="sxs-lookup"><span data-stu-id="162fe-104">Not so long ago, apps got faster simply by buying a newer PC or server and then that trend stopped.</span></span> <span data-ttu-id="162fe-105">Anzi, si è invertita.</span><span class="sxs-lookup"><span data-stu-id="162fe-105">In fact, it reversed.</span></span> <span data-ttu-id="162fe-106">Sono comparsi telefoni cellulari con chip ARM a core singolo da 1ghz e i carichi di lavoro dei server si sono spostati sulle macchine virtuali.</span><span class="sxs-lookup"><span data-stu-id="162fe-106">Mobile phones appeared with 1ghz single core ARM chips and server workloads transitioned to VMs.</span></span> <span data-ttu-id="162fe-107">Gli utenti vogliono interfacce a velocità di risposta elevata e i titolari di business vogliono server scalabili in base alle loro attività aziendali.</span><span class="sxs-lookup"><span data-stu-id="162fe-107">Users still want responsive UI and business owners want servers that scale with their business.</span></span> <span data-ttu-id="162fe-108">Il passaggio ai dispositivi mobili e cloud e una popolazione connessa a Internet che ormai supera i 3 miliardi di utenti, hanno avuto come risultato lo sviluppo di nuovi modelli di software.</span><span class="sxs-lookup"><span data-stu-id="162fe-108">The transition to mobile and cloud and an internet-connected population of >3B users has resulted in a new set of software patterns.</span></span>

- <span data-ttu-id="162fe-109">Ci si aspetta che le applicazioni client siano sempre attive, sempre connesse e costantemente reattive all'interazione dell'utente, ad esempio al tocco, con valutazioni dell'archivio applicazioni sempre ottime.</span><span class="sxs-lookup"><span data-stu-id="162fe-109">Client applications are expected to be always-on, always-connected and constantly responsive to user interaction (for example, touch) with high app store ratings!</span></span>
- <span data-ttu-id="162fe-110">Ci si attende dai servizi che sappiano gestire i picchi di traffico scalando verticalmente e orizzontalmente senza intoppi.</span><span class="sxs-lookup"><span data-stu-id="162fe-110">Services are expected to handle spikes in traffic by gracefully scaling up and down.</span></span>

<span data-ttu-id="162fe-111">La programmazione asincrona è una tecnica fondamentale che semplifica la gestione di pesanti operazioni I/O simultanee su diversi core.</span><span class="sxs-lookup"><span data-stu-id="162fe-111">Async programming is a key technique that makes it straightforward to handle blocking I/O and concurrent operations on multiple cores.</span></span> <span data-ttu-id="162fe-112">.NET offre la possibilità per le app e i servizi di essere reattivi ed elastici con modelli di programmazione asincrona di facile utilizzo a livello di linguaggio in C, Visual Basic e F.</span><span class="sxs-lookup"><span data-stu-id="162fe-112">.NET provides the capability for apps and services to be responsive and elastic with easy-to-use, language-level asynchronous programming models in C#, Visual Basic, and F#.</span></span>

## <a name="why-write-async-code"></a><span data-ttu-id="162fe-113">Perché scrivere codice asincrono?</span><span class="sxs-lookup"><span data-stu-id="162fe-113">Why Write Async Code?</span></span>

<span data-ttu-id="162fe-114">Le app moderne fanno un uso intensivo di I/O file e rete.</span><span class="sxs-lookup"><span data-stu-id="162fe-114">Modern apps make extensive use of file and networking I/O.</span></span> <span data-ttu-id="162fe-115">Le API I/O solitamente si bloccano per impostazione predefinita, con conseguenti esperienze utente e uso dell'hardware poco soddisfacenti, a meno che non si voglia imparare a usare modelli complessi.</span><span class="sxs-lookup"><span data-stu-id="162fe-115">I/O APIs traditionally block by default, resulting in poor user experiences and hardware utilization unless you want to learn and use challenging patterns.</span></span> <span data-ttu-id="162fe-116">Le API asincrone basate su attività e il modello di programmazione asincrona a livello di linguaggio invertono questa tendenza, rendendo l'esecuzione asincrona predefinita, con pochi concetti nuovi da apprendere.</span><span class="sxs-lookup"><span data-stu-id="162fe-116">Task-based async APIs and the language-level asynchronous programming model invert this model, making async execution the default with few new concepts to learn.</span></span>

<span data-ttu-id="162fe-117">Il codice asincrono ha le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="162fe-117">Async code has the following characteristics:</span></span>

- <span data-ttu-id="162fe-118">Gestisce più richieste server cedendo i thread per gestire più richieste durante l'attesa del ritorno delle richieste I/O.</span><span class="sxs-lookup"><span data-stu-id="162fe-118">Handles more server requests by yielding threads to handle more requests while waiting for I/O requests to return.</span></span>
- <span data-ttu-id="162fe-119">Consente alle interfacce utente di essere più reattive, cedendo thread all'interazione dell'interfaccia utente durante l'attesa delle richieste I/O e spostando le attività con esecuzione prolungata ad altri core della CPU.</span><span class="sxs-lookup"><span data-stu-id="162fe-119">Enables UIs to be more responsive by yielding threads to UI interaction while waiting for I/O requests and by transitioning long-running work to other CPU cores.</span></span>
- <span data-ttu-id="162fe-120">Molte delle API di .NET più recenti sono asincrone.</span><span class="sxs-lookup"><span data-stu-id="162fe-120">Many of the newer .NET APIs are asynchronous.</span></span>
- <span data-ttu-id="162fe-121">Scrivere codice asincrono in .NET è facile.</span><span class="sxs-lookup"><span data-stu-id="162fe-121">It's easy to write async code in .NET!</span></span>

## <a name="whats-next"></a><span data-ttu-id="162fe-122">Quali sono le operazioni successive?</span><span class="sxs-lookup"><span data-stu-id="162fe-122">What's next?</span></span>

<span data-ttu-id="162fe-123">Per altre informazioni, vedere l'argomento [La programmazione asincrona in dettaglio](async-in-depth.md).</span><span class="sxs-lookup"><span data-stu-id="162fe-123">For more information, see the [Async in depth](async-in-depth.md) topic.</span></span>

<span data-ttu-id="162fe-124">L'argomento [Modelli di programmazione asincrona](asynchronous-programming-patterns/index.md) offre una panoramica dei tre modelli di programmazione asincroni supportati in .NET:</span><span class="sxs-lookup"><span data-stu-id="162fe-124">The [Asynchronous Programming Patterns](asynchronous-programming-patterns/index.md) topic provides an overview of the three asynchronous programming patterns supported in .NET:</span></span>  
  
- <span data-ttu-id="162fe-125">[Asynchronous Programming Model (APM)](asynchronous-programming-patterns/asynchronous-programming-model-apm.md) (Modello di programmazione asincrona, APM - legacy)</span><span class="sxs-lookup"><span data-stu-id="162fe-125">[Asynchronous Programming Model (APM)](asynchronous-programming-patterns/asynchronous-programming-model-apm.md) (legacy)</span></span>  
  
- <span data-ttu-id="162fe-126">[Event-based Asynchronous Pattern (EAP)](asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) (Modello asincrono basato su eventi - legacy)</span><span class="sxs-lookup"><span data-stu-id="162fe-126">[Event-based Asynchronous Pattern (EAP)](asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) (legacy)</span></span>  
  
- <span data-ttu-id="162fe-127">[Task-based Asynchronous Pattern (TAP)](asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) (Modello asincrono basato su attività - Consigliato per nuove attività di sviluppo)</span><span class="sxs-lookup"><span data-stu-id="162fe-127">[Task-based Asynchronous Pattern (TAP)](asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) (recommended for new development)</span></span>  

<span data-ttu-id="162fe-128">Per altre informazioni sul modello di programmazione basato su attività consigliato, vedere l'argomento [Programmazione asincrona basata su attività](parallel-programming/task-based-asynchronous-programming.md).</span><span class="sxs-lookup"><span data-stu-id="162fe-128">For more information about recommended task-based programming model, see the [Task-based asynchronous programming](parallel-programming/task-based-asynchronous-programming.md) topic.</span></span>
