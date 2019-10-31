---
title: <generatePublisherEvidence> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
ms.openlocfilehash: b04ef53d6e9c3d954b0925ea8634b3d220b36af7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73116580"
---
# <a name="generatepublisherevidence-element"></a><span data-ttu-id="41e9b-102">\<elemento > generatePublisherEvidence</span><span class="sxs-lookup"><span data-stu-id="41e9b-102">\<generatePublisherEvidence> Element</span></span>
<span data-ttu-id="41e9b-103">Specifica se il runtime crea <xref:System.Security.Policy.Publisher> evidenza per la sicurezza dall'accesso di codice (CAS).</span><span class="sxs-lookup"><span data-stu-id="41e9b-103">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence for code access security (CAS).</span></span>  
  
<span data-ttu-id="41e9b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="41e9b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="41e9b-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="41e9b-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="41e9b-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<generatePublisherEvidence >**</span><span class="sxs-lookup"><span data-stu-id="41e9b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<generatePublisherEvidence>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41e9b-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="41e9b-107">Syntax</span></span>  
  
```xml  
<generatePublisherEvidence    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="41e9b-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="41e9b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="41e9b-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="41e9b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="41e9b-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="41e9b-110">Attributes</span></span>  
  
|<span data-ttu-id="41e9b-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="41e9b-111">Attribute</span></span>|<span data-ttu-id="41e9b-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="41e9b-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="41e9b-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="41e9b-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="41e9b-114">Specifica se il runtime crea <xref:System.Security.Policy.Publisher> evidenza.</span><span class="sxs-lookup"><span data-stu-id="41e9b-114">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="41e9b-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="41e9b-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="41e9b-116">Value</span><span class="sxs-lookup"><span data-stu-id="41e9b-116">Value</span></span>|<span data-ttu-id="41e9b-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="41e9b-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="41e9b-118">Non crea <xref:System.Security.Policy.Publisher> evidenza.</span><span class="sxs-lookup"><span data-stu-id="41e9b-118">Does not create <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
|`true`|<span data-ttu-id="41e9b-119">Crea <xref:System.Security.Policy.Publisher> evidenza.</span><span class="sxs-lookup"><span data-stu-id="41e9b-119">Creates <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="41e9b-120">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="41e9b-120">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="41e9b-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="41e9b-121">Child Elements</span></span>  
 <span data-ttu-id="41e9b-122">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="41e9b-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="41e9b-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="41e9b-123">Parent Elements</span></span>  
  
|<span data-ttu-id="41e9b-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="41e9b-124">Element</span></span>|<span data-ttu-id="41e9b-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="41e9b-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="41e9b-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="41e9b-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="41e9b-127">Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="41e9b-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="41e9b-128">Note</span><span class="sxs-lookup"><span data-stu-id="41e9b-128">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="41e9b-129">In .NET Framework 4 e versioni successive, questo elemento non ha alcun effetto sui tempi di caricamento degli assembly.</span><span class="sxs-lookup"><span data-stu-id="41e9b-129">In the .NET Framework 4 and later, this element has no effect on assembly load times.</span></span> <span data-ttu-id="41e9b-130">Per ulteriori informazioni, vedere la sezione "semplificazione dei criteri di sicurezza" in [modifiche della sicurezza](../../../security/security-changes.md).</span><span class="sxs-lookup"><span data-stu-id="41e9b-130">For more information, see the "Security Policy Simplification" section in [Security Changes](../../../security/security-changes.md).</span></span>  
  
 <span data-ttu-id="41e9b-131">Il Common Language Runtime (CLR) tenta di verificare la firma Authenticode in fase di caricamento per creare <xref:System.Security.Policy.Publisher> evidenza per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="41e9b-131">The common language runtime (CLR) tries to verify the Authenticode signature at load time to create <xref:System.Security.Policy.Publisher> evidence for the assembly.</span></span> <span data-ttu-id="41e9b-132">Per impostazione predefinita, tuttavia, la maggior parte delle applicazioni non necessita di <xref:System.Security.Policy.Publisher> evidenze.</span><span class="sxs-lookup"><span data-stu-id="41e9b-132">However, by default, most applications do not need <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="41e9b-133">I criteri CAS standard non si basano sul <xref:System.Security.Policy.PublisherMembershipCondition>.</span><span class="sxs-lookup"><span data-stu-id="41e9b-133">Standard CAS policy does not rely on the <xref:System.Security.Policy.PublisherMembershipCondition>.</span></span> <span data-ttu-id="41e9b-134">È consigliabile evitare il costo di avvio non necessario associato alla verifica della firma del server di pubblicazione, a meno che l'applicazione non venga eseguita in un computer con criteri di protezione accesso alla classe personalizzati o si intenda soddisfare le richieste di <xref:System.Security.Permissions.PublisherIdentityPermission> in un ambiente parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="41e9b-134">You should avoid the unnecessary startup cost associated with verifying the publisher signature unless your application executes on a computer with custom CAS policy, or is intending to satisfy demands for <xref:System.Security.Permissions.PublisherIdentityPermission> in a partial-trust environment.</span></span> <span data-ttu-id="41e9b-135">(Le richieste di autorizzazioni di identità hanno sempre esito positivo in un ambiente con attendibilità totale).</span><span class="sxs-lookup"><span data-stu-id="41e9b-135">(Demands for identity permissions always succeed in a full-trust environment.)</span></span>  
  
> [!NOTE]
> <span data-ttu-id="41e9b-136">È consigliabile che i servizi usino l'elemento `<generatePublisherEvidence>` per migliorare le prestazioni di avvio.</span><span class="sxs-lookup"><span data-stu-id="41e9b-136">We recommend that services use the `<generatePublisherEvidence>` element to improve startup performance.</span></span>  <span data-ttu-id="41e9b-137">L'uso di questo elemento consente inoltre di evitare ritardi che possono causare un timeout e l'annullamento dell'avvio del servizio.</span><span class="sxs-lookup"><span data-stu-id="41e9b-137">Using this element can also help avoid delays that can cause a time-out and the cancellation of the service startup.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="41e9b-138">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="41e9b-138">Configuration File</span></span>  
 <span data-ttu-id="41e9b-139">Questo elemento può essere utilizzato solo nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="41e9b-139">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="41e9b-140">Esempio</span><span class="sxs-lookup"><span data-stu-id="41e9b-140">Example</span></span>  
 <span data-ttu-id="41e9b-141">Nell'esempio seguente viene illustrato come utilizzare l'elemento `<generatePublisherEvidence>` per disabilitare il controllo dei criteri di pubblicazione CAS per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="41e9b-141">The following example shows how to use the `<generatePublisherEvidence>` element to disable checking for CAS publisher policy for an application.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="41e9b-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41e9b-142">See also</span></span>

- [<span data-ttu-id="41e9b-143">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="41e9b-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="41e9b-144">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="41e9b-144">Configuration File Schema</span></span>](../index.md)
