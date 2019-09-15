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
ms.openlocfilehash: 35b4c6201b5181b8d7241906f60a731e4175d523
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991231"
---
# <a name="bypasstrustedappstrongnames-element"></a><span data-ttu-id="6b67b-102">Elemento \<bypassTrustedAppStrongNames></span><span class="sxs-lookup"><span data-stu-id="6b67b-102">\<bypassTrustedAppStrongNames> Element</span></span>

<span data-ttu-id="6b67b-103">Specifica se ignorare la convalida di nomi sicuri in assembly con attendibilità totale caricati in un attendibilità <xref:System.AppDomain>totale.</span><span class="sxs-lookup"><span data-stu-id="6b67b-103">Specifies whether to bypass the validation of strong names on full-trust assemblies that are loaded into a full-trust <xref:System.AppDomain>.</span></span>

<span data-ttu-id="6b67b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6b67b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6b67b-105">&nbsp;&nbsp;[ **\<> di runtime**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="6b67b-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="6b67b-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<bypassTrustedAppStrongNames>**</span><span class="sxs-lookup"><span data-stu-id="6b67b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<bypassTrustedAppStrongNames>**</span></span>

## <a name="syntax"></a><span data-ttu-id="6b67b-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6b67b-107">Syntax</span></span>

```xml
<bypassTrustedAppStrongNames
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6b67b-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6b67b-108">Attributes and Elements</span></span>

<span data-ttu-id="6b67b-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6b67b-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="6b67b-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="6b67b-110">Attributes</span></span>

|<span data-ttu-id="6b67b-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="6b67b-111">Attribute</span></span>|<span data-ttu-id="6b67b-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6b67b-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="6b67b-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="6b67b-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="6b67b-114">Specifica se è abilitata la funzionalità bypass che consente di evitare la convalida di nomi sicuri per gli assembly con attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="6b67b-114">Specifies whether the bypass feature that avoids validating strong names for full-trust assemblies is enabled.</span></span> <span data-ttu-id="6b67b-115">Quando questa funzionalità è abilitata, i nomi sicuri non vengono convalidati per correttezza quando viene caricato l'assembly.</span><span class="sxs-lookup"><span data-stu-id="6b67b-115">When this feature is enabled, strong names are not validated for correctness when the assembly is loaded.</span></span> <span data-ttu-id="6b67b-116">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="6b67b-116">The default is `true`.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="6b67b-117">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="6b67b-117">enabled Attribute</span></span>

|<span data-ttu-id="6b67b-118">Valore</span><span class="sxs-lookup"><span data-stu-id="6b67b-118">Value</span></span>|<span data-ttu-id="6b67b-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6b67b-119">Description</span></span>|
|-----------|-----------------|
|`true`|<span data-ttu-id="6b67b-120">Le firme con nome sicuro in assembly con attendibilità totale non vengono convalidate quando gli assembly vengono caricati in un <xref:System.AppDomain>attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="6b67b-120">Strong-name signatures on full-trust assemblies are not validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="6b67b-121">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6b67b-121">This is the default.</span></span>|
|`false`|<span data-ttu-id="6b67b-122">Le firme con nome sicuro per gli assembly con attendibilità totale vengono convalidate quando gli assembly vengono caricati in <xref:System.AppDomain>un attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="6b67b-122">Strong-name signatures on full-trust assemblies are validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="6b67b-123">La firma con nome sicuro viene verificata solo per la correttezza della firma; non viene confrontato con un altro nome sicuro per una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="6b67b-123">The strong-name signature is checked only for signature correctness; it is not compared to another strong name for a match.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="6b67b-124">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6b67b-124">Child Elements</span></span>

<span data-ttu-id="6b67b-125">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="6b67b-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="6b67b-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6b67b-126">Parent Elements</span></span>

|<span data-ttu-id="6b67b-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="6b67b-127">Element</span></span>|<span data-ttu-id="6b67b-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6b67b-128">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="6b67b-129">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6b67b-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="6b67b-130">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="6b67b-130">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="6b67b-131">Note</span><span class="sxs-lookup"><span data-stu-id="6b67b-131">Remarks</span></span>

<span data-ttu-id="6b67b-132">La funzionalità di bypass con nome sicuro evita l'overhead della verifica della firma con nome sicuro degli assembly con attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="6b67b-132">The strong-name bypass feature avoids the overhead of strong-name signature verification of full-trust assemblies.</span></span>

<span data-ttu-id="6b67b-133">Questa funzionalità si applica a qualsiasi assembly firmato con un nome sicuro e che ha le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="6b67b-133">The bypass feature applies to any assembly that is signed with a strong name and that has the following characteristics:</span></span>

- <span data-ttu-id="6b67b-134">Completamente attendibile senza <xref:System.Security.Policy.StrongName> l'evidenza, ad esempio con `MyComputer` l'evidenza della zona.</span><span class="sxs-lookup"><span data-stu-id="6b67b-134">Fully trusted without the <xref:System.Security.Policy.StrongName> evidence (for example, has `MyComputer` zone evidence).</span></span>

- <span data-ttu-id="6b67b-135">Viene caricato in un dominio <xref:System.AppDomain> completamente attendibile.</span><span class="sxs-lookup"><span data-stu-id="6b67b-135">Loaded into a fully trusted <xref:System.AppDomain>.</span></span>

- <span data-ttu-id="6b67b-136">Viene caricato da una località nell'ambito della proprietà <xref:System.AppDomainSetup.ApplicationBase%2A> di <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="6b67b-136">Loaded from a location under the <xref:System.AppDomainSetup.ApplicationBase%2A> property of that <xref:System.AppDomain>.</span></span>

- <span data-ttu-id="6b67b-137">Non ha firma ritardata.</span><span class="sxs-lookup"><span data-stu-id="6b67b-137">Not delay-signed.</span></span>

> [!NOTE]
> <span data-ttu-id="6b67b-138">Se la funzionalità bypass è stata disattivata per tutte le applicazioni del computer utilizzando una chiave del registro di sistema, questa impostazione del file di configurazione non ha alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="6b67b-138">If the bypass feature has been turned off for all applications on the computer by using a registry key, this configuration file setting has no effect.</span></span> <span data-ttu-id="6b67b-139">Per altre informazioni, vedere [Procedura: Disabilitare la funzionalità che consente di ignorare il nome sicuro](../../../app-domains/how-to-disable-the-strong-name-bypass-feature.md).</span><span class="sxs-lookup"><span data-stu-id="6b67b-139">For more information, see [How to: Disable the Strong-Name Bypass Feature](../../../app-domains/how-to-disable-the-strong-name-bypass-feature.md).</span></span>

## <a name="example"></a><span data-ttu-id="6b67b-140">Esempio</span><span class="sxs-lookup"><span data-stu-id="6b67b-140">Example</span></span>

<span data-ttu-id="6b67b-141">Nell'esempio seguente viene illustrato come specificare il comportamento che convalida la firma con nome sicuro in assembly con attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="6b67b-141">The following example shows how to specify the behavior that validates the strong-name signature on full-trust assemblies.</span></span>

```xml
<configuration>
   <runtime>
      <bypassTrustedAppStrongNames enabled="false"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="6b67b-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b67b-142">See also</span></span>

- [<span data-ttu-id="6b67b-143">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="6b67b-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="6b67b-144">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="6b67b-144">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="6b67b-145">Procedura: Disabilitare la funzionalità di bypass con nome sicuro</span><span class="sxs-lookup"><span data-stu-id="6b67b-145">How to: Disable the strong-name bypass feature</span></span>](../../../../standard/assembly/disable-strong-name-bypass-feature.md)
