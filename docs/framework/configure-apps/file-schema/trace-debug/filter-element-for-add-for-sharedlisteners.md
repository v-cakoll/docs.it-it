---
title: <filter>Elemento per <add> per<sharedListeners>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add/filter
helpviewer_keywords:
- filter element for <add> for <sharedListeners>
- initializeData attribute
- <filter> element for <add> for <sharedListeners>
- filters, trace listeners
- trace listeners, filters
ms.assetid: 7d4e7faa-2e4e-4379-ac76-f6cd7f2f8fac
ms.openlocfilehash: 6fb52cdfa5792ab6059b60d8dbb91c107cd666ca
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153453"
---
# <a name="filter-element-for-add-for-sharedlisteners"></a><span data-ttu-id="53b93-102">\<filter>Elemento per \<add> per\<sharedListeners></span><span class="sxs-lookup"><span data-stu-id="53b93-102">\<filter> Element for \<add> for \<sharedListeners></span></span>
<span data-ttu-id="53b93-103">Aggiunge un filtro a un listener nella raccolta `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="53b93-103">Adds a filter to a listener in the `sharedListeners` collection.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sharedListeners>**](sharedlisteners-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-sharedlisteners.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**

## <a name="syntax"></a><span data-ttu-id="53b93-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="53b93-104">Syntax</span></span>  
  
```xml  
<filter type="System.Diagnostics.EventTypeFilter"
  initializeData="Warning" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="53b93-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="53b93-105">Attributes and Elements</span></span>  
 <span data-ttu-id="53b93-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="53b93-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="53b93-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="53b93-107">Attributes</span></span>  
  
|<span data-ttu-id="53b93-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="53b93-108">Attribute</span></span>|<span data-ttu-id="53b93-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53b93-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="53b93-110">**type**</span><span class="sxs-lookup"><span data-stu-id="53b93-110">**type**</span></span>|<span data-ttu-id="53b93-111">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="53b93-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="53b93-112">Specifica il tipo di filtro.</span><span class="sxs-lookup"><span data-stu-id="53b93-112">Specifies the type of the filter.</span></span> <span data-ttu-id="53b93-113">È possibile utilizzare solo il nome completo del tipo (nel formato della <xref:System.Type.FullName%2A?displayProperty=nameWithType> proprietà) oppure è possibile utilizzare il nome completo del tipo, incluse le informazioni sull'assembly (nel formato della <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> proprietà).</span><span class="sxs-lookup"><span data-stu-id="53b93-113">You can use only the full name of the type (in the format of the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property), or you can use the fully qualified type name including the assembly information (in the format of the <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> property).</span></span> <span data-ttu-id="53b93-114">Per informazioni sulla creazione di un nome di tipo completo, vedere [specifica di nomi di tipo](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)completi.</span><span class="sxs-lookup"><span data-stu-id="53b93-114">For information on creating a fully qualified type name, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="53b93-115">**initializeData**</span><span class="sxs-lookup"><span data-stu-id="53b93-115">**initializeData**</span></span>|<span data-ttu-id="53b93-116">Attributo facoltativo.</span><span class="sxs-lookup"><span data-stu-id="53b93-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="53b93-117">Stringa passata al costruttore per la classe specificata.</span><span class="sxs-lookup"><span data-stu-id="53b93-117">The string passed to the constructor for the specified class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="53b93-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="53b93-118">Child Elements</span></span>  
 <span data-ttu-id="53b93-119">No.</span><span class="sxs-lookup"><span data-stu-id="53b93-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="53b93-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="53b93-120">Parent Elements</span></span>  
  
|<span data-ttu-id="53b93-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="53b93-121">Element</span></span>|<span data-ttu-id="53b93-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53b93-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="53b93-123">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="53b93-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="53b93-124">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="53b93-124">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="53b93-125">Raccolta di listener a cui qualsiasi origine o elemento Trace può fare riferimento.</span><span class="sxs-lookup"><span data-stu-id="53b93-125">A collection of listeners that any source or trace element can reference.</span></span>|  
|`add`|<span data-ttu-id="53b93-126">Aggiunge un listener alla raccolta **sharedListeners** .</span><span class="sxs-lookup"><span data-stu-id="53b93-126">Adds a listener to the **sharedListeners** collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53b93-127">Commenti</span><span class="sxs-lookup"><span data-stu-id="53b93-127">Remarks</span></span>  
 <span data-ttu-id="53b93-128">Se un listener viene definito in un `<add>` elemento dell' `<sharedListeners>` elemento, il filtro per il listener deve essere definito in un `<filter>` elemento figlio dell' `<add>` elemento.</span><span class="sxs-lookup"><span data-stu-id="53b93-128">If a listener is defined in an `<add>` element of the `<sharedListeners>` element, the filter for that listener should be defined in a `<filter>` element that is a child of the `<add>` element.</span></span>  
  
 <span data-ttu-id="53b93-129">Questo elemento può essere utilizzato nel file di configurazione del computer (Machine. config) e nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="53b93-129">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="53b93-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="53b93-130">Example</span></span>  
 <span data-ttu-id="53b93-131">Nell'esempio seguente viene illustrato come utilizzare l' `<filter>` elemento per aggiungere un filtro al listener di traccia `console` nella `sharedListeners` raccolta.</span><span class="sxs-lookup"><span data-stu-id="53b93-131">The following example shows how to use the `<filter>` element to add a filter to the trace listener `console` in the `sharedListeners` collection.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="myTraceSource" >  
        <listeners>  
          <add name="console" />  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="console"
        type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"
          initializeData="Error" />  
      </add>  
    </sharedListeners>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="53b93-132">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="53b93-132">See also</span></span>

- <xref:System.Diagnostics.TraceFilter>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="53b93-133">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="53b93-133">Trace and Debug Settings Schema</span></span>](index.md)
