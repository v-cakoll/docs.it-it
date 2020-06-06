---
title: Elemento <add> per <switches>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches/add
helpviewer_keywords:
- <add> element for <switches>
- add element for <switches>
ms.assetid: 712ac3a7-7abf-4a9e-8db4-acd241c2f369
ms.openlocfilehash: db2de681227dfdb7420808963219b9f52381f8fe
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088953"
---
# <a name="add-element-for-switches"></a><span data-ttu-id="da25c-102">Elemento \<add> per \<switches></span><span class="sxs-lookup"><span data-stu-id="da25c-102">\<add> Element for \<switches></span></span>
<span data-ttu-id="da25c-103">Specifica il livello in cui viene impostata un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="da25c-103">Specifies the level where a trace switch is set.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<switches>**](switches-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="da25c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="da25c-104">Syntax</span></span>  
  
```xml  
<add name="switch name"  
     value="value"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="da25c-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="da25c-105">Attributes and Elements</span></span>  
 <span data-ttu-id="da25c-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="da25c-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="da25c-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="da25c-107">Attributes</span></span>  
  
|<span data-ttu-id="da25c-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="da25c-108">Attribute</span></span>|<span data-ttu-id="da25c-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="da25c-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="da25c-110">**nome**</span><span class="sxs-lookup"><span data-stu-id="da25c-110">**name**</span></span>|<span data-ttu-id="da25c-111">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="da25c-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="da25c-112">Specifica il nome dell'opzione.</span><span class="sxs-lookup"><span data-stu-id="da25c-112">Specifies the name of the switch.</span></span> <span data-ttu-id="da25c-113">Il valore di questo attributo corrisponde al parametro *DisplayName* passato al costruttore Switch.</span><span class="sxs-lookup"><span data-stu-id="da25c-113">The value of this attribute corresponds to the *displayName* parameter that is passed to switch constructor.</span></span>|  
|<span data-ttu-id="da25c-114">**value**</span><span class="sxs-lookup"><span data-stu-id="da25c-114">**value**</span></span>|<span data-ttu-id="da25c-115">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="da25c-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="da25c-116">Specifica il livello dell'opzione.</span><span class="sxs-lookup"><span data-stu-id="da25c-116">Specifies the level of the switch.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="da25c-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="da25c-117">Child Elements</span></span>  
 <span data-ttu-id="da25c-118">No.</span><span class="sxs-lookup"><span data-stu-id="da25c-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="da25c-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="da25c-119">Parent Elements</span></span>  
  
|<span data-ttu-id="da25c-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="da25c-120">Element</span></span>|<span data-ttu-id="da25c-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="da25c-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="da25c-122">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="da25c-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`switches`|<span data-ttu-id="da25c-123">Contiene le opzioni di traccia e il livello in cui vengono impostate le opzioni di traccia.</span><span class="sxs-lookup"><span data-stu-id="da25c-123">Contains trace switches and the level where the trace switches are set.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="da25c-124">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="da25c-124">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="da25c-125">Commenti</span><span class="sxs-lookup"><span data-stu-id="da25c-125">Remarks</span></span>  
 <span data-ttu-id="da25c-126">È possibile modificare il livello di un'opzione di traccia inserendola in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="da25c-126">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="da25c-127">Se l'opzione è un <xref:System.Diagnostics.BooleanSwitch> , è possibile attivarla o disattivarla.</span><span class="sxs-lookup"><span data-stu-id="da25c-127">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="da25c-128">Se l'opzione è un <xref:System.Diagnostics.TraceSwitch> , è possibile assegnare livelli diversi per specificare i tipi di traccia o i messaggi di debug restituiti dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="da25c-128">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="da25c-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="da25c-129">Example</span></span>  
 <span data-ttu-id="da25c-130">Nell'esempio seguente viene illustrato come utilizzare l' **\<add>** elemento per impostare l' `General` opzione di traccia sul <xref:System.Diagnostics.TraceLevel> livello e abilitare l' `Data` opzione di traccia booleana.</span><span class="sxs-lookup"><span data-stu-id="da25c-130">The following example shows how to use the **\<add>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="da25c-131">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="da25c-131">See also</span></span>

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [<span data-ttu-id="da25c-132">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="da25c-132">Trace and Debug Settings Schema</span></span>](index.md)
