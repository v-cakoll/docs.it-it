---
title: <bypassTrustedAppStrongNames> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- strong-name bypass feature
- bypassTrustedAppStrongNames element
- strong-named assemblies, loading into trusted application domains
- <bypassTrustedAppStrongNames> element
ms.assetid: 71b2ebf6-3843-41e2-ad52-ffa5cd083a40
ms.openlocfilehash: 96361a6742d1d2f76cb237344189d3277d7c8069
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73739090"
---
# <a name="bypasstrustedappstrongnames-element"></a><span data-ttu-id="8433e-102">\<bypassTrustedAppStrongNames> Elemento</span><span class="sxs-lookup"><span data-stu-id="8433e-102">\<bypassTrustedAppStrongNames> Element</span></span>

<span data-ttu-id="8433e-103">Specifica se ignorare la convalida di nomi sicuri in assembly con attendibilità totale caricati in un attendibilità totale <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="8433e-103">Specifies whether to bypass the validation of strong names on full-trust assemblies that are loaded into a full-trust <xref:System.AppDomain>.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<bypassTrustedAppStrongNames>**

## <a name="syntax"></a><span data-ttu-id="8433e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8433e-104">Syntax</span></span>

```xml
<bypassTrustedAppStrongNames
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8433e-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8433e-105">Attributes and Elements</span></span>

<span data-ttu-id="8433e-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8433e-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="8433e-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="8433e-107">Attributes</span></span>

|<span data-ttu-id="8433e-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="8433e-108">Attribute</span></span>|<span data-ttu-id="8433e-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8433e-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="8433e-110">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="8433e-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="8433e-111">Specifica se è abilitata la funzionalità bypass che consente di evitare la convalida di nomi sicuri per gli assembly con attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="8433e-111">Specifies whether the bypass feature that avoids validating strong names for full-trust assemblies is enabled.</span></span> <span data-ttu-id="8433e-112">Quando questa funzionalità è abilitata, i nomi sicuri non vengono convalidati per correttezza quando viene caricato l'assembly.</span><span class="sxs-lookup"><span data-stu-id="8433e-112">When this feature is enabled, strong names are not validated for correctness when the assembly is loaded.</span></span> <span data-ttu-id="8433e-113">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="8433e-113">The default is `true`.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="8433e-114">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="8433e-114">enabled Attribute</span></span>

|<span data-ttu-id="8433e-115">Valore</span><span class="sxs-lookup"><span data-stu-id="8433e-115">Value</span></span>|<span data-ttu-id="8433e-116">Description</span><span class="sxs-lookup"><span data-stu-id="8433e-116">Description</span></span>|
|-----------|-----------------|
|`true`|<span data-ttu-id="8433e-117">Le firme con nome sicuro in assembly con attendibilità totale non vengono convalidate quando gli assembly vengono caricati in un attendibilità totale <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="8433e-117">Strong-name signatures on full-trust assemblies are not validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="8433e-118">Questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="8433e-118">This is the default.</span></span>|
|`false`|<span data-ttu-id="8433e-119">Le firme con nome sicuro per gli assembly con attendibilità totale vengono convalidate quando gli assembly vengono caricati in un attendibilità totale <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="8433e-119">Strong-name signatures on full-trust assemblies are validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="8433e-120">La firma con nome sicuro viene verificata solo per la correttezza della firma; non viene confrontato con un altro nome sicuro per una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="8433e-120">The strong-name signature is checked only for signature correctness; it is not compared to another strong name for a match.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="8433e-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8433e-121">Child Elements</span></span>

<span data-ttu-id="8433e-122">No.</span><span class="sxs-lookup"><span data-stu-id="8433e-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="8433e-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8433e-123">Parent Elements</span></span>

|<span data-ttu-id="8433e-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="8433e-124">Element</span></span>|<span data-ttu-id="8433e-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8433e-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="8433e-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8433e-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="8433e-127">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="8433e-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="8433e-128">Commenti</span><span class="sxs-lookup"><span data-stu-id="8433e-128">Remarks</span></span>

<span data-ttu-id="8433e-129">La funzionalità di bypass con nome sicuro evita l'overhead della verifica della firma con nome sicuro degli assembly con attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="8433e-129">The strong-name bypass feature avoids the overhead of strong-name signature verification of full-trust assemblies.</span></span>

<span data-ttu-id="8433e-130">Questa funzionalità si applica a qualsiasi assembly firmato con un nome sicuro e che ha le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="8433e-130">The bypass feature applies to any assembly that is signed with a strong name and that has the following characteristics:</span></span>

- <span data-ttu-id="8433e-131">Completamente attendibile senza l' <xref:System.Security.Policy.StrongName> evidenza, ad esempio con l' `MyComputer` evidenza della zona.</span><span class="sxs-lookup"><span data-stu-id="8433e-131">Fully trusted without the <xref:System.Security.Policy.StrongName> evidence (for example, has `MyComputer` zone evidence).</span></span>

- <span data-ttu-id="8433e-132">Viene caricato in un dominio <xref:System.AppDomain> completamente attendibile.</span><span class="sxs-lookup"><span data-stu-id="8433e-132">Loaded into a fully trusted <xref:System.AppDomain>.</span></span>

- <span data-ttu-id="8433e-133">Viene caricato da una località nell'ambito della proprietà <xref:System.AppDomainSetup.ApplicationBase%2A> di <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="8433e-133">Loaded from a location under the <xref:System.AppDomainSetup.ApplicationBase%2A> property of that <xref:System.AppDomain>.</span></span>

- <span data-ttu-id="8433e-134">Non ha firma ritardata.</span><span class="sxs-lookup"><span data-stu-id="8433e-134">Not delay-signed.</span></span>

> [!NOTE]
> <span data-ttu-id="8433e-135">Se la funzionalità bypass è stata disattivata per tutte le applicazioni del computer utilizzando una chiave del registro di sistema, questa impostazione del file di configurazione non ha alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="8433e-135">If the bypass feature has been turned off for all applications on the computer by using a registry key, this configuration file setting has no effect.</span></span> <span data-ttu-id="8433e-136">Per altre informazioni, vedere [procedura: disabilitare la funzionalità di bypass con nome sicuro](../../../../standard/assembly/disable-strong-name-bypass-feature.md).</span><span class="sxs-lookup"><span data-stu-id="8433e-136">For more information, see [How to: Disable the Strong-Name Bypass Feature](../../../../standard/assembly/disable-strong-name-bypass-feature.md).</span></span>

## <a name="example"></a><span data-ttu-id="8433e-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="8433e-137">Example</span></span>

<span data-ttu-id="8433e-138">Nell'esempio seguente viene illustrato come specificare il comportamento che convalida la firma con nome sicuro in assembly con attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="8433e-138">The following example shows how to specify the behavior that validates the strong-name signature on full-trust assemblies.</span></span>

```xml
<configuration>
   <runtime>
      <bypassTrustedAppStrongNames enabled="false"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="8433e-139">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="8433e-139">See also</span></span>

- [<span data-ttu-id="8433e-140">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="8433e-140">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="8433e-141">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="8433e-141">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="8433e-142">Procedura: disabilitare la funzionalità di bypass con nome sicuro</span><span class="sxs-lookup"><span data-stu-id="8433e-142">How to: Disable the strong-name bypass feature</span></span>](../../../../standard/assembly/disable-strong-name-bypass-feature.md)
