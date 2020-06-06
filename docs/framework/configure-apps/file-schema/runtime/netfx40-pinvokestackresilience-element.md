---
title: Elemento < NetFx40_PInvokeStackResilience >
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_PInvokeStackResilience> element
- NetFx40_PInvokeStackResilience element
ms.assetid: 39fb1588-72a4-4479-af74-0605233b68bd
ms.openlocfilehash: 86f50aafe0b21d5080288e09ac7118ca1e4c939a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73116156"
---
# <a name="netfx40_pinvokestackresilience-element"></a><span data-ttu-id="5b63c-102">\<NetFx40_PInvokeStackResilience> Elemento</span><span class="sxs-lookup"><span data-stu-id="5b63c-102">\<NetFx40_PInvokeStackResilience> Element</span></span>

<span data-ttu-id="5b63c-103">Specifica se il runtime corregge automaticamente le dichiarazioni platform invoke non corrette in fase di esecuzione, al costo di transizioni più lente tra codice gestito e quello non gestito.</span><span class="sxs-lookup"><span data-stu-id="5b63c-103">Specifies whether the runtime automatically fixes incorrect platform invoke declarations at run time, at the cost of slower transitions between managed and unmanaged code.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<NetFx40_PInvokeStackResilience>**  

## <a name="syntax"></a><span data-ttu-id="5b63c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5b63c-104">Syntax</span></span>

```xml
<NetFx40_PInvokeStackResilience  enabled="1|0"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5b63c-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="5b63c-105">Attributes and Elements</span></span>

<span data-ttu-id="5b63c-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="5b63c-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="5b63c-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="5b63c-107">Attributes</span></span>

|<span data-ttu-id="5b63c-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="5b63c-108">Attribute</span></span>|<span data-ttu-id="5b63c-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5b63c-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="5b63c-110">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="5b63c-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="5b63c-111">Specifica se il runtime rileva dichiarazioni di platform invoke non corrette e corregge automaticamente lo stack in fase di esecuzione sulle piattaforme a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="5b63c-111">Specifies whether the runtime detects incorrect platform invoke declarations and automatically fixes the stack at run time on 32-bit platforms.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="5b63c-112">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="5b63c-112">enabled Attribute</span></span>

|<span data-ttu-id="5b63c-113">Valore</span><span class="sxs-lookup"><span data-stu-id="5b63c-113">Value</span></span>|<span data-ttu-id="5b63c-114">Description</span><span class="sxs-lookup"><span data-stu-id="5b63c-114">Description</span></span>|
|-----------|-----------------|
|`0`|<span data-ttu-id="5b63c-115">Il runtime usa l'architettura di marshalling di interoperabilità più veloce introdotta in .NET Framework 4, che non rileva e corregge platform invoke dichiarazioni non corrette.</span><span class="sxs-lookup"><span data-stu-id="5b63c-115">The runtime uses the faster interop marshaling architecture introduced in the .NET Framework 4, which does not detect and fix incorrect platform invoke declarations.</span></span> <span data-ttu-id="5b63c-116">Questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="5b63c-116">This is the default.</span></span>|
|`1`|<span data-ttu-id="5b63c-117">Il runtime utilizza transizioni più lente che rilevano e correggono dichiarazioni di platform invoke non corrette.</span><span class="sxs-lookup"><span data-stu-id="5b63c-117">The runtime uses slower transitions that detect and fix incorrect platform invoke declarations.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="5b63c-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="5b63c-118">Child Elements</span></span>

<span data-ttu-id="5b63c-119">No.</span><span class="sxs-lookup"><span data-stu-id="5b63c-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="5b63c-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="5b63c-120">Parent Elements</span></span>

|<span data-ttu-id="5b63c-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="5b63c-121">Element</span></span>|<span data-ttu-id="5b63c-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5b63c-122">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="5b63c-123">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5b63c-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="5b63c-124">Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="5b63c-124">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5b63c-125">Commenti</span><span class="sxs-lookup"><span data-stu-id="5b63c-125">Remarks</span></span>

<span data-ttu-id="5b63c-126">Questo elemento consente di effettuare il marshalling di interoperabilità più veloce per la resilienza in fase di esecuzione rispetto a dichiarazioni platform invoke non corrette.</span><span class="sxs-lookup"><span data-stu-id="5b63c-126">This element enables you to trade faster interop marshaling for run-time resilience against incorrect platform invoke declarations.</span></span>

<span data-ttu-id="5b63c-127">A partire da .NET Framework 4, un'architettura di marshalling di interoperabilità semplificata offre un miglioramento significativo delle prestazioni per le transizioni dal codice gestito al codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="5b63c-127">Starting with the .NET Framework 4, a streamlined interop marshaling architecture provides a significant performance improvement for transitions from managed code to unmanaged code.</span></span> <span data-ttu-id="5b63c-128">Nelle versioni precedenti del .NET Framework il livello di marshalling ha rilevato dichiarazioni di platform invoke non corrette sulle piattaforme a 32 bit e ha corretto automaticamente lo stack.</span><span class="sxs-lookup"><span data-stu-id="5b63c-128">In earlier versions of the .NET Framework, the marshaling layer detected incorrect platform invoke declarations on 32-bit platforms and automatically fixed the stack.</span></span> <span data-ttu-id="5b63c-129">La nuova architettura di marshalling elimina questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="5b63c-129">The new marshaling architecture eliminates this step.</span></span> <span data-ttu-id="5b63c-130">Di conseguenza, le transizioni sono molto veloci, ma una dichiarazione di platform invoke non corretta può causare un errore del programma.</span><span class="sxs-lookup"><span data-stu-id="5b63c-130">As a result, transitions are very fast, but an incorrect platform invoke declaration can cause a program failure.</span></span>

<span data-ttu-id="5b63c-131">Per semplificare il rilevamento di dichiarazioni non corrette durante lo sviluppo, è stata migliorata l'esperienza di debug di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5b63c-131">To make it easy to detect incorrect declarations during development, the Visual Studio debugging experience has been improved.</span></span> <span data-ttu-id="5b63c-132">L'assistente al debug gestito [pInvokeStackImbalance](../../../debug-trace-profile/pinvokestackimbalance-mda.md) Invia notifiche di Platform Invoke non corrette quando l'applicazione è in esecuzione con il debugger collegato.</span><span class="sxs-lookup"><span data-stu-id="5b63c-132">The [pInvokeStackImbalance](../../../debug-trace-profile/pinvokestackimbalance-mda.md) managed debugging assistant (MDA) notifies you of incorrect platform invoke declarations when your application is running with the debugger attached.</span></span>

<span data-ttu-id="5b63c-133">Per risolvere scenari in cui l'applicazione usa componenti che non è possibile ricompilare e che contengono dichiarazioni di platform invoke non corrette, è possibile usare l' `NetFx40_PInvokeStackResilience` elemento.</span><span class="sxs-lookup"><span data-stu-id="5b63c-133">To address scenarios where your application uses components that you cannot recompile, and that have incorrect platform invoke declarations, you can use the `NetFx40_PInvokeStackResilience` element.</span></span> <span data-ttu-id="5b63c-134">L'aggiunta di questo elemento al file di configurazione dell'applicazione con `enabled="1"` opta in una modalità di compatibilità con il comportamento delle versioni precedenti del .NET Framework, a scapito delle transizioni più lente.</span><span class="sxs-lookup"><span data-stu-id="5b63c-134">Adding this element to your application configuration file with `enabled="1"` opts into a compatibility mode with the behavior of earlier versions of the .NET Framework, at the cost of slower transitions.</span></span> <span data-ttu-id="5b63c-135">Gli assembly compilati con versioni precedenti del .NET Framework vengono automaticamente scelti in questa modalità di compatibilità e non richiedono questo elemento.</span><span class="sxs-lookup"><span data-stu-id="5b63c-135">Assemblies that have been compiled against earlier versions of the .NET Framework are automatically opted into this compatibility mode, and do not need this element.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="5b63c-136">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="5b63c-136">Configuration File</span></span>

<span data-ttu-id="5b63c-137">Questo elemento può essere utilizzato solo nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5b63c-137">This element can be used only in the application configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="5b63c-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="5b63c-138">Example</span></span>

<span data-ttu-id="5b63c-139">Nell'esempio seguente viene illustrato come scegliere una maggiore resilienza in caso di dichiarazioni di platform invoke non corrette per un'applicazione, al costo di transizioni più lente tra codice gestito e non gestito.</span><span class="sxs-lookup"><span data-stu-id="5b63c-139">The following example shows how to opt into increased resilience against incorrect platform invoke declarations for an application, at the cost of slower transitions between managed and unmanaged code.</span></span>

```xml
<configuration>
   <runtime>
      <NetFx40_PInvokeStackResilience enabled="1"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="5b63c-140">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="5b63c-140">See also</span></span>

- [<span data-ttu-id="5b63c-141">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="5b63c-141">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="5b63c-142">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="5b63c-142">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="5b63c-143">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="5b63c-143">pInvokeStackImbalance</span></span>](../../../debug-trace-profile/pinvokestackimbalance-mda.md)
