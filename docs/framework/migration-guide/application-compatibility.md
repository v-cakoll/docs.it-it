---
title: "Compatibilità delle applicazioni in .NET Framework"
ms.custom: 
ms.date: 05/19/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
- app-compat
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application compatibility
- .NET Framework application compatibility
- .NET Framework changes
caps.latest.revision: "19"
ms.assetid: c4ba3ff2-fe59-4c5d-9e0b-86bba3cd865c
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e67fff19c4b187010b35519081f46e11effbad6c
ms.sourcegitcommit: d0f7646d67db5809cf43ff1d27b399a4020e8ee2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/25/2017
---
# <a name="application-compatibility-in-the-net-framework"></a><span data-ttu-id="5107e-102">Compatibilità delle applicazioni in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="5107e-102">Application Compatibility in the .NET Framework</span></span>

## <a name="introduction"></a><span data-ttu-id="5107e-103">Introduzione</span><span class="sxs-lookup"><span data-stu-id="5107e-103">Introduction</span></span>
<span data-ttu-id="5107e-104">La compatibilità è un obiettivo molto importante di ogni versione di .NET,</span><span class="sxs-lookup"><span data-stu-id="5107e-104">Compatibility is a very important goal of each .NET release.</span></span> <span data-ttu-id="5107e-105">perché garantisce che ogni versione venga aggiunta alle precedenti, che pertanto continuano a funzionare.</span><span class="sxs-lookup"><span data-stu-id="5107e-105">Compatibility ensures that each version is additive, so previous versions will still work.</span></span> <span data-ttu-id="5107e-106">D'altra parte, quando codice o applicazioni esistenti vengono eseguiti in una versione successiva, le modifiche apportate alle funzionalità precedenti per migliorare le prestazioni, risolvere i problemi di sicurezza o correggere i bug possono causare problemi di compatibilità.</span><span class="sxs-lookup"><span data-stu-id="5107e-106">On the other hand, changes to previous functionality (to improve performance, address security issues, or fix bugs) can cause compatibility problems in existing code or existing applications that run under a later version.</span></span> <span data-ttu-id="5107e-107">In .NET Framework esiste la distinzione tra modifiche di ridestinazione e modifiche di runtime.</span><span class="sxs-lookup"><span data-stu-id="5107e-107">The .NET Framework recognizes retargeting changes and runtime changes.</span></span> <span data-ttu-id="5107e-108">Le modifiche di ridestinazione interessano le applicazioni destinate a una versione specifica di .NET Framework ma che vengono eseguite in una versione successiva.</span><span class="sxs-lookup"><span data-stu-id="5107e-108">Retargeting changes affect applications that target a specific version of the .NET Framework but are running on a later version.</span></span> <span data-ttu-id="5107e-109">Le modifiche di runtime interessano tutte le applicazioni in esecuzione in una versione specifica.</span><span class="sxs-lookup"><span data-stu-id="5107e-109">Runtime changes affect all applications running on a particular version.</span></span>

<span data-ttu-id="5107e-110">Ogni app è destinata a una versione specifica di .NET Framework, che può essere indicata tramite le azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5107e-110">Each app targets a specific version of the .NET Framework, which can be specified by:</span></span>

* <span data-ttu-id="5107e-111">Definizione di un framework di destinazione in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5107e-111">Defining a target framework in Visual Studio.</span></span>
* <span data-ttu-id="5107e-112">Indicazione del framework di destinazione in un file di progetto.</span><span class="sxs-lookup"><span data-stu-id="5107e-112">Specifying the target framework in a project file.</span></span>
* <span data-ttu-id="5107e-113">Applicazione di un <xref:System.Runtime.Versioning.TargetFrameworkAttribute> al codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="5107e-113">Applying a <xref:System.Runtime.Versioning.TargetFrameworkAttribute> to the source code.</span></span>

<span data-ttu-id="5107e-114">Durante l'esecuzione in una versione più recente di quella di destinazione, .NET Framework simula la versione di destinazione precedente adottando un comportamento anomalo.</span><span class="sxs-lookup"><span data-stu-id="5107e-114">When running on a newer version than what was targeted, the .NET Framework will use quirked behavior to mimic the older targeted version.</span></span> <span data-ttu-id="5107e-115">In altre parole, l'app viene eseguita nella versione più recente di .NET Framework, ma si comporta come se fosse in esecuzione nella versione precedente.</span><span class="sxs-lookup"><span data-stu-id="5107e-115">In other words, the app will run on the newer version of the Framework, but act as if it's running on the older version.</span></span> <span data-ttu-id="5107e-116">Questo modello di comportamento consente di attenuare molti problemi di compatibilità tra versioni diverse di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5107e-116">Many of the compatibility issues between versions of the .NET Framework are mitigated through this quirking model.</span></span>

## <a name="runtime-changes"></a><span data-ttu-id="5107e-117">Modifiche in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="5107e-117">Runtime changes</span></span>

<span data-ttu-id="5107e-118">I problemi di runtime sono quelli che si verificano quando in un computer viene installato un nuovo runtime e, pur eseguendo gli stessi file binari, il comportamento riscontrato è diverso.</span><span class="sxs-lookup"><span data-stu-id="5107e-118">Runtime issues are those that arise when a new runtime is placed on a machine and the same binaries are run, but different behavior is seen.</span></span> <span data-ttu-id="5107e-119">Se un file binario è stato compilato per .NET Framework 4.0, in .NET Framework versione 4.5 o successiva viene eseguito in modalità compatibilità .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="5107e-119">If a binary was compiled for .NET Framework 4.0 it will run in .NET Framework 4.0 compatibility mode on 4.5 or later versions.</span></span> <span data-ttu-id="5107e-120">Molte delle modifiche che interessano la versione 4.5 non interessano i file binari compilati per la versione 4.0.</span><span class="sxs-lookup"><span data-stu-id="5107e-120">Many of the changes that affect 4.5 will not affect a binary compiled for 4.0.</span></span> <span data-ttu-id="5107e-121">Questo è specifico di AppDomain e dipende dalle impostazioni dell'assembly di voce.</span><span class="sxs-lookup"><span data-stu-id="5107e-121">This is specific to the AppDomain and depends on the settings of the entry assembly.</span></span>

## <a name="retargeting-changes"></a><span data-ttu-id="5107e-122">Modifiche di reindirizzamento</span><span class="sxs-lookup"><span data-stu-id="5107e-122">Retargeting changes</span></span>

<span data-ttu-id="5107e-123">I problemi di ridestinazione sono quelli che si verificano quando per un assembly destinato alla versione 4.0 viene assegnata come destinazione la versione 4.5.</span><span class="sxs-lookup"><span data-stu-id="5107e-123">Retargeting issues are those that arise when an assembly that was targeting 4.0 is now set to target 4.5.</span></span> <span data-ttu-id="5107e-124">A questo punto l'assembly è in grado di usare le nuove funzionalità, ma può presentare problemi di compatibilità con le funzionalità precedenti.</span><span class="sxs-lookup"><span data-stu-id="5107e-124">Now the assembly opts into the new features as well as potential compatibility issues to old features.</span></span> <span data-ttu-id="5107e-125">Anche in questo caso, ciò dipende dall'assembly di voce, quindi dall'app console che usa l'assembly o dal sito Web che vi fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="5107e-125">Again, this is dictated by the entry assembly, so the console app that uses the assembly, or the website that references the assembly.</span></span>

## <a name="net-compatibility-diagnostics"></a><span data-ttu-id="5107e-126">.NET Compatibility Diagnostics</span><span class="sxs-lookup"><span data-stu-id="5107e-126">.NET Compatibility Diagnostics</span></span>

<span data-ttu-id="5107e-127">.NET Compatibility Diagnostics include analizzatori basati su Roslyn che consentono di identificare problemi di compatibilità delle applicazioni tra versioni diverse di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5107e-127">The .NET Compatibility Diagnostics are Roslyn-powered analyzers that help identify application compatibility issues between versions of the .NET Framework.</span></span> <span data-ttu-id="5107e-128">Questo elenco contiene tutti gli analizzatori disponibili, anche se solo un subset sarà applicabile a ogni specifica migrazione.</span><span class="sxs-lookup"><span data-stu-id="5107e-128">This list contains all of the analyzers available, although only a subset will apply to any specific migration.</span></span> <span data-ttu-id="5107e-129">Saranno gli analizzatori a determinare i problemi applicabili alla migrazione pianificata e a segnalare solo quelli.</span><span class="sxs-lookup"><span data-stu-id="5107e-129">The analyzers will determine which issues are applicable for the planned migration and will only surface those.</span></span>

<span data-ttu-id="5107e-130">Per ogni problema sono incluse le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5107e-130">Each issue includes the following information:</span></span>

-   <span data-ttu-id="5107e-131">Descrizione delle modifiche rispetto a una versione precedente.</span><span class="sxs-lookup"><span data-stu-id="5107e-131">The description of what has changed from a previous version.</span></span>

-   <span data-ttu-id="5107e-132">Le conseguenze della modifica sui clienti e l'eventuale disponibilità di soluzioni per mantenere la compatibilità tra versioni diverse.</span><span class="sxs-lookup"><span data-stu-id="5107e-132">How the change affects customers and whether any workarounds are available to preserve compatibility across versions.</span></span>

-   <span data-ttu-id="5107e-133">Valutazione dell'importanza della modifica.</span><span class="sxs-lookup"><span data-stu-id="5107e-133">An assessment of how important the change is.</span></span> <span data-ttu-id="5107e-134">I problemi di compatibilità delle applicazioni sono classificati come segue:</span><span class="sxs-lookup"><span data-stu-id="5107e-134">Application compatibility issue are categorized as follows:</span></span>

    |   |   |
    |---|---|
    |<span data-ttu-id="5107e-135">Principale</span><span class="sxs-lookup"><span data-stu-id="5107e-135">Major</span></span>|<span data-ttu-id="5107e-136">Una modifica significativa che influisce su un numero elevato di app o che richiede variazioni sostanziali del codice.</span><span class="sxs-lookup"><span data-stu-id="5107e-136">A significant change that affects a large number of apps or requires substantial modification of code.</span></span>|
    |<span data-ttu-id="5107e-137">Secondario</span><span class="sxs-lookup"><span data-stu-id="5107e-137">Minor</span></span>|<span data-ttu-id="5107e-138">Una modifica che influisce su un numero ridotto di app o che richiede variazioni marginali del codice.</span><span class="sxs-lookup"><span data-stu-id="5107e-138">A change that affects a small number of apps or that requires minor modification of code.</span></span>|
    |<span data-ttu-id="5107e-139">Caso limite</span><span class="sxs-lookup"><span data-stu-id="5107e-139">Edge case</span></span>|<span data-ttu-id="5107e-140">Una modifica che influisce sulle app in scenari molto specifici e non comuni.</span><span class="sxs-lookup"><span data-stu-id="5107e-140">A change that affects apps under very specific, uncommon scenarios.</span></span>|
    |<span data-ttu-id="5107e-141">Trasparente</span><span class="sxs-lookup"><span data-stu-id="5107e-141">Transparent</span></span>|<span data-ttu-id="5107e-142">Una modifica senza effetti evidenti sullo sviluppatore o sull'utente dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5107e-142">A change with no noticeable effect on the application's developer or user.</span></span>|

-   <span data-ttu-id="5107e-143">La versione indica quando la modifica è comparsa per la prima volta nel framework.</span><span class="sxs-lookup"><span data-stu-id="5107e-143">Version indicates when the change first appears in the framework.</span></span> <span data-ttu-id="5107e-144">Alcune modifiche vengono introdotte in una versione specifica e ripristinate in una versione successiva. Anche il ripristino viene indicato.</span><span class="sxs-lookup"><span data-stu-id="5107e-144">Some of the changes are introduced in a particular version and reverted in a later version; that is indicated as well.</span></span>

-   <span data-ttu-id="5107e-145">Tipo di modifica:</span><span class="sxs-lookup"><span data-stu-id="5107e-145">The type of change:</span></span>

    |   |   |
    |---|---|
    |<span data-ttu-id="5107e-146">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="5107e-146">Retargeting</span></span>|<span data-ttu-id="5107e-147">La modifica influisce sulle app ricompilate per una nuova versione di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5107e-147">The change affects apps that are recompiled to target a new version of the .NET Framework.</span></span>|
    |<span data-ttu-id="5107e-148">Runtime</span><span class="sxs-lookup"><span data-stu-id="5107e-148">Runtime</span></span>|<span data-ttu-id="5107e-149">La modifica influisce su un'app esistente destinata a una versione precedente di .NET Framework, ma che viene eseguita su una versione successiva.</span><span class="sxs-lookup"><span data-stu-id="5107e-149">The change affects an existing app that targets a previous version of the .NET Framework but runs on a later version.</span></span>|

-   <span data-ttu-id="5107e-150">Le eventuali API interessate.</span><span class="sxs-lookup"><span data-stu-id="5107e-150">The affected APIS, if any.</span></span>

-   <span data-ttu-id="5107e-151">ID delle diagnostiche disponibili</span><span class="sxs-lookup"><span data-stu-id="5107e-151">The IDs of the available diagnostics</span></span>

## <a name="usage"></a><span data-ttu-id="5107e-152">Utilizzo</span><span class="sxs-lookup"><span data-stu-id="5107e-152">Usage</span></span>
<span data-ttu-id="5107e-153">Per iniziare, selezionare il tipo di modifica della compatibilità di seguito:</span><span class="sxs-lookup"><span data-stu-id="5107e-153">To begin, select the type of compatibility change below:</span></span>

* [<span data-ttu-id="5107e-154">Modifiche di reindirizzamento</span><span class="sxs-lookup"><span data-stu-id="5107e-154">Retargeting Changes</span></span>](./retargeting/index.md)
* [<span data-ttu-id="5107e-155">Modifiche al runtime</span><span class="sxs-lookup"><span data-stu-id="5107e-155">Runtime Changes</span></span>](./runtime/index.md)


## <a name="see-also"></a><span data-ttu-id="5107e-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5107e-156">See Also</span></span>

* [<span data-ttu-id="5107e-157">Versioni e dipendenze</span><span class="sxs-lookup"><span data-stu-id="5107e-157">Versions and Dependencies</span></span>](../../../docs/framework/migration-guide/versions-and-dependencies.md)
* [<span data-ttu-id="5107e-158">Novità</span><span class="sxs-lookup"><span data-stu-id="5107e-158">What's New</span></span>](../../../docs/framework/whats-new/index.md)
* [<span data-ttu-id="5107e-159">Elementi obsoleti nella libreria di classi</span><span class="sxs-lookup"><span data-stu-id="5107e-159">What's Obsolete in the Class Library</span></span>](../../../docs/framework/whats-new/whats-obsolete.md)
