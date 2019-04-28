---
title: Elemento <NetFx45_CultureAwareComparerGetHashCode_LongStrings>
ms.date: 03/30/2017
helpviewer_keywords:
- NetFx45_CultureAwareComparerGetHashCode_LongStrings element
- <NetFx45_CultureAwareComparerGetHashCode_LongStrings> element
- GetHashCode method
- hash codes, calculating
ms.assetid: 3a5f38d1-ebc8-44de-aaeb-2929f6e6b48f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 854b58a1f57008326874b5e5ee60cc9e6297960b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674041"
---
# <a name="netfx45cultureawarecomparergethashcodelongstrings-element"></a><span data-ttu-id="a978a-102">\<NetFx45_CultureAwareComparerGetHashCode_LongStrings > elemento</span><span class="sxs-lookup"><span data-stu-id="a978a-102">\<NetFx45_CultureAwareComparerGetHashCode_LongStrings> Element</span></span>
<span data-ttu-id="a978a-103">Specifica se il runtime utilizza una quantità di memoria fissa per calcolare i codici hash per il metodo <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="a978a-103">Specifies whether the runtime uses a fixed amount of memory to calculate hash codes for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="a978a-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a978a-104">\<configuration></span></span>  
<span data-ttu-id="a978a-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="a978a-105">\<runtime></span></span>  
<span data-ttu-id="a978a-106"><NetFx45_CultureAwareComparerGetHashCode_LongStrings></span><span class="sxs-lookup"><span data-stu-id="a978a-106"><NetFx45_CultureAwareComparerGetHashCode_LongStrings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a978a-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a978a-107">Syntax</span></span>  
  
```xml
<NetFx45_CultureAwareComparerGetHashCode_LongStrings enabled="0|1">  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a978a-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a978a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a978a-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a978a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a978a-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="a978a-110">Attributes</span></span>  
  
|<span data-ttu-id="a978a-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="a978a-111">Attribute</span></span>|<span data-ttu-id="a978a-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a978a-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="a978a-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a978a-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="a978a-114">Specifica se tramite Common Language Runtime viene allocata una quantità di memoria fissa durante il calcolo dei codici hash.</span><span class="sxs-lookup"><span data-stu-id="a978a-114">Specifies whether the common language runtime allocates a fixed amount of memory when calculating hash codes.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="a978a-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="a978a-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="a978a-116">Valore</span><span class="sxs-lookup"><span data-stu-id="a978a-116">Value</span></span>|<span data-ttu-id="a978a-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a978a-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a978a-118">0</span><span class="sxs-lookup"><span data-stu-id="a978a-118">0</span></span>|<span data-ttu-id="a978a-119">Specifica se tramite Common Language Runtime viene allocata una quantità di memoria variabile al metodo <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> per il calcolo dei codici hash.</span><span class="sxs-lookup"><span data-stu-id="a978a-119">The common language runtime allocates a variable amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method to calculate hash codes.</span></span> <span data-ttu-id="a978a-120">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="a978a-120">This is the default.</span></span>|  
|<span data-ttu-id="a978a-121">1</span><span class="sxs-lookup"><span data-stu-id="a978a-121">1</span></span>|<span data-ttu-id="a978a-122">Specifica se tramite Common Language Runtime viene allocata una quantità di memoria fissa al metodo <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> per il calcolo dei codici hash.</span><span class="sxs-lookup"><span data-stu-id="a978a-122">The common language runtime allocates a fixed amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method to calculate hash codes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a978a-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a978a-123">Child Elements</span></span>  
 <span data-ttu-id="a978a-124">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="a978a-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a978a-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a978a-125">Parent Elements</span></span>  
  
|<span data-ttu-id="a978a-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="a978a-126">Element</span></span>|<span data-ttu-id="a978a-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a978a-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a978a-128">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a978a-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a978a-129">Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a978a-129">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a978a-130">Note</span><span class="sxs-lookup"><span data-stu-id="a978a-130">Remarks</span></span>  
 <span data-ttu-id="a978a-131">Per impostazione predefinita, tramite Common Language Runtime viene allocata una quantità di memoria variabile per il metodo <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> e <xref:System.ArgumentException> può essere generata quando il metodo tenta di calcolare il codice hash di stringhe di dimensioni considerevoli (oltre diversi milioni di caratteri).</span><span class="sxs-lookup"><span data-stu-id="a978a-131">By default, the common language runtime allocates a variable amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method, and an <xref:System.ArgumentException> can be thrown when the method attempts to compute the hash code of very large strings (over several million characters long).</span></span> <span data-ttu-id="a978a-132">Aggiungendo questo elemento a un file di configurazione dell'applicazione e impostando il relativo attributo `enabled` su "1", è possibile specificare che il metodo <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> utilizza un algoritmo alternativo che alloca una quantità di memoria fissa per il calcolo di codici hash.</span><span class="sxs-lookup"><span data-stu-id="a978a-132">By adding this element to an application configuration file and setting its `enabled` attribute to "1", you can specify that the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method use an alternate algorithm that allocates a fixed amount of memory for the computation of hash codes.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a978a-133">L'elemento di `<NetFx45_CultureAwareComparerGetHashCode_LongStrings>` non viene utilizzato in [!INCLUDE[win8](../../../../../includes/win8-md.md)] e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="a978a-133">The `<NetFx45_CultureAwareComparerGetHashCode_LongStrings>` element is not used in [!INCLUDE[win8](../../../../../includes/win8-md.md)] and later versions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a978a-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a978a-134">See also</span></span>

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- [<span data-ttu-id="a978a-135">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="a978a-135">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="a978a-136">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="a978a-136">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
