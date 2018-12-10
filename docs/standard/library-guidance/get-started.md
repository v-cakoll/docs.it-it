---
title: Introduzione alla creazione di librerie .NET di alto livello
description: Introduzione alla compilazione di librerie .NET.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 05466de1469fc765570b8250301e8404cd5df173
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53145725"
---
# <a name="get-started"></a><span data-ttu-id="b33e6-103">Introduzione</span><span class="sxs-lookup"><span data-stu-id="b33e6-103">Get started</span></span>

## <a name="cross-platform-targetingcross-platform-targetingmd"></a>[<span data-ttu-id="b33e6-104">Supporto multipiattaforma</span><span class="sxs-lookup"><span data-stu-id="b33e6-104">Cross-platform targeting</span></span>](./cross-platform-targeting.md)

<span data-ttu-id="b33e6-105">Come usare .NET Standard e il multitargeting per creare librerie multipiattaforma.</span><span class="sxs-lookup"><span data-stu-id="b33e6-105">How to use .NET Standard and multi-targeting to create cross-platform libraries.</span></span> <span data-ttu-id="b33e6-106">.NET viene eseguito in molte posizioni e le librerie .NET di un buon livello devono cercare di supportare il maggior numero possibile di piattaforme e sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="b33e6-106">.NET runs in many places, and good .NET libraries should strive to support as many platforms and developers as possible.</span></span>

## <a name="strong-namingstrong-namingmd"></a>[<span data-ttu-id="b33e6-107">Denominazione sicura</span><span class="sxs-lookup"><span data-stu-id="b33e6-107">Strong naming</span></span>](./strong-naming.md)

<span data-ttu-id="b33e6-108">Vengono fornite informazioni sui nomi sicuri e sui loro vantaggi e svantaggi.</span><span class="sxs-lookup"><span data-stu-id="b33e6-108">Learn about strong naming and its advantages and disadvantages.</span></span> <span data-ttu-id="b33e6-109">La scelta di un nome sicuro per una libreria .NET consente alla maggior parte degli sviluppatori di usare la libreria ed è una procedura consigliata.</span><span class="sxs-lookup"><span data-stu-id="b33e6-109">Strong naming a .NET library allows the most developers to use it and is a recommended best practice.</span></span>

## <a name="nuget-and-open-source-librariesnugetmd"></a>[<span data-ttu-id="b33e6-110">Librerie open source e NuGet</span><span class="sxs-lookup"><span data-stu-id="b33e6-110">NuGet and open-source libraries</span></span>](./nuget.md)

<span data-ttu-id="b33e6-111">Il modo migliore per creare pacchetti NuGet per le librerie .NET open source, inclusi i metadati consigliati per tutti i pacchetti pubblicati in NuGet.org.</span><span class="sxs-lookup"><span data-stu-id="b33e6-111">The best way to create NuGet packages for open-source .NET libraries, including recommended metadata for all packages published publicly on NuGet.org.</span></span>

### <a name="dependenciesdependenciesmd"></a>[<span data-ttu-id="b33e6-112">Dipendenze</span><span class="sxs-lookup"><span data-stu-id="b33e6-112">Dependencies</span></span>](./dependencies.md)

<span data-ttu-id="b33e6-113">NuGet semplifica l'uso di pacchetti esistenti quando si esegue la compilazione di una libreria .NET.</span><span class="sxs-lookup"><span data-stu-id="b33e6-113">NuGet makes it easy to use existing packages when building a .NET library.</span></span> <span data-ttu-id="b33e6-114">Vengono fornite informazioni sulle cause comuni dei problemi relativi alle dipendenze NuGet e su come evitare che si verifichino.</span><span class="sxs-lookup"><span data-stu-id="b33e6-114">Learn about NuGet dependencies' common sources of friction and how to avoid them.</span></span>

### <a name="sourcelinksourcelinkmd"></a>[<span data-ttu-id="b33e6-115">SourceLink</span><span class="sxs-lookup"><span data-stu-id="b33e6-115">SourceLink</span></span>](./sourcelink.md)

<span data-ttu-id="b33e6-116">SourceLink è uno strumento straordinario che consente agli utenti della libreria .NET di esaminare il codice sorgente durante il debug.</span><span class="sxs-lookup"><span data-stu-id="b33e6-116">SourceLink is a great tool that allows users of your .NET library to step into its source code while debugging.</span></span> <span data-ttu-id="b33e6-117">Questo articolo fornisce una panoramica di SourceLink e spiega perché è consigliabile usare questo strumento.</span><span class="sxs-lookup"><span data-stu-id="b33e6-117">This article is an overview of what SourceLink is and why you should use it.</span></span>

### <a name="publishingpublish-nuget-packagemd"></a>[<span data-ttu-id="b33e6-118">Pubblicazione</span><span class="sxs-lookup"><span data-stu-id="b33e6-118">Publishing</span></span>](./publish-nuget-package.md)

<span data-ttu-id="b33e6-119">Anche se NuGet.org è il repository più noto e più usato, ci sono molte posizioni in cui pubblicare i pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="b33e6-119">While NuGet.org is the most widely known and used repository, there are many places to publish NuGet packages.</span></span> <span data-ttu-id="b33e6-120">Vengono fornite informazioni sui diversi repository di pacchetti NuGet disponibili e sulle procedure consigliate per la sicurezza per la pubblicazione di una libreria .NET.</span><span class="sxs-lookup"><span data-stu-id="b33e6-120">Learn about the different NuGet package repositories available, and security best practices for publishing a .NET library.</span></span>

## <a name="versioningversioningmd"></a>[<span data-ttu-id="b33e6-121">Controllo delle versioni</span><span class="sxs-lookup"><span data-stu-id="b33e6-121">Versioning</span></span>](./versioning.md)

<span data-ttu-id="b33e6-122">Le librerie .NET di buon livello si evolvono nel tempo, con l'aggiunta di funzionalità, la correzione di bug e il miglioramento delle prestazioni nelle versioni successive.</span><span class="sxs-lookup"><span data-stu-id="b33e6-122">Good .NET libraries evolve over time, adding features, fixing bugs, and improving performance in later releases.</span></span> <span data-ttu-id="b33e6-123">Vengono fornite informazioni sui diversi numeri di versione e su come comunicare agli sviluppatori le modifiche che causano un'interruzione.</span><span class="sxs-lookup"><span data-stu-id="b33e6-123">Learn about the various version numbers and how to communicate breaking changes to developers.</span></span>

### <a name="breaking-changesbreaking-changesmd"></a>[<span data-ttu-id="b33e6-124">Modifiche che causano un'interruzione</span><span class="sxs-lookup"><span data-stu-id="b33e6-124">Breaking changes</span></span>](./breaking-changes.md)

<span data-ttu-id="b33e6-125">Per una libreria .NET è importante trovare un equilibrio tra la stabilità per gli utenti esistenti e l'innovazione per il futuro.</span><span class="sxs-lookup"><span data-stu-id="b33e6-125">It's important for a .NET library to find a balance between stability for existing users and innovation for the future.</span></span> <span data-ttu-id="b33e6-126">Vengono fornite informazioni sui diversi tipi di modifiche che causano un'interruzione e sulle strategie per aggiungere nuove funzionalità mantenendo la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="b33e6-126">Learn about the different kinds of breaking changes and strategies for adding new features while maintaining backwards compatibility.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="b33e6-127">[Precedente](index.md)
>[Successivo](cross-platform-targeting.md)</span><span class="sxs-lookup"><span data-stu-id="b33e6-127">[Previous](index.md)
[Next](cross-platform-targeting.md)</span></span>