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
ms.openlocfilehash: 15cc9680d7a20341eb5d1d1df302c1e034e70e02
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153230"
---
# <a name="switches-element"></a><span data-ttu-id="f6d60-102">\<switches> Elemento</span><span class="sxs-lookup"><span data-stu-id="f6d60-102">\<switches> Element</span></span>
<span data-ttu-id="f6d60-103">Contiene le opzioni di traccia e il livello in cui vengono impostate le opzioni di traccia.</span><span class="sxs-lookup"><span data-stu-id="f6d60-103">Contains trace switches and the level where the trace switches are set.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<switches>**

## <a name="syntax"></a><span data-ttu-id="f6d60-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f6d60-104">Syntax</span></span>  
  
```xml  
      <switches>
</switches>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f6d60-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f6d60-105">Attributes and Elements</span></span>  
 <span data-ttu-id="f6d60-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f6d60-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f6d60-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="f6d60-107">Attributes</span></span>  
 <span data-ttu-id="f6d60-108">No.</span><span class="sxs-lookup"><span data-stu-id="f6d60-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f6d60-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f6d60-109">Child Elements</span></span>  
  
|<span data-ttu-id="f6d60-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="f6d60-110">Element</span></span>|<span data-ttu-id="f6d60-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f6d60-111">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-element-for-switches.md)|<span data-ttu-id="f6d60-112">Specifica il livello in cui viene impostata un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="f6d60-112">Specifies the level where a trace switch is set.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f6d60-113">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f6d60-113">Parent Elements</span></span>  
  
|<span data-ttu-id="f6d60-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="f6d60-114">Element</span></span>|<span data-ttu-id="f6d60-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f6d60-115">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f6d60-116">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f6d60-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`System.diagnostics`|<span data-ttu-id="f6d60-117">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="f6d60-117">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6d60-118">Commenti</span><span class="sxs-lookup"><span data-stu-id="f6d60-118">Remarks</span></span>  
 <span data-ttu-id="f6d60-119">È possibile modificare il livello di un'opzione di traccia inserendola in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f6d60-119">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="f6d60-120">Se l'opzione è un <xref:System.Diagnostics.BooleanSwitch> , è possibile attivarla o disattivarla.</span><span class="sxs-lookup"><span data-stu-id="f6d60-120">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="f6d60-121">Se l'opzione è un <xref:System.Diagnostics.TraceSwitch> , è possibile assegnare livelli diversi per specificare i tipi di traccia o i messaggi di debug restituiti dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f6d60-121">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f6d60-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="f6d60-122">Example</span></span>  
 <span data-ttu-id="f6d60-123">Nell'esempio seguente viene illustrato come utilizzare l' **\<switch>** elemento per impostare l' `General` opzione di traccia sul <xref:System.Diagnostics.TraceLevel> livello e abilitare l' `Data` opzione di traccia booleana.</span><span class="sxs-lookup"><span data-stu-id="f6d60-123">The following example shows how to use the **\<switch>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f6d60-124">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="f6d60-124">See also</span></span>

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [<span data-ttu-id="f6d60-125">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="f6d60-125">Trace and Debug Settings Schema</span></span>](index.md)
