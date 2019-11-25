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
ms.openlocfilehash: 4aeb3cb0cd75f0fb27e3b359b86da61a77b491c7
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088796"
---
# <a name="switches-element"></a><span data-ttu-id="97c79-102">\<Opzioni > elemento</span><span class="sxs-lookup"><span data-stu-id="97c79-102">\<switches> Element</span></span>
<span data-ttu-id="97c79-103">Contiene le opzioni di traccia e il livello in cui vengono impostate le opzioni di traccia.</span><span class="sxs-lookup"><span data-stu-id="97c79-103">Contains trace switches and the level where the trace switches are set.</span></span>  

<span data-ttu-id="97c79-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="97c79-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="97c79-105">&nbsp;&nbsp;[ **\<System. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="97c79-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="97c79-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<opzioni >**</span><span class="sxs-lookup"><span data-stu-id="97c79-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<switches>**</span></span>

## <a name="syntax"></a><span data-ttu-id="97c79-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="97c79-107">Syntax</span></span>  
  
```xml  
      <switches>   
</switches>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="97c79-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="97c79-108">Attributes and Elements</span></span>  
 <span data-ttu-id="97c79-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="97c79-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="97c79-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="97c79-110">Attributes</span></span>  
 <span data-ttu-id="97c79-111">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="97c79-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="97c79-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="97c79-112">Child Elements</span></span>  
  
|<span data-ttu-id="97c79-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="97c79-113">Element</span></span>|<span data-ttu-id="97c79-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="97c79-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="97c79-115">\<add></span><span class="sxs-lookup"><span data-stu-id="97c79-115">\<add></span></span>](add-element-for-switches.md)|<span data-ttu-id="97c79-116">Specifica il livello in cui viene impostata un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="97c79-116">Specifies the level where a trace switch is set.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="97c79-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="97c79-117">Parent Elements</span></span>  
  
|<span data-ttu-id="97c79-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="97c79-118">Element</span></span>|<span data-ttu-id="97c79-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="97c79-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="97c79-120">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="97c79-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`System.diagnostics`|<span data-ttu-id="97c79-121">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="97c79-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97c79-122">Note</span><span class="sxs-lookup"><span data-stu-id="97c79-122">Remarks</span></span>  
 <span data-ttu-id="97c79-123">È possibile modificare il livello di un'opzione di traccia inserendola in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="97c79-123">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="97c79-124">Se l'opzione è una <xref:System.Diagnostics.BooleanSwitch>, è possibile attivarla o disattivarla.</span><span class="sxs-lookup"><span data-stu-id="97c79-124">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="97c79-125">Se l'opzione è una <xref:System.Diagnostics.TraceSwitch>, è possibile assegnare livelli diversi per specificare i tipi di traccia o i messaggi di debug restituiti dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="97c79-125">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97c79-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="97c79-126">Example</span></span>  
 <span data-ttu-id="97c79-127">Nell'esempio seguente viene illustrato come utilizzare l' **opzione\<** elemento per impostare l'opzione di traccia `General` sul livello di <xref:System.Diagnostics.TraceLevel> e abilitare l'opzione di traccia `Data` booleana.</span><span class="sxs-lookup"><span data-stu-id="97c79-127">The following example shows how to use the **\<switch>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="97c79-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97c79-128">See also</span></span>

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [<span data-ttu-id="97c79-129">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="97c79-129">Trace and Debug Settings Schema</span></span>](index.md)
