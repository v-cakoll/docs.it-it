---
title: <switches> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches
- http://schemas.microsoft.com/.NetConfiguration/v2.0#switches
helpviewer_keywords:
- <switches> element
- switches element
- trace switches, <switches> element
ms.assetid: 4cf36786-b89a-40e2-a0f1-86bb9b783343
ms.openlocfilehash: 44f5c918f19f84daf827ad4e8f3b6bfbc3e9f439
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704505"
---
# <a name="switches-element"></a><span data-ttu-id="d5310-102">\<Opzioni > elemento</span><span class="sxs-lookup"><span data-stu-id="d5310-102">\<switches> Element</span></span>
<span data-ttu-id="d5310-103">Contiene le opzioni di traccia e il livello in cui vengono impostate le opzioni di traccia.</span><span class="sxs-lookup"><span data-stu-id="d5310-103">Contains trace switches and the level where the trace switches are set.</span></span>  
  
 <span data-ttu-id="d5310-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d5310-104">\<configuration></span></span>  
<span data-ttu-id="d5310-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="d5310-105">\<system.diagnostics></span></span>  
<span data-ttu-id="d5310-106">\<switches></span><span class="sxs-lookup"><span data-stu-id="d5310-106">\<switches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5310-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d5310-107">Syntax</span></span>  
  
```xml  
      <switches>   
</switches>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d5310-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d5310-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d5310-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d5310-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d5310-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="d5310-110">Attributes</span></span>  
 <span data-ttu-id="d5310-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="d5310-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d5310-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d5310-112">Child Elements</span></span>  
  
|<span data-ttu-id="d5310-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="d5310-113">Element</span></span>|<span data-ttu-id="d5310-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d5310-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d5310-115">\<add></span><span class="sxs-lookup"><span data-stu-id="d5310-115">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-switches.md)|<span data-ttu-id="d5310-116">Specifica il livello in cui viene impostata un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="d5310-116">Specifies the level where a trace switch is set.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d5310-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d5310-117">Parent Elements</span></span>  
  
|<span data-ttu-id="d5310-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="d5310-118">Element</span></span>|<span data-ttu-id="d5310-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d5310-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d5310-120">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d5310-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`System.diagnostics`|<span data-ttu-id="d5310-121">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="d5310-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5310-122">Note</span><span class="sxs-lookup"><span data-stu-id="d5310-122">Remarks</span></span>  
 <span data-ttu-id="d5310-123">È possibile modificare il livello di un'opzione di traccia inserendolo in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d5310-123">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="d5310-124">Se l'opzione è un <xref:System.Diagnostics.BooleanSwitch>, è possibile attivare e disattivare.</span><span class="sxs-lookup"><span data-stu-id="d5310-124">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="d5310-125">Se l'opzione è un <xref:System.Diagnostics.TraceSwitch>, è possibile assegnare diversi livelli per specificare i tipi di traccia o debug messaggi generati dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d5310-125">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5310-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="d5310-126">Example</span></span>  
 <span data-ttu-id="d5310-127">Nell'esempio seguente viene illustrato come utilizzare il  **\<passare >** elemento per cui impostare il `General` opzione di traccia il <xref:System.Diagnostics.TraceLevel> livello e attivare il `Data` commutatore di traccia di tipo Boolean.</span><span class="sxs-lookup"><span data-stu-id="d5310-127">The following example shows how to use the **\<switch>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d5310-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5310-128">See also</span></span>

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [<span data-ttu-id="d5310-129">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="d5310-129">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
