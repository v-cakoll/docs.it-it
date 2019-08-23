---
title: <bypassTrustedAppStrongNames> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- strong-name bypass feature
- bypassTrustedAppStrongNames element
- strong-named assemblies, loading into trusted application domains
- <bypassTrustedAppStrongNames> element
ms.assetid: 71b2ebf6-3843-41e2-ad52-ffa5cd083a40
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 92873277b4b25e4c1c5981628187078ac7cb5704
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920893"
---
# <a name="bypasstrustedappstrongnames-element"></a><span data-ttu-id="7cfe3-102">Elemento \<bypassTrustedAppStrongNames></span><span class="sxs-lookup"><span data-stu-id="7cfe3-102">\<bypassTrustedAppStrongNames> Element</span></span>
<span data-ttu-id="7cfe3-103">Specifica se ignorare la convalida di nomi sicuri in assembly con attendibilità totale caricati in un attendibilità <xref:System.AppDomain>totale.</span><span class="sxs-lookup"><span data-stu-id="7cfe3-103">Specifies whether to bypass the validation of strong names on full-trust assemblies that are loaded into a full-trust <xref:System.AppDomain>.</span></span>  
  
 <span data-ttu-id="7cfe3-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7cfe3-104">\<configuration></span></span>  
<span data-ttu-id="7cfe3-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="7cfe3-105">\<runtime></span></span>  
<span data-ttu-id="7cfe3-106">\<bypassTrustedAppStrongNames></span><span class="sxs-lookup"><span data-stu-id="7cfe3-106">\<bypassTrustedAppStrongNames></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cfe3-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7cfe3-107">Syntax</span></span>  
  
```xml  
<bypassTrustedAppStrongNames    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7cfe3-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7cfe3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="7cfe3-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7cfe3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7cfe3-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="7cfe3-110">Attributes</span></span>  
  
|<span data-ttu-id="7cfe3-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="7cfe3-111">Attribute</span></span>|<span data-ttu-id="7cfe3-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7cfe3-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="7cfe3-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="7cfe3-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="7cfe3-114">Specifica se è abilitata la funzionalità bypass che consente di evitare la convalida di nomi sicuri per gli assembly con attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="7cfe3-114">Specifies whether the bypass feature that avoids validating strong names for full-trust assemblies is enabled.</span></span> <span data-ttu-id="7cfe3-115">Quando questa funzionalità è abilitata, i nomi sicuri non vengono convalidati per correttezza quando viene caricato l'assembly.</span><span class="sxs-lookup"><span data-stu-id="7cfe3-115">When this feature is enabled, strong names are not validated for correctness when the assembly is loaded.</span></span> <span data-ttu-id="7cfe3-116">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="7cfe3-116">The default is `true`.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="7cfe3-117">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="7cfe3-117">enabled Attribute</span></span>  
  
|<span data-ttu-id="7cfe3-118">Valore</span><span class="sxs-lookup"><span data-stu-id="7cfe3-118">Value</span></span>|<span data-ttu-id="7cfe3-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7cfe3-119">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="7cfe3-120">Le firme con nome sicuro in assembly con attendibilità totale non vengono convalidate quando gli assembly vengono caricati in un <xref:System.AppDomain>attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="7cfe3-120">Strong-name signatures on full-trust assemblies are not validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="7cfe3-121">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="7cfe3-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="7cfe3-122">Le firme con nome sicuro per gli assembly con attendibilità totale vengono convalidate quando gli assembly vengono caricati in <xref:System.AppDomain>un attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="7cfe3-122">Strong-name signatures on full-trust assemblies are validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="7cfe3-123">La firma con nome sicuro viene verificata solo per la correttezza della firma; non viene confrontato con un altro nome sicuro per una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="7cfe3-123">The strong-name signature is checked only for signature correctness; it is not compared to another strong name for a match.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7cfe3-124">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7cfe3-124">Child Elements</span></span>  
 <span data-ttu-id="7cfe3-125">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="7cfe3-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7cfe3-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7cfe3-126">Parent Elements</span></span>  
  
|<span data-ttu-id="7cfe3-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="7cfe3-127">Element</span></span>|<span data-ttu-id="7cfe3-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7cfe3-128">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7cfe3-129">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7cfe3-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="7cfe3-130">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="7cfe3-130">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7cfe3-131">Note</span><span class="sxs-lookup"><span data-stu-id="7cfe3-131">Remarks</span></span>  
 <span data-ttu-id="7cfe3-132">La funzionalità di bypass con nome sicuro evita l'overhead della verifica della firma con nome sicuro degli assembly con attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="7cfe3-132">The strong-name bypass feature avoids the overhead of strong-name signature verification of full-trust assemblies.</span></span>  
  
 <span data-ttu-id="7cfe3-133">Questa funzionalità si applica a qualsiasi assembly firmato con un nome sicuro e che ha le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="7cfe3-133">The bypass feature applies to any assembly that is signed with a strong name and that has the following characteristics:</span></span>  
  
- <span data-ttu-id="7cfe3-134">Completamente attendibile senza <xref:System.Security.Policy.StrongName> l'evidenza, ad esempio con `MyComputer` l'evidenza della zona.</span><span class="sxs-lookup"><span data-stu-id="7cfe3-134">Fully trusted without the <xref:System.Security.Policy.StrongName> evidence (for example, has `MyComputer` zone evidence).</span></span>  
  
- <span data-ttu-id="7cfe3-135">Viene caricato in un dominio <xref:System.AppDomain> completamente attendibile.</span><span class="sxs-lookup"><span data-stu-id="7cfe3-135">Loaded into a fully trusted <xref:System.AppDomain>.</span></span>  
  
- <span data-ttu-id="7cfe3-136">Viene caricato da una località nell'ambito della proprietà <xref:System.AppDomainSetup.ApplicationBase%2A> di <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="7cfe3-136">Loaded from a location under the <xref:System.AppDomainSetup.ApplicationBase%2A> property of that <xref:System.AppDomain>.</span></span>  
  
- <span data-ttu-id="7cfe3-137">Non ha firma ritardata.</span><span class="sxs-lookup"><span data-stu-id="7cfe3-137">Not delay-signed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7cfe3-138">Se la funzionalità bypass è stata disattivata per tutte le applicazioni del computer utilizzando una chiave del registro di sistema, questa impostazione del file di configurazione non ha alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="7cfe3-138">If the bypass feature has been turned off for all applications on the computer by using a registry key, this configuration file setting has no effect.</span></span> <span data-ttu-id="7cfe3-139">Per altre informazioni, vedere [Procedura: Disabilitare la funzionalità che consente di ignorare il nome sicuro](../../../app-domains/how-to-disable-the-strong-name-bypass-feature.md).</span><span class="sxs-lookup"><span data-stu-id="7cfe3-139">For more information, see [How to: Disable the Strong-Name Bypass Feature](../../../app-domains/how-to-disable-the-strong-name-bypass-feature.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7cfe3-140">Esempio</span><span class="sxs-lookup"><span data-stu-id="7cfe3-140">Example</span></span>  
 <span data-ttu-id="7cfe3-141">Nell'esempio seguente viene illustrato come specificare il comportamento che convalida la firma con nome sicuro in assembly con attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="7cfe3-141">The following example shows how to specify the behavior that validates the strong-name signature on full-trust assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <bypassTrustedAppStrongNames enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7cfe3-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7cfe3-142">See also</span></span>

- [<span data-ttu-id="7cfe3-143">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="7cfe3-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="7cfe3-144">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="7cfe3-144">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="7cfe3-145">Procedura: Disabilitare la funzionalità che consente di ignorare il nome sicuro</span><span class="sxs-lookup"><span data-stu-id="7cfe3-145">How to: Disable the Strong-Name Bypass Feature</span></span>](../../../app-domains/how-to-disable-the-strong-name-bypass-feature.md)
