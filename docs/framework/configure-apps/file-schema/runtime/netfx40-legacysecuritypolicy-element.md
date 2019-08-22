---
title: Elemento < NetFx40_LegacySecurityPolicy >
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_LegacySecurityPolicy> element
- NetFx40_LegacySecurityPolicy element
ms.assetid: 07132b9c-4a72-4710-99d7-e702405e02d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 881862b6b81ace1c1923b2a22d2fbe54d939d84e
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663566"
---
# <a name="netfx40_legacysecuritypolicy-element"></a><span data-ttu-id="2496c-102">\<Elemento > NetFx40_LegacySecurityPolicy</span><span class="sxs-lookup"><span data-stu-id="2496c-102">\<NetFx40_LegacySecurityPolicy> Element</span></span>

<span data-ttu-id="2496c-103">Specifica se il runtime usa i criteri di sicurezza per l'accesso di codice legacy.</span><span class="sxs-lookup"><span data-stu-id="2496c-103">Specifies whether the runtime uses legacy code access security (CAS) policy.</span></span>

<span data-ttu-id="2496c-104">\<> di configurazione </span><span class="sxs-lookup"><span data-stu-id="2496c-104">\<configuration></span></span>\
<span data-ttu-id="2496c-105">\<> runtime </span><span class="sxs-lookup"><span data-stu-id="2496c-105">\<runtime></span></span>\
<span data-ttu-id="2496c-106">\<NetFx40_LegacySecurityPolicy></span><span class="sxs-lookup"><span data-stu-id="2496c-106">\<NetFx40_LegacySecurityPolicy></span></span>

## <a name="syntax"></a><span data-ttu-id="2496c-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2496c-107">Syntax</span></span>

```xml
<NetFx40_LegacySecurityPolicy
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2496c-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2496c-108">Attributes and Elements</span></span>

<span data-ttu-id="2496c-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2496c-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="2496c-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="2496c-110">Attributes</span></span>

|<span data-ttu-id="2496c-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="2496c-111">Attribute</span></span>|<span data-ttu-id="2496c-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2496c-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="2496c-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="2496c-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="2496c-114">Specifica se il runtime usa i criteri CAS legacy.</span><span class="sxs-lookup"><span data-stu-id="2496c-114">Specifies whether the runtime uses legacy CAS policy.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="2496c-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="2496c-115">enabled Attribute</span></span>

|<span data-ttu-id="2496c-116">Valore</span><span class="sxs-lookup"><span data-stu-id="2496c-116">Value</span></span>|<span data-ttu-id="2496c-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2496c-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="2496c-118">Il runtime non usa i criteri CAS legacy.</span><span class="sxs-lookup"><span data-stu-id="2496c-118">The runtime does not use legacy CAS policy.</span></span> <span data-ttu-id="2496c-119">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="2496c-119">This is the default.</span></span>|
|`true`|<span data-ttu-id="2496c-120">Il runtime usa i criteri CAS legacy.</span><span class="sxs-lookup"><span data-stu-id="2496c-120">The runtime uses legacy CAS policy.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="2496c-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2496c-121">Child Elements</span></span>

<span data-ttu-id="2496c-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="2496c-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2496c-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2496c-123">Parent Elements</span></span>

|<span data-ttu-id="2496c-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="2496c-124">Element</span></span>|<span data-ttu-id="2496c-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2496c-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="2496c-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2496c-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="2496c-127">Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2496c-127">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="2496c-128">Note</span><span class="sxs-lookup"><span data-stu-id="2496c-128">Remarks</span></span>

<span data-ttu-id="2496c-129">In .NET Framework versione 3,5 e versioni precedenti, i criteri CAS sono sempre attivi.</span><span class="sxs-lookup"><span data-stu-id="2496c-129">In the .NET Framework version 3.5 and earlier versions, CAS policy is always in effect.</span></span> <span data-ttu-id="2496c-130">Nella .NET Framework 4 è necessario abilitare i criteri CAS.</span><span class="sxs-lookup"><span data-stu-id="2496c-130">In the .NET Framework 4, CAS policy must be enabled.</span></span>

<span data-ttu-id="2496c-131">I criteri CAS sono specifici della versione.</span><span class="sxs-lookup"><span data-stu-id="2496c-131">CAS policy is version-specific.</span></span> <span data-ttu-id="2496c-132">I criteri CAS personalizzati presenti nelle versioni precedenti del .NET Framework devono essere specificati nuovamente nell'.NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="2496c-132">Custom CAS policies that exist in earlier versions of the .NET Framework must be respecified in the .NET Framework 4.</span></span>

<span data-ttu-id="2496c-133">L'applicazione `<NetFx40_LegacySecurityPolicy>` dell'elemento a un assembly .NET Framework 4 non influisce sul [codice SecurityTransparent](../../../misc/security-transparent-code.md); le regole di trasparenza sono comunque valide.</span><span class="sxs-lookup"><span data-stu-id="2496c-133">Applying the `<NetFx40_LegacySecurityPolicy>` element to a .NET Framework 4 assembly does not affect [security-transparent code](../../../misc/security-transparent-code.md); the transparency rules still apply.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2496c-134">L'applicazione `<NetFx40_LegacySecurityPolicy>` dell'elemento può comportare un calo significativo delle prestazioni per gli assembly di immagini native creati dal [Generatore di immagini native (Ngen. exe)](../../../tools/ngen-exe-native-image-generator.md) che non sono installati nel [global assembly cache](../../../app-domains/gac.md).</span><span class="sxs-lookup"><span data-stu-id="2496c-134">Applying the `<NetFx40_LegacySecurityPolicy>` element can result in significant performance penalties for native image assemblies created by the [Native Image Generator (Ngen.exe)](../../../tools/ngen-exe-native-image-generator.md) that are not installed in the [global assembly cache](../../../app-domains/gac.md).</span></span> <span data-ttu-id="2496c-135">Il calo delle prestazioni è dovuto al fatto che il runtime non è in grado di caricare gli assembly come immagini native quando viene applicato l'attributo, ottenendo così il caricamento come assembly JIT.</span><span class="sxs-lookup"><span data-stu-id="2496c-135">The performance degradation is caused by the inability of the runtime to load the assemblies as native images when the attribute is applied, resulting in their being loaded as just-in-time assemblies.</span></span>

> [!NOTE]
> <span data-ttu-id="2496c-136">Se si specifica una versione di .NET Framework di destinazione precedente alla .NET Framework 4 nelle impostazioni del progetto per il progetto di Visual Studio, verranno abilitati i criteri CAS, inclusi i criteri CAS personalizzati specificati per tale versione.</span><span class="sxs-lookup"><span data-stu-id="2496c-136">If you specify a target .NET Framework version that is earlier than the .NET Framework 4 in the project settings for your Visual Studio project, CAS policy will be enabled, including any custom CAS policies you specified for that version.</span></span> <span data-ttu-id="2496c-137">Tuttavia, non sarà possibile usare nuovi tipi e membri di .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="2496c-137">However, you will not be able to use new .NET Framework 4 types and members.</span></span> <span data-ttu-id="2496c-138">È anche possibile specificare una versione precedente del .NET Framework usando l' [ \<elemento > supportedRuntime](../startup/supportedruntime-element.md) nello schema delle impostazioni di avvio nel file di [configurazione dell'applicazione](../../index.md).</span><span class="sxs-lookup"><span data-stu-id="2496c-138">You can also specify an earlier version of the .NET Framework by using the [\<supportedRuntime> element](../startup/supportedruntime-element.md) in the startup settings schema in your [application configuration file](../../index.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2496c-139">La sintassi del file di configurazione distingue tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="2496c-139">Configuration file syntax is case-sensitive.</span></span> <span data-ttu-id="2496c-140">È necessario utilizzare la sintassi come indicato nelle sezioni Sintassi ed esempio.</span><span class="sxs-lookup"><span data-stu-id="2496c-140">You should use the syntax as provided in the Syntax and Example sections.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="2496c-141">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="2496c-141">Configuration File</span></span>

<span data-ttu-id="2496c-142">Questo elemento può essere utilizzato solo nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2496c-142">This element can be used only in the application configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="2496c-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="2496c-143">Example</span></span>

<span data-ttu-id="2496c-144">Nell'esempio seguente viene illustrato come abilitare i criteri CAS legacy per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2496c-144">The following example shows how to enable legacy CAS policy for an application.</span></span>

```xml
<configuration>
   <runtime>
      <NetFx40_LegacySecurityPolicy enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="2496c-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2496c-145">See also</span></span>

- [<span data-ttu-id="2496c-146">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="2496c-146">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="2496c-147">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="2496c-147">Configuration File Schema</span></span>](../index.md)
