---
title: '&lt;aggiungere&gt; elemento per &lt;switch&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches/add
helpviewer_keywords:
- <add> element for <switches>
- add element for <switches>
ms.assetid: 712ac3a7-7abf-4a9e-8db4-acd241c2f369
caps.latest.revision: 
author: mcleblanc
ms.author: markl
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: 4406caa4da1375bea9809843ca96774e24421d5d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-element-for-ltswitchesgt"></a><span data-ttu-id="db8f2-102">&lt;aggiungere&gt; elemento per &lt;switch&gt;</span><span class="sxs-lookup"><span data-stu-id="db8f2-102">&lt;add&gt; Element for &lt;switches&gt;</span></span>
<span data-ttu-id="db8f2-103">Specifica il livello in cui viene impostata un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="db8f2-103">Specifies the level where a trace switch is set.</span></span>  
  
 <span data-ttu-id="db8f2-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="db8f2-104">\<configuration></span></span>  
<span data-ttu-id="db8f2-105">\<System. Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="db8f2-105">\<system.diagnostics></span></span>  
<span data-ttu-id="db8f2-106">\<Opzioni ></span><span class="sxs-lookup"><span data-stu-id="db8f2-106">\<switches></span></span>  
<span data-ttu-id="db8f2-107">\<add></span><span class="sxs-lookup"><span data-stu-id="db8f2-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db8f2-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="db8f2-108">Syntax</span></span>  
  
```xml  
<add name="switch name"  
     value="value"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="db8f2-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="db8f2-109">Attributes and Elements</span></span>  
 <span data-ttu-id="db8f2-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="db8f2-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="db8f2-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="db8f2-111">Attributes</span></span>  
  
|<span data-ttu-id="db8f2-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="db8f2-112">Attribute</span></span>|<span data-ttu-id="db8f2-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="db8f2-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="db8f2-114">**name**</span><span class="sxs-lookup"><span data-stu-id="db8f2-114">**name**</span></span>|<span data-ttu-id="db8f2-115">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="db8f2-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="db8f2-116">Specifica il nome del commutatore.</span><span class="sxs-lookup"><span data-stu-id="db8f2-116">Specifies the name of the switch.</span></span> <span data-ttu-id="db8f2-117">Il valore di questo attributo corrisponde alla *displayName* parametro passato al costruttore di opzioni.</span><span class="sxs-lookup"><span data-stu-id="db8f2-117">The value of this attribute corresponds to the *displayName* parameter that is passed to switch constructor.</span></span>|  
|<span data-ttu-id="db8f2-118">**value**</span><span class="sxs-lookup"><span data-stu-id="db8f2-118">**value**</span></span>|<span data-ttu-id="db8f2-119">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="db8f2-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="db8f2-120">Specifica il livello del commutatore.</span><span class="sxs-lookup"><span data-stu-id="db8f2-120">Specifies the level of the switch.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="db8f2-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="db8f2-121">Child Elements</span></span>  
 <span data-ttu-id="db8f2-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="db8f2-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="db8f2-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="db8f2-123">Parent Elements</span></span>  
  
|<span data-ttu-id="db8f2-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="db8f2-124">Element</span></span>|<span data-ttu-id="db8f2-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="db8f2-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="db8f2-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="db8f2-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`switches`|<span data-ttu-id="db8f2-127">Contiene le opzioni di traccia e il livello in cui vengono impostate le opzioni di traccia.</span><span class="sxs-lookup"><span data-stu-id="db8f2-127">Contains trace switches and the level where the trace switches are set.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="db8f2-128">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="db8f2-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db8f2-129">Note</span><span class="sxs-lookup"><span data-stu-id="db8f2-129">Remarks</span></span>  
 <span data-ttu-id="db8f2-130">È possibile modificare il livello di un'opzione di traccia mediante l'inserimento in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="db8f2-130">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="db8f2-131">Se l'opzione è un <xref:System.Diagnostics.BooleanSwitch>, è possibile attivare e disattivare.</span><span class="sxs-lookup"><span data-stu-id="db8f2-131">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="db8f2-132">Se l'opzione è un <xref:System.Diagnostics.TraceSwitch>, è possibile assegnare diversi livelli per specificare i tipi di traccia messaggi o di debug generati dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="db8f2-132">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="db8f2-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="db8f2-133">Example</span></span>  
 <span data-ttu-id="db8f2-134">Nell'esempio seguente viene illustrato come utilizzare il  **\<aggiungere >** elemento da impostare il `General` opzione di traccia di <xref:System.Diagnostics.TraceLevel> livello e attivare il `Data` opzione di traccia Boolean.</span><span class="sxs-lookup"><span data-stu-id="db8f2-134">The following example shows how to use the **\<add>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
         <add name="Data" value="1" />  
      </switches>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="db8f2-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db8f2-135">See Also</span></span>  
 <xref:System.Diagnostics.Switch>  
 <xref:System.Diagnostics.TraceSwitch>  
 <xref:System.Diagnostics.BooleanSwitch>  
 [<span data-ttu-id="db8f2-136">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="db8f2-136">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
