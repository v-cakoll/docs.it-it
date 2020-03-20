---
title: Modifiche di runtime e retargeting - .NET Framework
ms.date: 10/29/2019
helpviewer_keywords:
- application compatibility
- .NET Framework application compatibility
- .NET Framework changes
ms.assetid: c4ba3ff2-fe59-4c5d-9e0b-86bba3cd865c
ms.openlocfilehash: c46f781d495b87a4f24e77935df7c4814c8567ae
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73196703"
---
# <a name="application-compatibility-in-the-net-framework"></a><span data-ttu-id="5ea35-102">Compatibilità delle applicazioni in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="5ea35-102">Application compatibility in the .NET Framework</span></span>

<span data-ttu-id="5ea35-103">La compatibilità è un obiettivo importante di ogni versione di .NET.</span><span class="sxs-lookup"><span data-stu-id="5ea35-103">Compatibility is an important goal of each .NET release.</span></span> <span data-ttu-id="5ea35-104">La compatibilità garantisce che ogni versione sia additiva, pertanto le versioni precedenti continueranno a funzionare.</span><span class="sxs-lookup"><span data-stu-id="5ea35-104">Compatibility ensures that each version is additive, so previous versions will continue to work.</span></span> <span data-ttu-id="5ea35-105">D'altra parte, le modifiche alle funzionalità precedenti (ad esempio, per migliorare le prestazioni, risolvere i problemi di sicurezza o correggere i bug) possono causare problemi di compatibilità nel codice esistente o nelle applicazioni esistenti eseguite in una versione successiva.</span><span class="sxs-lookup"><span data-stu-id="5ea35-105">On the other hand, changes to previous functionality (for example, to improve performance, address security issues, or fix bugs) can cause compatibility problems in existing code or existing applications that run under a later version.</span></span>

<span data-ttu-id="5ea35-106">Ogni app è destinata a una versione specifica di .NET Framework tramite:</span><span class="sxs-lookup"><span data-stu-id="5ea35-106">Each app targets a specific version of the .NET Framework by:</span></span>

- <span data-ttu-id="5ea35-107">Definizione di un framework di destinazione in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5ea35-107">Defining a target framework in Visual Studio.</span></span>
- <span data-ttu-id="5ea35-108">Indicazione del framework di destinazione in un file di progetto.</span><span class="sxs-lookup"><span data-stu-id="5ea35-108">Specifying the target framework in a project file.</span></span>
- <span data-ttu-id="5ea35-109">Applicazione di un <xref:System.Runtime.Versioning.TargetFrameworkAttribute> al codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="5ea35-109">Applying a <xref:System.Runtime.Versioning.TargetFrameworkAttribute> to the source code.</span></span>

<span data-ttu-id="5ea35-110">Quando si esegue la migrazione da una versione di .NET Framework a un'altra, è necessario considerare due tipi di modifiche:</span><span class="sxs-lookup"><span data-stu-id="5ea35-110">When migrating from one version of the .NET Framework to another, there are two types of changes to consider:</span></span>

- [<span data-ttu-id="5ea35-111">Modifiche di runtime</span><span class="sxs-lookup"><span data-stu-id="5ea35-111">Runtime changes</span></span>](#runtime-changes)
- [<span data-ttu-id="5ea35-112">Modifiche di retargeting</span><span class="sxs-lookup"><span data-stu-id="5ea35-112">Retargeting changes</span></span>](#retargeting-changes)

## <a name="runtime-changes"></a><span data-ttu-id="5ea35-113">Modifiche in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="5ea35-113">Runtime changes</span></span>

<span data-ttu-id="5ea35-114">I problemi di runtime sono quelli che si verificano quando un nuovo runtime viene inserito in un computer e il comportamento di un'app cambia.</span><span class="sxs-lookup"><span data-stu-id="5ea35-114">Runtime issues are those that arise when a new runtime is placed on a machine and an app's behavior changes.</span></span> <span data-ttu-id="5ea35-115">Quando viene eseguito su una versione più recente di quella di destinazione, .NET Framework utilizza un comportamento *anomalo* per simulare la versione di destinazione precedente.</span><span class="sxs-lookup"><span data-stu-id="5ea35-115">When running on a newer version than what was targeted, the .NET Framework uses *quirked* behavior to mimic the older targeted version.</span></span> <span data-ttu-id="5ea35-116">L'app viene eseguita nella versione più recente, ma funziona come se fosse in esecuzione nella versione precedente.</span><span class="sxs-lookup"><span data-stu-id="5ea35-116">The app runs on the newer version but acts as if it's running on the older version.</span></span> <span data-ttu-id="5ea35-117">Questo modello di comportamento consente di attenuare molti problemi di compatibilità tra versioni diverse di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5ea35-117">Many of the compatibility issues between versions of the .NET Framework are mitigated through this quirking model.</span></span> <span data-ttu-id="5ea35-118">Ad esempio, se un file binario è stato compilato per .NET Framework 4.0 ma viene eseguito in un computer con .NET Framework 4.5 o versione successiva, viene eseguito in modalità compatibilità .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="5ea35-118">For example, if a binary was compiled for .NET Framework 4.0 but runs on a machine with .NET Framework 4.5 or later, it runs in .NET Framework 4.0 compatibility mode.</span></span> <span data-ttu-id="5ea35-119">Ciò significa che molte delle modifiche nella versione successiva non influiscono sul file binario.</span><span class="sxs-lookup"><span data-stu-id="5ea35-119">This means that many of the changes in the later version don't affect the binary.</span></span>

<span data-ttu-id="5ea35-120">La versione di .NET Framework di destinazione di un'applicazione è determinata dalla versione di destinazione dell'assembly della voce per il dominio applicazione in cui viene eseguito il codice.</span><span class="sxs-lookup"><span data-stu-id="5ea35-120">The version of the .NET Framework that an application targets is determined by the target version of the entry assembly for the application domain that the code runs in.</span></span> <span data-ttu-id="5ea35-121">Tutti gli assembly aggiuntivi caricati in tale dominio applicazione sono destinati a tale versione.</span><span class="sxs-lookup"><span data-stu-id="5ea35-121">All additional assemblies loaded in that application domain target that version.</span></span> <span data-ttu-id="5ea35-122">Ad esempio, nel caso di un eseguibile, la versione che le destinazioni eseguibili è la modalità di compatibilità in cui vengono eseguiti tutti gli assembly in tale dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="5ea35-122">For example, in the case of an executable, the version that the executable targets is the compatibility mode all assemblies in that application domain run under.</span></span>

<span data-ttu-id="5ea35-123">Per visualizzare un elenco delle modifiche di runtime che si applicano all'ambiente, selezionare la versione di .NET Framework attualmente di destinazione e quindi la versione a cui si desidera eseguire la migrazione:</span><span class="sxs-lookup"><span data-stu-id="5ea35-123">To see a list of runtime changes that apply to your environment, select the .NET Framework version you're currently targeting and then the version you wish to migrate to:</span></span>

[!INCLUDE[versionselector](../../../includes/migration-guide/runtime/versionselector.md)]

## <a name="retargeting-changes"></a><span data-ttu-id="5ea35-124">Modifiche di reindirizzamento</span><span class="sxs-lookup"><span data-stu-id="5ea35-124">Retargeting changes</span></span>

<span data-ttu-id="5ea35-125">Le modifiche di retargeting sono quelle che si verificano quando un assembly viene ricompilato per essere destinato a una versione più recente.</span><span class="sxs-lookup"><span data-stu-id="5ea35-125">Retargeting changes are those that arise when an assembly is recompiled to target a newer version.</span></span> <span data-ttu-id="5ea35-126">La destinazione di una versione più recente significa che l'assembly attiva le nuove funzionalità e potenziali problemi di compatibilità per le funzionalità precedenti.</span><span class="sxs-lookup"><span data-stu-id="5ea35-126">Targeting a newer version means the assembly opts into the new features as well as potential compatibility issues for old features.</span></span>

<span data-ttu-id="5ea35-127">Per visualizzare un elenco delle modifiche di retargeting che si applicano all'ambiente, selezionare la versione di .NET Framework attualmente di destinazione e quindi la versione in cui si desidera eseguire la migrazione:</span><span class="sxs-lookup"><span data-stu-id="5ea35-127">To see a list of retargeting changes that apply to your environment, select the .NET Framework version you're currently targeting and then the version you wish to migrate to:</span></span>

[!INCLUDE[versionselector](../../../includes/migration-guide/retargeting/versionselector.md)]

## <a name="impact-classification"></a><span data-ttu-id="5ea35-128">Classificazione d'impatto</span><span class="sxs-lookup"><span data-stu-id="5ea35-128">Impact classification</span></span>

<span data-ttu-id="5ea35-129">Negli argomenti che descrivono le modifiche di runtime e retargeting, ad esempio, [il retargeting delle modifiche per la migrazione da 4.7.2 a 4.8](retargeting/4.7.2-4.8.md), i singoli elementi vengono classificati in base all'impatto previsto come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="5ea35-129">In the topics that describe runtime and retargeting changes, for example, [Retargeting changes for migrating from 4.7.2 to 4.8](retargeting/4.7.2-4.8.md), individual items are classified by their expected impact as follows:</span></span>

<span data-ttu-id="5ea35-130">**Principali**</span><span class="sxs-lookup"><span data-stu-id="5ea35-130">**Major**</span></span>\
<span data-ttu-id="5ea35-131">Una modifica significativa che influisce su un numero elevato di app o che richiede variazioni sostanziali del codice.</span><span class="sxs-lookup"><span data-stu-id="5ea35-131">A significant change that affects a large number of apps or that requires substantial modification of code.</span></span>

<span data-ttu-id="5ea35-132">**Minore**</span><span class="sxs-lookup"><span data-stu-id="5ea35-132">**Minor**</span></span>\
<span data-ttu-id="5ea35-133">Una modifica che influisce su un numero ridotto di app o che richiede variazioni marginali del codice.</span><span class="sxs-lookup"><span data-stu-id="5ea35-133">A change that affects a small number of apps or that requires minor modification of code.</span></span>

<span data-ttu-id="5ea35-134">**Custodia per bordi**</span><span class="sxs-lookup"><span data-stu-id="5ea35-134">**Edge case**</span></span>\
<span data-ttu-id="5ea35-135">Una modifica che influisce sulle app in scenari molto specifici e non comuni.</span><span class="sxs-lookup"><span data-stu-id="5ea35-135">A change that affects apps under very specific scenarios that are not common.</span></span>

<span data-ttu-id="5ea35-136">**Trasparente**</span><span class="sxs-lookup"><span data-stu-id="5ea35-136">**Transparent**</span></span>\
<span data-ttu-id="5ea35-137">Una modifica che non ha effetti evidenti sullo sviluppatore o sull'utente dell'app.</span><span class="sxs-lookup"><span data-stu-id="5ea35-137">A change that has no noticeable effect on the app's developer or user.</span></span> <span data-ttu-id="5ea35-138">L'app non dovrebbe richiedere variazioni a causa di questa modifica.</span><span class="sxs-lookup"><span data-stu-id="5ea35-138">The app should not require modification because of this change.</span></span>

## <a name="see-also"></a><span data-ttu-id="5ea35-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5ea35-139">See also</span></span>

- [<span data-ttu-id="5ea35-140">Versioni e dipendenze</span><span class="sxs-lookup"><span data-stu-id="5ea35-140">Versions and dependencies</span></span>](versions-and-dependencies.md)
- [<span data-ttu-id="5ea35-141">Novità</span><span class="sxs-lookup"><span data-stu-id="5ea35-141">What's new</span></span>](../whats-new/index.md)
- [<span data-ttu-id="5ea35-142">Ciò che è obsoleto</span><span class="sxs-lookup"><span data-stu-id="5ea35-142">What's obsolete</span></span>](../whats-new/whats-obsolete.md)
