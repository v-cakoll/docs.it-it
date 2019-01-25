---
title: '&lt;legacyCorruptedStateExceptionsPolicy&gt; Element'
ms.date: 03/30/2017
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 14b8940fa0c5c7ceb4a14fdd0f40867c7be9f65e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54737715"
---
# <a name="ltlegacycorruptedstateexceptionspolicygt-element"></a><span data-ttu-id="b6d13-102">&lt;legacyCorruptedStateExceptionsPolicy&gt; Element</span><span class="sxs-lookup"><span data-stu-id="b6d13-102">&lt;legacyCorruptedStateExceptionsPolicy&gt; Element</span></span>
<span data-ttu-id="b6d13-103">Specifica se common language runtime consente al codice gestito rilevare le violazioni di accesso e altre eccezioni stato danneggiato.</span><span class="sxs-lookup"><span data-stu-id="b6d13-103">Specifies whether the common language runtime allows managed code to catch access violations and other corrupted state exceptions.</span></span>  
  
 <span data-ttu-id="b6d13-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b6d13-104">\<configuration></span></span>  
<span data-ttu-id="b6d13-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="b6d13-105">\<runtime></span></span>  
<span data-ttu-id="b6d13-106">\<legacyCorruptedStateExceptionsPolicy></span><span class="sxs-lookup"><span data-stu-id="b6d13-106">\<legacyCorruptedStateExceptionsPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6d13-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b6d13-107">Syntax</span></span>  
  
```xml  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b6d13-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b6d13-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b6d13-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b6d13-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b6d13-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="b6d13-110">Attributes</span></span>  
  
|<span data-ttu-id="b6d13-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="b6d13-111">Attribute</span></span>|<span data-ttu-id="b6d13-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6d13-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="b6d13-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b6d13-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="b6d13-114">Specifica che l'applicazione verrà intercettare le eccezioni di stato danneggiato, ad esempio le violazioni di accesso.</span><span class="sxs-lookup"><span data-stu-id="b6d13-114">Specifies that the application will catch corrupting state exception failures such as access violations.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="b6d13-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="b6d13-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="b6d13-116">Valore</span><span class="sxs-lookup"><span data-stu-id="b6d13-116">Value</span></span>|<span data-ttu-id="b6d13-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6d13-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="b6d13-118">L'applicazione non rileva le eccezioni di stato danneggiato, ad esempio le violazioni di accesso.</span><span class="sxs-lookup"><span data-stu-id="b6d13-118">The application will not catch corrupting state exception failures such as access violations.</span></span> <span data-ttu-id="b6d13-119">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b6d13-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="b6d13-120">L'applicazione rileva le eccezioni di stato danneggiato, ad esempio le violazioni di accesso.</span><span class="sxs-lookup"><span data-stu-id="b6d13-120">The application will catch corrupting state exception failures such as access violations.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b6d13-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b6d13-121">Child Elements</span></span>  
 <span data-ttu-id="b6d13-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="b6d13-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b6d13-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b6d13-123">Parent Elements</span></span>  
  
|<span data-ttu-id="b6d13-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="b6d13-124">Element</span></span>|<span data-ttu-id="b6d13-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6d13-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b6d13-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b6d13-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="b6d13-127">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="b6d13-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6d13-128">Note</span><span class="sxs-lookup"><span data-stu-id="b6d13-128">Remarks</span></span>  
 <span data-ttu-id="b6d13-129">In .NET Framework versione 3.5 e versioni precedenti, common language runtime consente al codice gestito intercettare le eccezioni che sono state generate gli stati di processo danneggiato.</span><span class="sxs-lookup"><span data-stu-id="b6d13-129">In the .NET Framework version 3.5 and earlier, the common language runtime allowed managed code to catch exceptions that were raised by corrupted process states.</span></span> <span data-ttu-id="b6d13-130">Una violazione di accesso è un esempio di questo tipo di eccezione.</span><span class="sxs-lookup"><span data-stu-id="b6d13-130">An access violation is an example of this type of exception.</span></span>  
  
 <span data-ttu-id="b6d13-131">Inizia con la [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]gestiti, codice non è più rileva questi tipi di eccezioni in `catch` blocchi.</span><span class="sxs-lookup"><span data-stu-id="b6d13-131">Starting with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], managed code no longer catches these types of exceptions in `catch` blocks.</span></span> <span data-ttu-id="b6d13-132">Tuttavia, è possibile eseguire l'override di questa modifica e mantenere la gestione delle eccezioni stato danneggiato in due modi:</span><span class="sxs-lookup"><span data-stu-id="b6d13-132">However, you can override this change and maintain the handling of corrupted state exceptions in two ways:</span></span>  
  
-   <span data-ttu-id="b6d13-133">Impostare il `<legacyCorruptedStateExceptionsPolicy>` dell'elemento `enabled` dell'attributo `true`.</span><span class="sxs-lookup"><span data-stu-id="b6d13-133">Set the `<legacyCorruptedStateExceptionsPolicy>` element's `enabled` attribute to `true`.</span></span> <span data-ttu-id="b6d13-134">Questa impostazione di configurazione viene applicata all'intero processo e influisce su tutti i metodi.</span><span class="sxs-lookup"><span data-stu-id="b6d13-134">This configuration setting is applied processwide and affects all methods.</span></span>  
  
 <span data-ttu-id="b6d13-135">-oppure-</span><span class="sxs-lookup"><span data-stu-id="b6d13-135">-or-</span></span>  
  
-   <span data-ttu-id="b6d13-136">Si applicano i <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> al metodo che contiene le eccezioni `catch` blocco.</span><span class="sxs-lookup"><span data-stu-id="b6d13-136">Apply the <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> attribute to the method that contains the exceptions `catch` block.</span></span>  
  
 <span data-ttu-id="b6d13-137">Questo elemento di configurazione è disponibile solo nel [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="b6d13-137">This configuration element is available only in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6d13-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="b6d13-138">Example</span></span>  
 <span data-ttu-id="b6d13-139">Nell'esempio seguente viene illustrato come specificare che l'applicazione viene ripristinato il comportamento prima di [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]e rilevare tutte le eccezioni stato danneggiato.</span><span class="sxs-lookup"><span data-stu-id="b6d13-139">The following example shows how to specify that the application should revert to the behavior before the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], and catch all corrupting state exception failures.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b6d13-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6d13-140">See also</span></span>
- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>
- [<span data-ttu-id="b6d13-141">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="b6d13-141">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="b6d13-142">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="b6d13-142">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
