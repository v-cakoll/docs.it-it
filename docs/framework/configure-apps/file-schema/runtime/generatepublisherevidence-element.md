---
title: <generatePublisherEvidence> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
ms.openlocfilehash: c2ba4a7244b7849e28eac38fb34a2cdd0d1f1048
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "81645349"
---
# <a name="generatepublisherevidence-element"></a><span data-ttu-id="c1e16-102">\<generatePublisherEvidence> Elemento</span><span class="sxs-lookup"><span data-stu-id="c1e16-102">\<generatePublisherEvidence> Element</span></span>
<span data-ttu-id="c1e16-103">Specifica se il runtime crea <xref:System.Security.Policy.Publisher> evidenza per la sicurezza dall'accesso di codice (CAS).</span><span class="sxs-lookup"><span data-stu-id="c1e16-103">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence for code access security (CAS).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<generatePublisherEvidence>**  
  
## <a name="syntax"></a><span data-ttu-id="c1e16-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c1e16-104">Syntax</span></span>  
  
```xml  
<generatePublisherEvidence
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c1e16-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c1e16-105">Attributes and Elements</span></span>  
 <span data-ttu-id="c1e16-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c1e16-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c1e16-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="c1e16-107">Attributes</span></span>  
  
|<span data-ttu-id="c1e16-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="c1e16-108">Attribute</span></span>|<span data-ttu-id="c1e16-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c1e16-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="c1e16-110">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="c1e16-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="c1e16-111">Specifica se il runtime crea la <xref:System.Security.Policy.Publisher> prova.</span><span class="sxs-lookup"><span data-stu-id="c1e16-111">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="c1e16-112">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="c1e16-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="c1e16-113">Valore</span><span class="sxs-lookup"><span data-stu-id="c1e16-113">Value</span></span>|<span data-ttu-id="c1e16-114">Description</span><span class="sxs-lookup"><span data-stu-id="c1e16-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="c1e16-115">Non crea <xref:System.Security.Policy.Publisher> evidenze.</span><span class="sxs-lookup"><span data-stu-id="c1e16-115">Does not create <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
|`true`|<span data-ttu-id="c1e16-116">Crea l' <xref:System.Security.Policy.Publisher> evidenza.</span><span class="sxs-lookup"><span data-stu-id="c1e16-116">Creates <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="c1e16-117">Questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="c1e16-117">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c1e16-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c1e16-118">Child Elements</span></span>  
 <span data-ttu-id="c1e16-119">No.</span><span class="sxs-lookup"><span data-stu-id="c1e16-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c1e16-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c1e16-120">Parent Elements</span></span>  
  
|<span data-ttu-id="c1e16-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="c1e16-121">Element</span></span>|<span data-ttu-id="c1e16-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c1e16-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c1e16-123">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c1e16-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="c1e16-124">Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c1e16-124">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1e16-125">Commenti</span><span class="sxs-lookup"><span data-stu-id="c1e16-125">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c1e16-126">In .NET Framework 4 e versioni successive, questo elemento non ha alcun effetto sui tempi di caricamento degli assembly.</span><span class="sxs-lookup"><span data-stu-id="c1e16-126">In the .NET Framework 4 and later, this element has no effect on assembly load times.</span></span> <span data-ttu-id="c1e16-127">Per ulteriori informazioni, vedere la sezione "semplificazione dei criteri di sicurezza" in [modifiche della sicurezza](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes).</span><span class="sxs-lookup"><span data-stu-id="c1e16-127">For more information, see the "Security Policy Simplification" section in [Security Changes](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes).</span></span>  
  
 <span data-ttu-id="c1e16-128">Il Common Language Runtime (CLR) tenta di verificare la firma Authenticode in fase di caricamento per creare <xref:System.Security.Policy.Publisher> evidenza per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="c1e16-128">The common language runtime (CLR) tries to verify the Authenticode signature at load time to create <xref:System.Security.Policy.Publisher> evidence for the assembly.</span></span> <span data-ttu-id="c1e16-129">Per impostazione predefinita, tuttavia, la maggior parte delle applicazioni non necessita di <xref:System.Security.Policy.Publisher> evidenza.</span><span class="sxs-lookup"><span data-stu-id="c1e16-129">However, by default, most applications do not need <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="c1e16-130">I criteri CAS standard non si basano su <xref:System.Security.Policy.PublisherMembershipCondition> .</span><span class="sxs-lookup"><span data-stu-id="c1e16-130">Standard CAS policy does not rely on the <xref:System.Security.Policy.PublisherMembershipCondition>.</span></span> <span data-ttu-id="c1e16-131">È consigliabile evitare il costo di avvio non necessario associato alla verifica della firma del server di pubblicazione, a meno che l'applicazione non venga eseguita in un computer con criteri CAS personalizzati o si intenda soddisfare le richieste per <xref:System.Security.Permissions.PublisherIdentityPermission> in un ambiente parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="c1e16-131">You should avoid the unnecessary startup cost associated with verifying the publisher signature unless your application executes on a computer with custom CAS policy, or is intending to satisfy demands for <xref:System.Security.Permissions.PublisherIdentityPermission> in a partial-trust environment.</span></span> <span data-ttu-id="c1e16-132">(Le richieste di autorizzazioni di identità hanno sempre esito positivo in un ambiente con attendibilità totale).</span><span class="sxs-lookup"><span data-stu-id="c1e16-132">(Demands for identity permissions always succeed in a full-trust environment.)</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c1e16-133">È consigliabile che i servizi usino l' `<generatePublisherEvidence>` elemento per migliorare le prestazioni di avvio.</span><span class="sxs-lookup"><span data-stu-id="c1e16-133">We recommend that services use the `<generatePublisherEvidence>` element to improve startup performance.</span></span>  <span data-ttu-id="c1e16-134">L'uso di questo elemento consente inoltre di evitare ritardi che possono causare un timeout e l'annullamento dell'avvio del servizio.</span><span class="sxs-lookup"><span data-stu-id="c1e16-134">Using this element can also help avoid delays that can cause a time-out and the cancellation of the service startup.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="c1e16-135">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="c1e16-135">Configuration File</span></span>  
 <span data-ttu-id="c1e16-136">Questo elemento può essere utilizzato solo nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c1e16-136">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1e16-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="c1e16-137">Example</span></span>  
 <span data-ttu-id="c1e16-138">Nell'esempio seguente viene illustrato come utilizzare l' `<generatePublisherEvidence>` elemento per disabilitare il controllo dei criteri di pubblicazione CAS per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c1e16-138">The following example shows how to use the `<generatePublisherEvidence>` element to disable checking for CAS publisher policy for an application.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c1e16-139">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="c1e16-139">See also</span></span>

- [<span data-ttu-id="c1e16-140">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="c1e16-140">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="c1e16-141">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="c1e16-141">Configuration File Schema</span></span>](../index.md)
