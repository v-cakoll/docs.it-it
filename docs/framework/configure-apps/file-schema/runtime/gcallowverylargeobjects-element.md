---
title: '&lt;gcAllowVeryLargeObjects&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- gcAllowVeryLargeObjects element
- <gcAllowVeryLargeObjects> element
ms.assetid: 5c7ea24a-39ac-4e5f-83b7-b9f9a1b556ab
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b5db777f147e2eca7644d5b5f1a4bc18c8401ca8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltgcallowverylargeobjectsgt-element"></a><span data-ttu-id="702dc-102">&lt;gcAllowVeryLargeObjects&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="702dc-102">&lt;gcAllowVeryLargeObjects&gt; Element</span></span>
<span data-ttu-id="702dc-103">Nelle piattaforme a 64 bit, abilita le matrici con dimensione totale maggiore di 2 gigabyte (GB).</span><span class="sxs-lookup"><span data-stu-id="702dc-103">On 64-bit platforms, enables arrays that are greater than 2 gigabytes (GB) in total size.</span></span>  
  
 <span data-ttu-id="702dc-104">\<configurazione > elemento</span><span class="sxs-lookup"><span data-stu-id="702dc-104">\<configuration> Element</span></span>  
<span data-ttu-id="702dc-105">\<runtime > elemento</span><span class="sxs-lookup"><span data-stu-id="702dc-105">\<runtime> Element</span></span>  
<span data-ttu-id="702dc-106">\<gcAllowVeryLargeObjects > elemento</span><span class="sxs-lookup"><span data-stu-id="702dc-106">\<gcAllowVeryLargeObjects> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="702dc-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="702dc-107">Syntax</span></span>  
  
```xml  
<gcAllowVeryLargeObjects    
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="702dc-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="702dc-108">Attributes and Elements</span></span>  
 <span data-ttu-id="702dc-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="702dc-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="702dc-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="702dc-110">Attributes</span></span>  
  
|<span data-ttu-id="702dc-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="702dc-111">Attribute</span></span>|<span data-ttu-id="702dc-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="702dc-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="702dc-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="702dc-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="702dc-114">Specifica se le matrici con dimensione totale più grande di 2 GB sono abilitate nelle piattaforme a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="702dc-114">Specifies whether arrays that are greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="702dc-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="702dc-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="702dc-116">Valore</span><span class="sxs-lookup"><span data-stu-id="702dc-116">Value</span></span>|<span data-ttu-id="702dc-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="702dc-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="702dc-118">Le matrici con dimensione totale più grande di 2 GB non sono abilitate.</span><span class="sxs-lookup"><span data-stu-id="702dc-118">Arrays greater than 2 GB in total size are not enabled.</span></span> <span data-ttu-id="702dc-119">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="702dc-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="702dc-120">Le matrici con dimensione totale più grande di 2 GB sono abilitate nelle piattaforme a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="702dc-120">Arrays greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="702dc-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="702dc-121">Child Elements</span></span>  
 <span data-ttu-id="702dc-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="702dc-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="702dc-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="702dc-123">Parent Elements</span></span>  
  
|<span data-ttu-id="702dc-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="702dc-124">Element</span></span>|<span data-ttu-id="702dc-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="702dc-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="702dc-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="702dc-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="702dc-127">Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="702dc-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="702dc-128">Note</span><span class="sxs-lookup"><span data-stu-id="702dc-128">Remarks</span></span>  
 <span data-ttu-id="702dc-129">L'utilizzo di questo elemento nel file di configurazione dell'applicazione abilita le matrici con dimensione maggiori di 2 GB, ma non consente di modificare gli altri limiti relativi alla dimensione dell'oggetto o della matrice:</span><span class="sxs-lookup"><span data-stu-id="702dc-129">Using this element in your application configuration file enables arrays that are larger than 2 GB in size, but does not change other limits on object size or array size:</span></span>  
  
-   <span data-ttu-id="702dc-130">Il numero massimo di elementi in una matrice è <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="702dc-130">The maximum number of elements in an array is <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="702dc-131">L'indice massimo in ogni singola dimensione è 2.147.483.591 (0x7FFFFFC7) per le matrici di byte e le matrici di strutture a byte singolo e 2.146.435.071 (0X7FEFFFFF) per gli altri tipi.</span><span class="sxs-lookup"><span data-stu-id="702dc-131">The maximum index in any single dimension is 2,147,483,591 (0x7FFFFFC7) for byte arrays and arrays of single-byte structures, and 2,146,435,071 (0X7FEFFFFF) for other types.</span></span>  
  
-   <span data-ttu-id="702dc-132">La dimensione massima consentita per le stringhe e altri oggetti diversi da matrici è invariata.</span><span class="sxs-lookup"><span data-stu-id="702dc-132">The maximum size for strings and other non-array objects is unchanged.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="702dc-133">Prima di abilitare questa funzionalità, assicurarsi che nell'applicazione non sia incluso codice di tipo unsafe in cui si presuppone che la dimensione di tutte le matrici sia inferiore a 2 GB.</span><span class="sxs-lookup"><span data-stu-id="702dc-133">Before enabling this feature, ensure that your application does not include unsafe code that assumes that all arrays are smaller than 2 GB in size.</span></span> <span data-ttu-id="702dc-134">Ad esempio, il codice di tipo unsafe in cui le matrici vengono utilizzate come buffer può essere soggetto a sovraccarichi del buffer se viene scritto partendo dal presupposto che le matrici non superino i 2 GB.</span><span class="sxs-lookup"><span data-stu-id="702dc-134">For example, unsafe code that uses arrays as buffers might be susceptible to buffer overruns if it is written on the assumption that arrays will not exceed 2 GB.</span></span>  
  
## <a name="example"></a><span data-ttu-id="702dc-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="702dc-135">Example</span></span>  
 <span data-ttu-id="702dc-136">Nell'esempio riportato di seguito viene illustrato come abilitare questa funzionalità per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="702dc-136">The following example shows how to enable this feature for an application.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <gcAllowVeryLargeObjects enabled="true" />  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="702dc-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="702dc-137">See Also</span></span>  
 [<span data-ttu-id="702dc-138">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="702dc-138">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="702dc-139">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="702dc-139">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
