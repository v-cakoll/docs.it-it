---
title: <gcAllowVeryLargeObjects> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- gcAllowVeryLargeObjects element
- <gcAllowVeryLargeObjects> element
ms.assetid: 5c7ea24a-39ac-4e5f-83b7-b9f9a1b556ab
ms.openlocfilehash: 8b2f39a0867228474afdee788474fda11f14ca82
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154127"
---
# <a name="gcallowverylargeobjects-element"></a><span data-ttu-id="ac376-102">\<gcAllowVeryLargeObjects> Elemento</span><span class="sxs-lookup"><span data-stu-id="ac376-102">\<gcAllowVeryLargeObjects> Element</span></span>
<span data-ttu-id="ac376-103">Nelle piattaforme a 64 bit, abilita le matrici con dimensione totale maggiore di 2 gigabyte (GB).</span><span class="sxs-lookup"><span data-stu-id="ac376-103">On 64-bit platforms, enables arrays that are greater than 2 gigabytes (GB) in total size.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<gcAllowVeryLargeObjects>**  
  
## <a name="syntax"></a><span data-ttu-id="ac376-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ac376-104">Syntax</span></span>  
  
```xml  
<gcAllowVeryLargeObjects
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ac376-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ac376-105">Attributes and Elements</span></span>  
 <span data-ttu-id="ac376-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ac376-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ac376-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="ac376-107">Attributes</span></span>  
  
|<span data-ttu-id="ac376-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="ac376-108">Attribute</span></span>|<span data-ttu-id="ac376-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ac376-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="ac376-110">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="ac376-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="ac376-111">Specifica se le matrici con dimensione totale più grande di 2 GB sono abilitate nelle piattaforme a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="ac376-111">Specifies whether arrays that are greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="ac376-112">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="ac376-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="ac376-113">Valore</span><span class="sxs-lookup"><span data-stu-id="ac376-113">Value</span></span>|<span data-ttu-id="ac376-114">Description</span><span class="sxs-lookup"><span data-stu-id="ac376-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="ac376-115">Le matrici con dimensione totale più grande di 2 GB non sono abilitate.</span><span class="sxs-lookup"><span data-stu-id="ac376-115">Arrays greater than 2 GB in total size are not enabled.</span></span> <span data-ttu-id="ac376-116">Questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="ac376-116">This is the default.</span></span>|  
|`true`|<span data-ttu-id="ac376-117">Le matrici con dimensione totale più grande di 2 GB sono abilitate nelle piattaforme a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="ac376-117">Arrays greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ac376-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ac376-118">Child Elements</span></span>  
 <span data-ttu-id="ac376-119">No.</span><span class="sxs-lookup"><span data-stu-id="ac376-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ac376-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ac376-120">Parent Elements</span></span>  
  
|<span data-ttu-id="ac376-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="ac376-121">Element</span></span>|<span data-ttu-id="ac376-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ac376-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ac376-123">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ac376-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="ac376-124">Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ac376-124">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac376-125">Commenti</span><span class="sxs-lookup"><span data-stu-id="ac376-125">Remarks</span></span>  
 <span data-ttu-id="ac376-126">L'utilizzo di questo elemento nel file di configurazione dell'applicazione abilita le matrici con dimensione maggiori di 2 GB, ma non consente di modificare gli altri limiti relativi alla dimensione dell'oggetto o della matrice:</span><span class="sxs-lookup"><span data-stu-id="ac376-126">Using this element in your application configuration file enables arrays that are larger than 2 GB in size, but does not change other limits on object size or array size:</span></span>  
  
- <span data-ttu-id="ac376-127">Il numero massimo di elementi in una matrice è <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ac376-127">The maximum number of elements in an array is <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="ac376-128">L'indice massimo in ogni singola dimensione è 2.147.483.591 (0x7FFFFFC7) per le matrici di byte e le matrici di strutture a byte singolo e 2.146.435.071 (0X7FEFFFFF) per gli altri tipi.</span><span class="sxs-lookup"><span data-stu-id="ac376-128">The maximum index in any single dimension is 2,147,483,591 (0x7FFFFFC7) for byte arrays and arrays of single-byte structures, and 2,146,435,071 (0X7FEFFFFF) for other types.</span></span>  
  
- <span data-ttu-id="ac376-129">La dimensione massima consentita per le stringhe e altri oggetti diversi da matrici è invariata.</span><span class="sxs-lookup"><span data-stu-id="ac376-129">The maximum size for strings and other non-array objects is unchanged.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="ac376-130">Prima di abilitare questa funzionalità, assicurarsi che nell'applicazione non sia incluso codice di tipo unsafe in cui si presuppone che la dimensione di tutte le matrici sia inferiore a 2 GB.</span><span class="sxs-lookup"><span data-stu-id="ac376-130">Before enabling this feature, ensure that your application does not include unsafe code that assumes that all arrays are smaller than 2 GB in size.</span></span> <span data-ttu-id="ac376-131">Ad esempio, il codice di tipo unsafe in cui le matrici vengono utilizzate come buffer può essere soggetto a sovraccarichi del buffer se viene scritto partendo dal presupposto che le matrici non superino i 2 GB.</span><span class="sxs-lookup"><span data-stu-id="ac376-131">For example, unsafe code that uses arrays as buffers might be susceptible to buffer overruns if it is written on the assumption that arrays will not exceed 2 GB.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac376-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="ac376-132">Example</span></span>  
 <span data-ttu-id="ac376-133">Nell'esempio riportato di seguito viene illustrato come abilitare questa funzionalità per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ac376-133">The following example shows how to enable this feature for an application.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <gcAllowVeryLargeObjects enabled="true" />  
  </runtime>  
</configuration>  
```  
  
## <a name="supported-in"></a><span data-ttu-id="ac376-134">Supportato in</span><span class="sxs-lookup"><span data-stu-id="ac376-134">Supported in</span></span>

<span data-ttu-id="ac376-135">.NET Framework 4,5 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="ac376-135">.NET Framework 4.5 and later versions</span></span>

## <a name="see-also"></a><span data-ttu-id="ac376-136">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="ac376-136">See also</span></span>

- [<span data-ttu-id="ac376-137">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="ac376-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="ac376-138">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="ac376-138">Configuration File Schema</span></span>](../index.md)
