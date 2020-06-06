---
title: Schema delle impostazioni di traccia e debug
ms.date: 03/30/2017
helpviewer_keywords:
- tracing [.NET Framework], trace and debug settings schema
- configuration schema [.NET Framework], trace and debug settings
- configuration settings [.NET Framework], tracing
- schema configuration settings
- configuration settings [.NET Framework], debugging
- trace listeners, trace and debug settings schema
- configuration sections [.NET Framework]
- elements [.NET Framework], trace and debug settings
ms.assetid: 277ca5f6-e1c4-41b6-a47f-3a67ce5b94ac
ms.openlocfilehash: 037d08b33e9aa6a64d236b36ebcf821b604b03df
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "69927124"
---
# <a name="trace-and-debug-settings-schema"></a><span data-ttu-id="158d7-102">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="158d7-102">Trace and Debug Settings Schema</span></span>
<span data-ttu-id="158d7-103">Le impostazioni di traccia e debug specificano i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="158d7-103">Trace and debug settings specify trace listeners that collect, store, and route messages, and the level where a trace switch is set.</span></span>  
  
 <span data-ttu-id="158d7-104">La tabella seguente descrive la funzione di ogni elemento delle impostazioni di traccia e debug.</span><span class="sxs-lookup"><span data-stu-id="158d7-104">The following table describes the function of each trace and debug settings element.</span></span>  
  
|<span data-ttu-id="158d7-105">Elemento</span><span class="sxs-lookup"><span data-stu-id="158d7-105">Element</span></span>|<span data-ttu-id="158d7-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="158d7-106">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-element-for-listeners-for-source.md)|<span data-ttu-id="158d7-107">Aggiunge un listener alla raccolta `Listeners` per un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="158d7-107">Adds a listener to the `Listeners` collection for a trace source.</span></span>|  
|[\<add>](add-element-for-listeners-for-trace.md)|<span data-ttu-id="158d7-108">Aggiunge un listener alla raccolta `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="158d7-108">Adds a listener to the `Listeners` collection.</span></span>|  
|[\<add>](add-element-for-sharedlisteners.md)|<span data-ttu-id="158d7-109">Aggiunge un listener alla raccolta `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="158d7-109">Adds a listener to the `sharedListeners` collection.</span></span>|  
|[\<add>](add-element-for-switches.md)|<span data-ttu-id="158d7-110">Specifica il livello in cui viene impostata un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="158d7-110">Specifies the level where a trace switch is set.</span></span>|  
|[\<assert>](assert-element.md)|<span data-ttu-id="158d7-111">Specifica se visualizzare una finestra di messaggio quando si chiama il metodo <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>. Specifica anche il nome del file in cui scrivere i messaggi.</span><span class="sxs-lookup"><span data-stu-id="158d7-111">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>|  
|[\<clear>](clear-element-for-listeners-for-source.md)|<span data-ttu-id="158d7-112">Cancella la raccolta `Listeners` per un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="158d7-112">Clears the `Listeners` collection for a trace source.</span></span>|  
|[\<clear>](clear-element-for-listeners-for-trace.md)|<span data-ttu-id="158d7-113">Cancella la raccolta `Listeners` per una traccia.</span><span class="sxs-lookup"><span data-stu-id="158d7-113">Clears the `Listeners` collection for trace.</span></span>|  
|[\<filter>](filter-element-for-add-for-listeners-for-source.md)|<span data-ttu-id="158d7-114">Aggiunge un filtro a un listener nella raccolta `Listeners` per un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="158d7-114">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>|  
|[\<filter>](filter-element-for-add-for-listeners-for-trace.md)|<span data-ttu-id="158d7-115">Aggiunge un filtro a un listener nella raccolta `Listeners` per la traccia.</span><span class="sxs-lookup"><span data-stu-id="158d7-115">Adds a filter to a listener in the `Listeners` collection for trace.</span></span>|  
|[\<filter>](filter-element-for-add-for-sharedlisteners.md)|<span data-ttu-id="158d7-116">Aggiunge un filtro a un listener nella raccolta `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="158d7-116">Adds a filter to a listener in the `sharedListeners` collection.</span></span>|  
|[\<listeners>](listeners-element-for-source.md)|<span data-ttu-id="158d7-117">Specifica i listener per la raccolta `Listeners` per un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="158d7-117">Specifies listeners for the `Listeners` collection for a trace source.</span></span>|  
|[\<listeners>](listeners-element-for-trace.md)|<span data-ttu-id="158d7-118">Specifica i listener per la raccolta `Listeners` per una traccia.</span><span class="sxs-lookup"><span data-stu-id="158d7-118">Specifies listeners for the `Listeners` collection for trace.</span></span>|  
|[\<performanceCounters>](performancecounters-element.md)|<span data-ttu-id="158d7-119">Specifica le dimensioni della memoria globale condivisa dai contatori delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="158d7-119">Specifies the size of the global memory shared by performance counters.</span></span>|  
|[\<remove>](remove-element-for-listeners-for-trace.md)|<span data-ttu-id="158d7-120">Rimuove un listener dalla raccolta `Listeners` per la traccia.</span><span class="sxs-lookup"><span data-stu-id="158d7-120">Removes a listener from the `Listeners` collection for trace.</span></span>|  
|[\<remove>](remove-element-for-listeners-for-source.md)|<span data-ttu-id="158d7-121">Rimuove un listener dalla raccolta `Listeners` per un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="158d7-121">Removes a listener from the `Listeners` collection for a trace source.</span></span>|  
|[\<sharedListeners>](sharedlisteners-element.md)|<span data-ttu-id="158d7-122">Contiene i listener a cui può fare riferimento qualsiasi origine o elemento di traccia.</span><span class="sxs-lookup"><span data-stu-id="158d7-122">Contains listeners that any source or trace element can reference.</span></span>|  
|[\<sources>](sources-element.md)|<span data-ttu-id="158d7-123">Contiene le origini di traccia che avviano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="158d7-123">Contains trace sources that initiate tracing messages.</span></span>|  
|[\<source>](source-element.md)|<span data-ttu-id="158d7-124">Specifica un'origine di traccia che avvia i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="158d7-124">Specifies a trace source that initiates tracing messages.</span></span>|  
|[\<switches>](switches-element.md)|<span data-ttu-id="158d7-125">Contiene le opzioni di traccia e il livello in cui vengono impostate le opzioni di traccia.</span><span class="sxs-lookup"><span data-stu-id="158d7-125">Contains trace switches and the level where the trace switches are set.</span></span>|  
|[\<system.diagnostics>](system-diagnostics-element.md)|<span data-ttu-id="158d7-126">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="158d7-126">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|[\<trace>](trace-element.md)|<span data-ttu-id="158d7-127">Contiene i listener che raccolgono, archiviano e indirizzano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="158d7-127">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="158d7-128">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="158d7-128">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.Debug>
- [<span data-ttu-id="158d7-129">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="158d7-129">Configuration File Schema</span></span>](../index.md)
