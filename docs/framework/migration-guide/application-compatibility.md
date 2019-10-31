---
title: Runtime e modifiche di reindirizzamento-.NET Framework
ms.date: 10/29/2019
helpviewer_keywords:
- application compatibility
- .NET Framework application compatibility
- .NET Framework changes
ms.assetid: c4ba3ff2-fe59-4c5d-9e0b-86bba3cd865c
ms.openlocfilehash: c46f781d495b87a4f24e77935df7c4814c8567ae
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2019
ms.locfileid: "73196703"
---
# <a name="application-compatibility-in-the-net-framework"></a><span data-ttu-id="27ae5-102">Compatibilità delle applicazioni nel .NET Framework</span><span class="sxs-lookup"><span data-stu-id="27ae5-102">Application compatibility in the .NET Framework</span></span>

<span data-ttu-id="27ae5-103">La compatibilità è un obiettivo importante di ogni versione di .NET.</span><span class="sxs-lookup"><span data-stu-id="27ae5-103">Compatibility is an important goal of each .NET release.</span></span> <span data-ttu-id="27ae5-104">La compatibilità garantisce che ogni versione sia additiva, quindi le versioni precedenti continueranno a funzionare.</span><span class="sxs-lookup"><span data-stu-id="27ae5-104">Compatibility ensures that each version is additive, so previous versions will continue to work.</span></span> <span data-ttu-id="27ae5-105">D'altra parte, le modifiche apportate alle funzionalità precedenti, ad esempio per migliorare le prestazioni, risolvere i problemi di sicurezza o correggere i bug, possono causare problemi di compatibilità nel codice esistente o nelle applicazioni esistenti eseguite in una versione successiva.</span><span class="sxs-lookup"><span data-stu-id="27ae5-105">On the other hand, changes to previous functionality (for example, to improve performance, address security issues, or fix bugs) can cause compatibility problems in existing code or existing applications that run under a later version.</span></span>

<span data-ttu-id="27ae5-106">Ogni app è destinata a una versione specifica del .NET Framework da:</span><span class="sxs-lookup"><span data-stu-id="27ae5-106">Each app targets a specific version of the .NET Framework by:</span></span>

- <span data-ttu-id="27ae5-107">Definizione di un framework di destinazione in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="27ae5-107">Defining a target framework in Visual Studio.</span></span>
- <span data-ttu-id="27ae5-108">Indicazione del framework di destinazione in un file di progetto.</span><span class="sxs-lookup"><span data-stu-id="27ae5-108">Specifying the target framework in a project file.</span></span>
- <span data-ttu-id="27ae5-109">Applicazione di un <xref:System.Runtime.Versioning.TargetFrameworkAttribute> al codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="27ae5-109">Applying a <xref:System.Runtime.Versioning.TargetFrameworkAttribute> to the source code.</span></span>

<span data-ttu-id="27ae5-110">Quando si esegue la migrazione da una versione del .NET Framework a un'altra, è necessario considerare due tipi di modifiche:</span><span class="sxs-lookup"><span data-stu-id="27ae5-110">When migrating from one version of the .NET Framework to another, there are two types of changes to consider:</span></span>

- [<span data-ttu-id="27ae5-111">Modifiche al runtime</span><span class="sxs-lookup"><span data-stu-id="27ae5-111">Runtime changes</span></span>](#runtime-changes)
- [<span data-ttu-id="27ae5-112">Modifiche di reindirizzamento</span><span class="sxs-lookup"><span data-stu-id="27ae5-112">Retargeting changes</span></span>](#retargeting-changes)

## <a name="runtime-changes"></a><span data-ttu-id="27ae5-113">Modifiche in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="27ae5-113">Runtime changes</span></span>

<span data-ttu-id="27ae5-114">I problemi di runtime sono quelli che si verificano quando un nuovo runtime viene inserito in un computer e cambia il comportamento di un'app.</span><span class="sxs-lookup"><span data-stu-id="27ae5-114">Runtime issues are those that arise when a new runtime is placed on a machine and an app's behavior changes.</span></span> <span data-ttu-id="27ae5-115">Quando si esegue una versione più recente di quella di destinazione, il .NET Framework *utilizza un* comportamento anomalo per simulare la versione di destinazione precedente.</span><span class="sxs-lookup"><span data-stu-id="27ae5-115">When running on a newer version than what was targeted, the .NET Framework uses *quirked* behavior to mimic the older targeted version.</span></span> <span data-ttu-id="27ae5-116">L'app viene eseguita nella versione più recente, ma funziona come se fosse in esecuzione nella versione precedente.</span><span class="sxs-lookup"><span data-stu-id="27ae5-116">The app runs on the newer version but acts as if it's running on the older version.</span></span> <span data-ttu-id="27ae5-117">Questo modello di comportamento consente di attenuare molti problemi di compatibilità tra versioni diverse di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="27ae5-117">Many of the compatibility issues between versions of the .NET Framework are mitigated through this quirking model.</span></span> <span data-ttu-id="27ae5-118">Ad esempio, se un file binario è stato compilato per .NET Framework 4,0 ma viene eseguito in un computer con .NET Framework 4,5 o versione successiva, viene eseguito in modalità di compatibilità .NET Framework 4,0.</span><span class="sxs-lookup"><span data-stu-id="27ae5-118">For example, if a binary was compiled for .NET Framework 4.0 but runs on a machine with .NET Framework 4.5 or later, it runs in .NET Framework 4.0 compatibility mode.</span></span> <span data-ttu-id="27ae5-119">Ciò significa che molte delle modifiche apportate alla versione successiva non influiscono sul file binario.</span><span class="sxs-lookup"><span data-stu-id="27ae5-119">This means that many of the changes in the later version don't affect the binary.</span></span>

<span data-ttu-id="27ae5-120">La versione del .NET Framework a cui è destinata un'applicazione è determinata dalla versione di destinazione dell'assembly di immissione per il dominio dell'applicazione in cui viene eseguito il codice.</span><span class="sxs-lookup"><span data-stu-id="27ae5-120">The version of the .NET Framework that an application targets is determined by the target version of the entry assembly for the application domain that the code runs in.</span></span> <span data-ttu-id="27ae5-121">Tutti gli assembly aggiuntivi caricati nel dominio applicazione sono destinati a tale versione.</span><span class="sxs-lookup"><span data-stu-id="27ae5-121">All additional assemblies loaded in that application domain target that version.</span></span> <span data-ttu-id="27ae5-122">Nel caso di un eseguibile, ad esempio, la versione di destinazione dell'eseguibile è la modalità di compatibilità in cui vengono eseguiti tutti gli assembly del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="27ae5-122">For example, in the case of an executable, the version that the executable targets is the compatibility mode all assemblies in that application domain run under.</span></span>

<span data-ttu-id="27ae5-123">Per visualizzare un elenco delle modifiche di runtime che si applicano all'ambiente in uso, selezionare la versione di .NET Framework attualmente destinata e quindi la versione a cui si vuole eseguire la migrazione:</span><span class="sxs-lookup"><span data-stu-id="27ae5-123">To see a list of runtime changes that apply to your environment, select the .NET Framework version you're currently targeting and then the version you wish to migrate to:</span></span>

[!INCLUDE[versionselector](../../../includes/migration-guide/runtime/versionselector.md)]

## <a name="retargeting-changes"></a><span data-ttu-id="27ae5-124">Modifiche di reindirizzamento</span><span class="sxs-lookup"><span data-stu-id="27ae5-124">Retargeting changes</span></span>

<span data-ttu-id="27ae5-125">Le modifiche di reindirizzamento sono quelle che si verificano quando un assembly viene ricompilato per avere come destinazione una versione più recente.</span><span class="sxs-lookup"><span data-stu-id="27ae5-125">Retargeting changes are those that arise when an assembly is recompiled to target a newer version.</span></span> <span data-ttu-id="27ae5-126">La definizione di una versione più recente indica che l'assembly sceglie le nuove funzionalità, nonché i potenziali problemi di compatibilità per le funzionalità obsolete.</span><span class="sxs-lookup"><span data-stu-id="27ae5-126">Targeting a newer version means the assembly opts into the new features as well as potential compatibility issues for old features.</span></span>

<span data-ttu-id="27ae5-127">Per visualizzare un elenco delle modifiche di reindirizzamento applicabili all'ambiente in uso, selezionare la versione .NET Framework attualmente destinata e quindi la versione a cui si vuole eseguire la migrazione:</span><span class="sxs-lookup"><span data-stu-id="27ae5-127">To see a list of retargeting changes that apply to your environment, select the .NET Framework version you're currently targeting and then the version you wish to migrate to:</span></span>

[!INCLUDE[versionselector](../../../includes/migration-guide/retargeting/versionselector.md)]

## <a name="impact-classification"></a><span data-ttu-id="27ae5-128">Classificazione di effetto</span><span class="sxs-lookup"><span data-stu-id="27ae5-128">Impact classification</span></span>

<span data-ttu-id="27ae5-129">Negli argomenti che descrivono le modifiche di runtime e di reindirizzamento, ad esempio le [modifiche di reindirizzamento per la migrazione da 4.7.2 a 4,8](retargeting/4.7.2-4.8.md), i singoli elementi vengono classificati in base all'effetto previsto, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="27ae5-129">In the topics that describe runtime and retargeting changes, for example, [Retargeting changes for migrating from 4.7.2 to 4.8](retargeting/4.7.2-4.8.md), individual items are classified by their expected impact as follows:</span></span>

<span data-ttu-id="27ae5-130">**Major**</span><span class="sxs-lookup"><span data-stu-id="27ae5-130">**Major**</span></span>\
<span data-ttu-id="27ae5-131">Una modifica significativa che influisce su un numero elevato di app o che richiede variazioni sostanziali del codice.</span><span class="sxs-lookup"><span data-stu-id="27ae5-131">A significant change that affects a large number of apps or that requires substantial modification of code.</span></span>

<span data-ttu-id="27ae5-132">**Minor**</span><span class="sxs-lookup"><span data-stu-id="27ae5-132">**Minor**</span></span>\
<span data-ttu-id="27ae5-133">Una modifica che influisce su un numero ridotto di app o che richiede variazioni marginali del codice.</span><span class="sxs-lookup"><span data-stu-id="27ae5-133">A change that affects a small number of apps or that requires minor modification of code.</span></span>

<span data-ttu-id="27ae5-134">\ **caso Edge**</span><span class="sxs-lookup"><span data-stu-id="27ae5-134">**Edge case**\</span></span>
<span data-ttu-id="27ae5-135">Una modifica che influisce sulle app in scenari molto specifici e non comuni.</span><span class="sxs-lookup"><span data-stu-id="27ae5-135">A change that affects apps under very specific scenarios that are not common.</span></span>

<span data-ttu-id="27ae5-136">\ **trasparente**</span><span class="sxs-lookup"><span data-stu-id="27ae5-136">**Transparent**\</span></span>
<span data-ttu-id="27ae5-137">Una modifica che non ha effetti evidenti sullo sviluppatore o sull'utente dell'app.</span><span class="sxs-lookup"><span data-stu-id="27ae5-137">A change that has no noticeable effect on the app's developer or user.</span></span> <span data-ttu-id="27ae5-138">L'app non dovrebbe richiedere variazioni a causa di questa modifica.</span><span class="sxs-lookup"><span data-stu-id="27ae5-138">The app should not require modification because of this change.</span></span>

## <a name="see-also"></a><span data-ttu-id="27ae5-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27ae5-139">See also</span></span>

- [<span data-ttu-id="27ae5-140">Versioni e dipendenze</span><span class="sxs-lookup"><span data-stu-id="27ae5-140">Versions and dependencies</span></span>](versions-and-dependencies.md)
- [<span data-ttu-id="27ae5-141">Novità</span><span class="sxs-lookup"><span data-stu-id="27ae5-141">What's new</span></span>](../whats-new/index.md)
- [<span data-ttu-id="27ae5-142">Elementi obsoleti</span><span class="sxs-lookup"><span data-stu-id="27ae5-142">What's obsolete</span></span>](../whats-new/whats-obsolete.md)
