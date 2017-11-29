---
title: '&lt;commutatori&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches
- http://schemas.microsoft.com/.NetConfiguration/v2.0#switches
helpviewer_keywords:
- <switches> element
- switches element
- trace switches, <switches> element
ms.assetid: 4cf36786-b89a-40e2-a0f1-86bb9b783343
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 6240f8192f2a31faeb81528e54481eb06cc04d04
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltswitchesgt-element"></a><span data-ttu-id="00066-102">&lt;commutatori&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="00066-102">&lt;switches&gt; Element</span></span>
<span data-ttu-id="00066-103">Contiene le opzioni di traccia e il livello in cui vengono impostate le opzioni di traccia.</span><span class="sxs-lookup"><span data-stu-id="00066-103">Contains trace switches and the level where the trace switches are set.</span></span>  
  
 <span data-ttu-id="00066-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="00066-104">\<configuration></span></span>  
<span data-ttu-id="00066-105">\<System. Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="00066-105">\<system.diagnostics></span></span>  
<span data-ttu-id="00066-106">\<Opzioni ></span><span class="sxs-lookup"><span data-stu-id="00066-106">\<switches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00066-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="00066-107">Syntax</span></span>  
  
```xml  
      <switches>   
</switches>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="00066-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="00066-108">Attributes and Elements</span></span>  
 <span data-ttu-id="00066-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="00066-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="00066-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="00066-110">Attributes</span></span>  
 <span data-ttu-id="00066-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="00066-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="00066-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="00066-112">Child Elements</span></span>  
  
|<span data-ttu-id="00066-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="00066-113">Element</span></span>|<span data-ttu-id="00066-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="00066-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="00066-115">\<add></span><span class="sxs-lookup"><span data-stu-id="00066-115">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-switches.md)|<span data-ttu-id="00066-116">Specifica il livello in cui viene impostata un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="00066-116">Specifies the level where a trace switch is set.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="00066-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="00066-117">Parent Elements</span></span>  
  
|<span data-ttu-id="00066-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="00066-118">Element</span></span>|<span data-ttu-id="00066-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="00066-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="00066-120">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="00066-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`System.diagnostics`|<span data-ttu-id="00066-121">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="00066-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00066-122">Note</span><span class="sxs-lookup"><span data-stu-id="00066-122">Remarks</span></span>  
 <span data-ttu-id="00066-123">È possibile modificare il livello di un'opzione di traccia mediante l'inserimento in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="00066-123">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="00066-124">Se l'opzione è un <xref:System.Diagnostics.BooleanSwitch>, è possibile attivare e disattivare.</span><span class="sxs-lookup"><span data-stu-id="00066-124">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="00066-125">Se l'opzione è un <xref:System.Diagnostics.TraceSwitch>, è possibile assegnare diversi livelli per specificare i tipi di traccia messaggi o di debug generati dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="00066-125">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00066-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="00066-126">Example</span></span>  
 <span data-ttu-id="00066-127">Nell'esempio seguente viene illustrato come utilizzare il  **\<passare >** elemento da impostare il `General` opzione di traccia di <xref:System.Diagnostics.TraceLevel> livello e attivare il `Data` opzione di traccia Boolean.</span><span class="sxs-lookup"><span data-stu-id="00066-127">The following example shows how to use the **\<switch>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="00066-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00066-128">See Also</span></span>  
 <xref:System.Diagnostics.Switch>  
 <xref:System.Diagnostics.TraceSwitch>  
 <xref:System.Diagnostics.BooleanSwitch>  
 [<span data-ttu-id="00066-129">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="00066-129">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
