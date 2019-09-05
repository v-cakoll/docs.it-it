---
title: Elemento < NetFx40_PInvokeStackResilience >
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_PInvokeStackResilience> element
- NetFx40_PInvokeStackResilience element
ms.assetid: 39fb1588-72a4-4479-af74-0605233b68bd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8f4dffe5428ccb7541055fa4f3f335f57deaf2ec
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252435"
---
# <a name="netfx40_pinvokestackresilience-element"></a><span data-ttu-id="f7bba-102">\<Elemento > NetFx40_PInvokeStackResilience</span><span class="sxs-lookup"><span data-stu-id="f7bba-102">\<NetFx40_PInvokeStackResilience> Element</span></span>

<span data-ttu-id="f7bba-103">Specifica se il runtime corregge automaticamente le dichiarazioni platform invoke non corrette in fase di esecuzione, al costo di transizioni più lente tra codice gestito e quello non gestito.</span><span class="sxs-lookup"><span data-stu-id="f7bba-103">Specifies whether the runtime automatically fixes incorrect platform invoke declarations at run time, at the cost of slower transitions between managed and unmanaged code.</span></span>

<span data-ttu-id="f7bba-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f7bba-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f7bba-105">&nbsp;&nbsp;[ **\<> di runtime**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="f7bba-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="f7bba-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<> NetFx40_PInvokeStackResilience**</span><span class="sxs-lookup"><span data-stu-id="f7bba-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<NetFx40_PInvokeStackResilience>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="f7bba-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f7bba-107">Syntax</span></span>

```xml
<NetFx40_PInvokeStackResilience  enabled="1|0"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f7bba-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f7bba-108">Attributes and Elements</span></span>

<span data-ttu-id="f7bba-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f7bba-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="f7bba-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="f7bba-110">Attributes</span></span>

|<span data-ttu-id="f7bba-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="f7bba-111">Attribute</span></span>|<span data-ttu-id="f7bba-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f7bba-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="f7bba-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="f7bba-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="f7bba-114">Specifica se il runtime rileva dichiarazioni di platform invoke non corrette e corregge automaticamente lo stack in fase di esecuzione sulle piattaforme a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="f7bba-114">Specifies whether the runtime detects incorrect platform invoke declarations and automatically fixes the stack at run time on 32-bit platforms.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="f7bba-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="f7bba-115">enabled Attribute</span></span>

|<span data-ttu-id="f7bba-116">Valore</span><span class="sxs-lookup"><span data-stu-id="f7bba-116">Value</span></span>|<span data-ttu-id="f7bba-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f7bba-117">Description</span></span>|
|-----------|-----------------|
|`0`|<span data-ttu-id="f7bba-118">Il runtime usa l'architettura di marshalling di interoperabilità più veloce introdotta in .NET Framework 4, che non rileva e corregge platform invoke dichiarazioni non corrette.</span><span class="sxs-lookup"><span data-stu-id="f7bba-118">The runtime uses the faster interop marshaling architecture introduced in the .NET Framework 4, which does not detect and fix incorrect platform invoke declarations.</span></span> <span data-ttu-id="f7bba-119">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f7bba-119">This is the default.</span></span>|
|`1`|<span data-ttu-id="f7bba-120">Il runtime utilizza transizioni più lente che rilevano e correggono dichiarazioni di platform invoke non corrette.</span><span class="sxs-lookup"><span data-stu-id="f7bba-120">The runtime uses slower transitions that detect and fix incorrect platform invoke declarations.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="f7bba-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f7bba-121">Child Elements</span></span>

<span data-ttu-id="f7bba-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="f7bba-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f7bba-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f7bba-123">Parent Elements</span></span>

|<span data-ttu-id="f7bba-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="f7bba-124">Element</span></span>|<span data-ttu-id="f7bba-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f7bba-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="f7bba-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f7bba-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="f7bba-127">Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f7bba-127">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f7bba-128">Note</span><span class="sxs-lookup"><span data-stu-id="f7bba-128">Remarks</span></span>

<span data-ttu-id="f7bba-129">Questo elemento consente di effettuare il marshalling di interoperabilità più veloce per la resilienza in fase di esecuzione rispetto a dichiarazioni platform invoke non corrette.</span><span class="sxs-lookup"><span data-stu-id="f7bba-129">This element enables you to trade faster interop marshaling for run-time resilience against incorrect platform invoke declarations.</span></span>

<span data-ttu-id="f7bba-130">A partire da .NET Framework 4, un'architettura di marshalling di interoperabilità semplificata offre un miglioramento significativo delle prestazioni per le transizioni dal codice gestito al codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="f7bba-130">Starting with the .NET Framework 4, a streamlined interop marshaling architecture provides a significant performance improvement for transitions from managed code to unmanaged code.</span></span> <span data-ttu-id="f7bba-131">Nelle versioni precedenti del .NET Framework il livello di marshalling ha rilevato dichiarazioni di platform invoke non corrette sulle piattaforme a 32 bit e ha corretto automaticamente lo stack.</span><span class="sxs-lookup"><span data-stu-id="f7bba-131">In earlier versions of the .NET Framework, the marshaling layer detected incorrect platform invoke declarations on 32-bit platforms and automatically fixed the stack.</span></span> <span data-ttu-id="f7bba-132">La nuova architettura di marshalling elimina questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="f7bba-132">The new marshaling architecture eliminates this step.</span></span> <span data-ttu-id="f7bba-133">Di conseguenza, le transizioni sono molto veloci, ma una dichiarazione di platform invoke non corretta può causare un errore del programma.</span><span class="sxs-lookup"><span data-stu-id="f7bba-133">As a result, transitions are very fast, but an incorrect platform invoke declaration can cause a program failure.</span></span>

<span data-ttu-id="f7bba-134">Per semplificare il rilevamento di dichiarazioni non corrette durante lo sviluppo, è stata migliorata l'esperienza di debug di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f7bba-134">To make it easy to detect incorrect declarations during development, the Visual Studio debugging experience has been improved.</span></span> <span data-ttu-id="f7bba-135">L'assistente al debug gestito [pInvokeStackImbalance](../../../debug-trace-profile/pinvokestackimbalance-mda.md) Invia notifiche di Platform Invoke non corrette quando l'applicazione è in esecuzione con il debugger collegato.</span><span class="sxs-lookup"><span data-stu-id="f7bba-135">The [pInvokeStackImbalance](../../../debug-trace-profile/pinvokestackimbalance-mda.md) managed debugging assistant (MDA) notifies you of incorrect platform invoke declarations when your application is running with the debugger attached.</span></span>

<span data-ttu-id="f7bba-136">Per risolvere scenari in cui l'applicazione usa componenti che non è possibile ricompilare e che contengono dichiarazioni di Platform Invoke non corrette, è possibile `NetFx40_PInvokeStackResilience` usare l'elemento.</span><span class="sxs-lookup"><span data-stu-id="f7bba-136">To address scenarios where your application uses components that you cannot recompile, and that have incorrect platform invoke declarations, you can use the `NetFx40_PInvokeStackResilience` element.</span></span> <span data-ttu-id="f7bba-137">L'aggiunta di questo elemento al file di configurazione `enabled="1"` dell'applicazione con opta in una modalità di compatibilità con il comportamento delle versioni precedenti del .NET Framework, a scapito delle transizioni più lente.</span><span class="sxs-lookup"><span data-stu-id="f7bba-137">Adding this element to your application configuration file with `enabled="1"` opts into a compatibility mode with the behavior of earlier versions of the .NET Framework, at the cost of slower transitions.</span></span> <span data-ttu-id="f7bba-138">Gli assembly compilati con versioni precedenti del .NET Framework vengono automaticamente scelti in questa modalità di compatibilità e non richiedono questo elemento.</span><span class="sxs-lookup"><span data-stu-id="f7bba-138">Assemblies that have been compiled against earlier versions of the .NET Framework are automatically opted into this compatibility mode, and do not need this element.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="f7bba-139">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="f7bba-139">Configuration File</span></span>

<span data-ttu-id="f7bba-140">Questo elemento può essere utilizzato solo nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f7bba-140">This element can be used only in the application configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="f7bba-141">Esempio</span><span class="sxs-lookup"><span data-stu-id="f7bba-141">Example</span></span>

<span data-ttu-id="f7bba-142">Nell'esempio seguente viene illustrato come scegliere una maggiore resilienza in caso di dichiarazioni di platform invoke non corrette per un'applicazione, al costo di transizioni più lente tra codice gestito e non gestito.</span><span class="sxs-lookup"><span data-stu-id="f7bba-142">The following example shows how to opt into increased resilience against incorrect platform invoke declarations for an application, at the cost of slower transitions between managed and unmanaged code.</span></span>

```xml
<configuration>
   <runtime>
      <NetFx40_PInvokeStackResilience enabled="1"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="f7bba-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7bba-143">See also</span></span>

- [<span data-ttu-id="f7bba-144">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="f7bba-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f7bba-145">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="f7bba-145">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="f7bba-146">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="f7bba-146">pInvokeStackImbalance</span></span>](../../../debug-trace-profile/pinvokestackimbalance-mda.md)
