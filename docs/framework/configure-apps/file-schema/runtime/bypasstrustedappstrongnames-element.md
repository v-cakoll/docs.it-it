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
ms.openlocfilehash: c70a03e1ad443739f43dc50ab34021652017713d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64607415"
---
# <a name="bypasstrustedappstrongnames-element"></a><span data-ttu-id="b2c9c-102">Elemento \<bypassTrustedAppStrongNames></span><span class="sxs-lookup"><span data-stu-id="b2c9c-102">\<bypassTrustedAppStrongNames> Element</span></span>
<span data-ttu-id="b2c9c-103">Specifica se ignorare la convalida di nomi sicuri per gli assembly con attendibilità che vengono caricati con attendibilità <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="b2c9c-103">Specifies whether to bypass the validation of strong names on full-trust assemblies that are loaded into a full-trust <xref:System.AppDomain>.</span></span>  
  
 <span data-ttu-id="b2c9c-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b2c9c-104">\<configuration></span></span>  
<span data-ttu-id="b2c9c-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="b2c9c-105">\<runtime></span></span>  
<span data-ttu-id="b2c9c-106">\<bypassTrustedAppStrongNames></span><span class="sxs-lookup"><span data-stu-id="b2c9c-106">\<bypassTrustedAppStrongNames></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2c9c-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b2c9c-107">Syntax</span></span>  
  
```xml  
<bypassTrustedAppStrongNames    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b2c9c-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b2c9c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b2c9c-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b2c9c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b2c9c-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="b2c9c-110">Attributes</span></span>  
  
|<span data-ttu-id="b2c9c-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="b2c9c-111">Attribute</span></span>|<span data-ttu-id="b2c9c-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b2c9c-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="b2c9c-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b2c9c-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="b2c9c-114">Specifica se è abilitata la funzionalità che consente di evitare la convalida di nomi sicuri agli assembly completamente attendibili.</span><span class="sxs-lookup"><span data-stu-id="b2c9c-114">Specifies whether the bypass feature that avoids validating strong names for full-trust assemblies is enabled.</span></span> <span data-ttu-id="b2c9c-115">Quando questa funzionalità è abilitata, i nomi sicuri non vengono convalidati la correttezza quando l'assembly viene caricato.</span><span class="sxs-lookup"><span data-stu-id="b2c9c-115">When this feature is enabled, strong names are not validated for correctness when the assembly is loaded.</span></span> <span data-ttu-id="b2c9c-116">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="b2c9c-116">The default is `true`.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="b2c9c-117">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="b2c9c-117">enabled Attribute</span></span>  
  
|<span data-ttu-id="b2c9c-118">Valore</span><span class="sxs-lookup"><span data-stu-id="b2c9c-118">Value</span></span>|<span data-ttu-id="b2c9c-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b2c9c-119">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="b2c9c-120">Le firme con nome sicuro su assembly con attendibilità non vengono convalidate quando gli assembly vengono caricati in un oggetto attendibilità <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="b2c9c-120">Strong-name signatures on full-trust assemblies are not validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="b2c9c-121">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b2c9c-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="b2c9c-122">Le firme con nome sicuro su assembly con attendibilità vengono convalidate quando gli assembly vengono caricati in un oggetto attendibilità <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="b2c9c-122">Strong-name signatures on full-trust assemblies are validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="b2c9c-123">La firma con nome sicuro viene controllata solo la correttezza della firma; non verrà confrontato a un altro nome sicuro per trovare una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="b2c9c-123">The strong-name signature is checked only for signature correctness; it is not compared to another strong name for a match.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b2c9c-124">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b2c9c-124">Child Elements</span></span>  
 <span data-ttu-id="b2c9c-125">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="b2c9c-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b2c9c-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b2c9c-126">Parent Elements</span></span>  
  
|<span data-ttu-id="b2c9c-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="b2c9c-127">Element</span></span>|<span data-ttu-id="b2c9c-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b2c9c-128">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b2c9c-129">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b2c9c-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="b2c9c-130">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="b2c9c-130">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2c9c-131">Note</span><span class="sxs-lookup"><span data-stu-id="b2c9c-131">Remarks</span></span>  
 <span data-ttu-id="b2c9c-132">Questa funzionalità con nome sicuro evita l'overhead della verifica della firma con nome sicuro di assembly completamente attendibili.</span><span class="sxs-lookup"><span data-stu-id="b2c9c-132">The strong-name bypass feature avoids the overhead of strong-name signature verification of full-trust assemblies.</span></span>  
  
 <span data-ttu-id="b2c9c-133">Questa funzionalità si applica a qualsiasi assembly firmato con un nome sicuro e che ha le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="b2c9c-133">The bypass feature applies to any assembly that is signed with a strong name and that has the following characteristics:</span></span>  
  
- <span data-ttu-id="b2c9c-134">Completamente attendibile senza il <xref:System.Security.Policy.StrongName> evidenza (ad esempio, ha `MyComputer` evidenza della zona).</span><span class="sxs-lookup"><span data-stu-id="b2c9c-134">Fully trusted without the <xref:System.Security.Policy.StrongName> evidence (for example, has `MyComputer` zone evidence).</span></span>  
  
- <span data-ttu-id="b2c9c-135">Viene caricato in un dominio <xref:System.AppDomain> completamente attendibile.</span><span class="sxs-lookup"><span data-stu-id="b2c9c-135">Loaded into a fully trusted <xref:System.AppDomain>.</span></span>  
  
- <span data-ttu-id="b2c9c-136">Viene caricato da una località nell'ambito della proprietà <xref:System.AppDomainSetup.ApplicationBase%2A> di <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="b2c9c-136">Loaded from a location under the <xref:System.AppDomainSetup.ApplicationBase%2A> property of that <xref:System.AppDomain>.</span></span>  
  
- <span data-ttu-id="b2c9c-137">Non ha firma ritardata.</span><span class="sxs-lookup"><span data-stu-id="b2c9c-137">Not delay-signed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b2c9c-138">Se questa funzionalità è stata disattivata per tutte le applicazioni nel computer usando una chiave del Registro di sistema, questa impostazione di file di configurazione non ha alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="b2c9c-138">If the bypass feature has been turned off for all applications on the computer by using a registry key, this configuration file setting has no effect.</span></span> <span data-ttu-id="b2c9c-139">Per altre informazioni, vedere [Procedura: Disabilitare la funzionalità che consente di ignorare il nome sicuro](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md).</span><span class="sxs-lookup"><span data-stu-id="b2c9c-139">For more information, see [How to: Disable the Strong-Name Bypass Feature](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2c9c-140">Esempio</span><span class="sxs-lookup"><span data-stu-id="b2c9c-140">Example</span></span>  
 <span data-ttu-id="b2c9c-141">Nell'esempio seguente viene illustrato come specificare il comportamento che convalida la firma con nome sicuro su assembly completamente attendibili.</span><span class="sxs-lookup"><span data-stu-id="b2c9c-141">The following example shows how to specify the behavior that validates the strong-name signature on full-trust assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <bypassTrustedAppStrongNames enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b2c9c-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2c9c-142">See also</span></span>

- [<span data-ttu-id="b2c9c-143">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="b2c9c-143">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="b2c9c-144">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="b2c9c-144">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="b2c9c-145">Procedura: Disabilitare la funzionalità che consente di ignorare il nome sicuro</span><span class="sxs-lookup"><span data-stu-id="b2c9c-145">How to: Disable the Strong-Name Bypass Feature</span></span>](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md)
