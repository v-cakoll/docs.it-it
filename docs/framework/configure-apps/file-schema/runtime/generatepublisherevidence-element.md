---
title: <generatePublisherEvidence> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
ms.openlocfilehash: 24a5ea02992a5bce681b5bab4fb7f75505bd225d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154114"
---
# <a name="generatepublisherevidence-element"></a><span data-ttu-id="2b2eb-102">\<Elemento generatePublisherEvidence></span><span class="sxs-lookup"><span data-stu-id="2b2eb-102">\<generatePublisherEvidence> Element</span></span>
<span data-ttu-id="2b2eb-103">Specifica se il <xref:System.Security.Policy.Publisher> runtime crea l'evidenza per la sicurezza dall'accesso di codice.</span><span class="sxs-lookup"><span data-stu-id="2b2eb-103">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence for code access security (CAS).</span></span>  
  
<span data-ttu-id="2b2eb-104">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2b2eb-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2b2eb-105">&nbsp;&nbsp;[**\<>di runtime**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="2b2eb-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="2b2eb-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<generare PublisherEvidence>**</span><span class="sxs-lookup"><span data-stu-id="2b2eb-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<generatePublisherEvidence>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b2eb-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2b2eb-107">Syntax</span></span>  
  
```xml  
<generatePublisherEvidence
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2b2eb-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2b2eb-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2b2eb-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2b2eb-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2b2eb-110">Attributes</span><span class="sxs-lookup"><span data-stu-id="2b2eb-110">Attributes</span></span>  
  
|<span data-ttu-id="2b2eb-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="2b2eb-111">Attribute</span></span>|<span data-ttu-id="2b2eb-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2b2eb-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="2b2eb-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="2b2eb-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="2b2eb-114">Specifica se il <xref:System.Security.Policy.Publisher> runtime crea l'evidenza.</span><span class="sxs-lookup"><span data-stu-id="2b2eb-114">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="2b2eb-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="2b2eb-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="2b2eb-116">valore</span><span class="sxs-lookup"><span data-stu-id="2b2eb-116">Value</span></span>|<span data-ttu-id="2b2eb-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2b2eb-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="2b2eb-118">Non crea <xref:System.Security.Policy.Publisher> prove.</span><span class="sxs-lookup"><span data-stu-id="2b2eb-118">Does not create <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
|`true`|<span data-ttu-id="2b2eb-119">Crea <xref:System.Security.Policy.Publisher> prove.</span><span class="sxs-lookup"><span data-stu-id="2b2eb-119">Creates <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="2b2eb-120">Questa è la modalità predefinita.</span><span class="sxs-lookup"><span data-stu-id="2b2eb-120">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2b2eb-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2b2eb-121">Child Elements</span></span>  
 <span data-ttu-id="2b2eb-122">No.</span><span class="sxs-lookup"><span data-stu-id="2b2eb-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2b2eb-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2b2eb-123">Parent Elements</span></span>  
  
|<span data-ttu-id="2b2eb-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="2b2eb-124">Element</span></span>|<span data-ttu-id="2b2eb-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2b2eb-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2b2eb-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2b2eb-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="2b2eb-127">Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2b2eb-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b2eb-128">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2b2eb-128">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2b2eb-129">In .NET Framework 4 e versioni successive, questo elemento non ha alcun effetto sui tempi di caricamento dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="2b2eb-129">In the .NET Framework 4 and later, this element has no effect on assembly load times.</span></span> <span data-ttu-id="2b2eb-130">Per ulteriori informazioni, vedere la sezione "Semplificazione dei criteri di sicurezza" in Modifiche alla [protezione](../../../security/security-changes.md).</span><span class="sxs-lookup"><span data-stu-id="2b2eb-130">For more information, see the "Security Policy Simplification" section in [Security Changes](../../../security/security-changes.md).</span></span>  
  
 <span data-ttu-id="2b2eb-131">Common Language Runtime (CLR) tenta di verificare la firma <xref:System.Security.Policy.Publisher> Authenticode in fase di caricamento per creare l'evidenza per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="2b2eb-131">The common language runtime (CLR) tries to verify the Authenticode signature at load time to create <xref:System.Security.Policy.Publisher> evidence for the assembly.</span></span> <span data-ttu-id="2b2eb-132">Tuttavia, per impostazione predefinita, la maggior parte delle applicazioni non richiedono <xref:System.Security.Policy.Publisher> prove.</span><span class="sxs-lookup"><span data-stu-id="2b2eb-132">However, by default, most applications do not need <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="2b2eb-133">I criteri CAS standard <xref:System.Security.Policy.PublisherMembershipCondition>non si basano sul file .</span><span class="sxs-lookup"><span data-stu-id="2b2eb-133">Standard CAS policy does not rely on the <xref:System.Security.Policy.PublisherMembershipCondition>.</span></span> <span data-ttu-id="2b2eb-134">È consigliabile evitare il costo di avvio non necessario associato alla verifica della firma dell'editore, a meno che l'applicazione non venga eseguita in un computer con criteri CAS personalizzati o non intenda soddisfare le richieste <xref:System.Security.Permissions.PublisherIdentityPermission> in un ambiente parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="2b2eb-134">You should avoid the unnecessary startup cost associated with verifying the publisher signature unless your application executes on a computer with custom CAS policy, or is intending to satisfy demands for <xref:System.Security.Permissions.PublisherIdentityPermission> in a partial-trust environment.</span></span> <span data-ttu-id="2b2eb-135">Le richieste di autorizzazioni di identità hanno sempre esito positivo in un ambiente con attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="2b2eb-135">(Demands for identity permissions always succeed in a full-trust environment.)</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2b2eb-136">È consigliabile che `<generatePublisherEvidence>` i servizi utilizzino l'elemento per migliorare le prestazioni di avvio.</span><span class="sxs-lookup"><span data-stu-id="2b2eb-136">We recommend that services use the `<generatePublisherEvidence>` element to improve startup performance.</span></span>  <span data-ttu-id="2b2eb-137">L'utilizzo di questo elemento consente inoltre di evitare ritardi che possono causare un timeout e l'annullamento dell'avvio del servizio.</span><span class="sxs-lookup"><span data-stu-id="2b2eb-137">Using this element can also help avoid delays that can cause a time-out and the cancellation of the service startup.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="2b2eb-138">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="2b2eb-138">Configuration File</span></span>  
 <span data-ttu-id="2b2eb-139">Questo elemento può essere utilizzato solo nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2b2eb-139">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b2eb-140">Esempio</span><span class="sxs-lookup"><span data-stu-id="2b2eb-140">Example</span></span>  
 <span data-ttu-id="2b2eb-141">Nell'esempio seguente viene `<generatePublisherEvidence>` illustrato come utilizzare l'elemento per disabilitare il controllo dei criteri editore CAS per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2b2eb-141">The following example shows how to use the `<generatePublisherEvidence>` element to disable checking for CAS publisher policy for an application.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2b2eb-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b2eb-142">See also</span></span>

- [<span data-ttu-id="2b2eb-143">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="2b2eb-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="2b2eb-144">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="2b2eb-144">Configuration File Schema</span></span>](../index.md)
