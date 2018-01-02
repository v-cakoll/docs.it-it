---
title: '&lt;generatePublisherEvidence&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c7f7debed03526dbd7a5b2e24ff8a370921fe020
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltgeneratepublisherevidencegt-element"></a><span data-ttu-id="9e4cc-102">&lt;generatePublisherEvidence&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="9e4cc-102">&lt;generatePublisherEvidence&gt; Element</span></span>
<span data-ttu-id="9e4cc-103">Specifica se il runtime crea <xref:System.Security.Policy.Publisher> evidenza di sicurezza dall'accesso di codice (CAS).</span><span class="sxs-lookup"><span data-stu-id="9e4cc-103">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence for code access security (CAS).</span></span>  
  
 <span data-ttu-id="9e4cc-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9e4cc-104">\<configuration></span></span>  
<span data-ttu-id="9e4cc-105">\<runtime ></span><span class="sxs-lookup"><span data-stu-id="9e4cc-105">\<runtime></span></span>  
<span data-ttu-id="9e4cc-106">\<generatePublisherEvidence ></span><span class="sxs-lookup"><span data-stu-id="9e4cc-106">\<generatePublisherEvidence></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e4cc-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9e4cc-107">Syntax</span></span>  
  
```xml  
<generatePublisherEvidence    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9e4cc-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9e4cc-108">Attributes and Elements</span></span>  
 <span data-ttu-id="9e4cc-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9e4cc-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9e4cc-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="9e4cc-110">Attributes</span></span>  
  
|<span data-ttu-id="9e4cc-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="9e4cc-111">Attribute</span></span>|<span data-ttu-id="9e4cc-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9e4cc-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="9e4cc-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="9e4cc-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="9e4cc-114">Specifica se il runtime crea <xref:System.Security.Policy.Publisher> evidenza.</span><span class="sxs-lookup"><span data-stu-id="9e4cc-114">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="9e4cc-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="9e4cc-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="9e4cc-116">Valore</span><span class="sxs-lookup"><span data-stu-id="9e4cc-116">Value</span></span>|<span data-ttu-id="9e4cc-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9e4cc-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="9e4cc-118">Non creare <xref:System.Security.Policy.Publisher> evidenza.</span><span class="sxs-lookup"><span data-stu-id="9e4cc-118">Does not create <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
|`true`|<span data-ttu-id="9e4cc-119">Crea <xref:System.Security.Policy.Publisher> evidenza.</span><span class="sxs-lookup"><span data-stu-id="9e4cc-119">Creates <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="9e4cc-120">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="9e4cc-120">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9e4cc-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9e4cc-121">Child Elements</span></span>  
 <span data-ttu-id="9e4cc-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="9e4cc-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9e4cc-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9e4cc-123">Parent Elements</span></span>  
  
|<span data-ttu-id="9e4cc-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="9e4cc-124">Element</span></span>|<span data-ttu-id="9e4cc-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9e4cc-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9e4cc-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9e4cc-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="9e4cc-127">Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9e4cc-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e4cc-128">Note</span><span class="sxs-lookup"><span data-stu-id="9e4cc-128">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e4cc-129">Nel [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] e versioni successive, l'elemento non ha alcun effetto sui tempi di caricamento di assembly.</span><span class="sxs-lookup"><span data-stu-id="9e4cc-129">In the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] and later, this element has no effect on assembly load times.</span></span> <span data-ttu-id="9e4cc-130">Per ulteriori informazioni, vedere la sezione "Semplificazione dei criteri di sicurezza" in [modifiche della sicurezza](../../../../../docs/framework/security/security-changes.md).</span><span class="sxs-lookup"><span data-stu-id="9e4cc-130">For more information, see the "Security Policy Simplification" section in [Security Changes](../../../../../docs/framework/security/security-changes.md).</span></span>  
  
 <span data-ttu-id="9e4cc-131">Common language runtime (CLR) tenta di verificare la firma Authenticode in fase di caricamento per creare <xref:System.Security.Policy.Publisher> evidenza per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="9e4cc-131">The common language runtime (CLR) tries to verify the Authenticode signature at load time to create <xref:System.Security.Policy.Publisher> evidence for the assembly.</span></span> <span data-ttu-id="9e4cc-132">Tuttavia, per impostazione predefinita, la maggior parte delle applicazioni non è necessario <xref:System.Security.Policy.Publisher> evidenza.</span><span class="sxs-lookup"><span data-stu-id="9e4cc-132">However, by default, most applications do not need <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="9e4cc-133">Criteri di sicurezza standard per fare affidamento su di <xref:System.Security.Policy.PublisherMembershipCondition>.</span><span class="sxs-lookup"><span data-stu-id="9e4cc-133">Standard CAS policy does not rely on the <xref:System.Security.Policy.PublisherMembershipCondition>.</span></span> <span data-ttu-id="9e4cc-134">È consigliabile evitare il costo di esecuzione automatica non necessari associato alla verifica della firma dell'editore a meno che non viene eseguita in un computer con criteri di sicurezza personalizzato per l'applicazione o non sia progettata per soddisfare le richieste per <xref:System.Security.Permissions.PublisherIdentityPermission> in un ambiente parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="9e4cc-134">You should avoid the unnecessary startup cost associated with verifying the publisher signature unless your application executes on a computer with custom CAS policy, or is intending to satisfy demands for <xref:System.Security.Permissions.PublisherIdentityPermission> in a partial-trust environment.</span></span> <span data-ttu-id="9e4cc-135">(Le richieste per le autorizzazioni di identità sempre esito positivo in un ambiente completamente attendibile).</span><span class="sxs-lookup"><span data-stu-id="9e4cc-135">(Demands for identity permissions always succeed in a full-trust environment.)</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e4cc-136">È consigliabile che i servizi utilizzino la `<generatePublisherEvidence>` elemento per migliorare le prestazioni di avvio.</span><span class="sxs-lookup"><span data-stu-id="9e4cc-136">We recommend that services use the `<generatePublisherEvidence>` element to improve startup performance.</span></span>  <span data-ttu-id="9e4cc-137">Utilizzo di questo elemento consente inoltre di evitare ritardi che possono causare un timeout e l'annullamento dell'avvio del servizio.</span><span class="sxs-lookup"><span data-stu-id="9e4cc-137">Using this element can also help avoid delays that can cause a time-out and the cancellation of the service startup.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="9e4cc-138">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="9e4cc-138">Configuration File</span></span>  
 <span data-ttu-id="9e4cc-139">Questo elemento può essere usato solo nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9e4cc-139">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e4cc-140">Esempio</span><span class="sxs-lookup"><span data-stu-id="9e4cc-140">Example</span></span>  
 <span data-ttu-id="9e4cc-141">Nell'esempio seguente viene illustrato come utilizzare il `<generatePublisherEvidence>` elemento per disabilitare la verifica dei criteri dell'editore di autorità di certificazione per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9e4cc-141">The following example shows how to use the `<generatePublisherEvidence>` element to disable checking for CAS publisher policy for an application.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9e4cc-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e4cc-142">See Also</span></span>  
 [<span data-ttu-id="9e4cc-143">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="9e4cc-143">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="9e4cc-144">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="9e4cc-144">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
