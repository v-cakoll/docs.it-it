---
title: Elemento < NetFx40_LegacySecurityPolicy >
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_LegacySecurityPolicy> element
- NetFx40_LegacySecurityPolicy element
ms.assetid: 07132b9c-4a72-4710-99d7-e702405e02d4
ms.openlocfilehash: d5192eb56bb8b640544bdc52a0bb9d8a5277efef
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73116244"
---
# <a name="netfx40_legacysecuritypolicy-element"></a><span data-ttu-id="d11ed-102">\<NetFx40_LegacySecurityPolicy> Elemento</span><span class="sxs-lookup"><span data-stu-id="d11ed-102">\<NetFx40_LegacySecurityPolicy> Element</span></span>

<span data-ttu-id="d11ed-103">Specifica se il runtime usa i criteri di sicurezza per l'accesso di codice legacy.</span><span class="sxs-lookup"><span data-stu-id="d11ed-103">Specifies whether the runtime uses legacy code access security (CAS) policy.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<NetFx40_LegacySecurityPolicy>**  

## <a name="syntax"></a><span data-ttu-id="d11ed-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d11ed-104">Syntax</span></span>

```xml
<NetFx40_LegacySecurityPolicy
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d11ed-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d11ed-105">Attributes and Elements</span></span>

<span data-ttu-id="d11ed-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d11ed-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="d11ed-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="d11ed-107">Attributes</span></span>

|<span data-ttu-id="d11ed-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="d11ed-108">Attribute</span></span>|<span data-ttu-id="d11ed-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d11ed-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="d11ed-110">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d11ed-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="d11ed-111">Specifica se il runtime usa i criteri CAS legacy.</span><span class="sxs-lookup"><span data-stu-id="d11ed-111">Specifies whether the runtime uses legacy CAS policy.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="d11ed-112">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="d11ed-112">enabled Attribute</span></span>

|<span data-ttu-id="d11ed-113">Valore</span><span class="sxs-lookup"><span data-stu-id="d11ed-113">Value</span></span>|<span data-ttu-id="d11ed-114">Description</span><span class="sxs-lookup"><span data-stu-id="d11ed-114">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="d11ed-115">Il runtime non usa i criteri CAS legacy.</span><span class="sxs-lookup"><span data-stu-id="d11ed-115">The runtime does not use legacy CAS policy.</span></span> <span data-ttu-id="d11ed-116">Questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="d11ed-116">This is the default.</span></span>|
|`true`|<span data-ttu-id="d11ed-117">Il runtime usa i criteri CAS legacy.</span><span class="sxs-lookup"><span data-stu-id="d11ed-117">The runtime uses legacy CAS policy.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="d11ed-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d11ed-118">Child Elements</span></span>

<span data-ttu-id="d11ed-119">No.</span><span class="sxs-lookup"><span data-stu-id="d11ed-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d11ed-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d11ed-120">Parent Elements</span></span>

|<span data-ttu-id="d11ed-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="d11ed-121">Element</span></span>|<span data-ttu-id="d11ed-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d11ed-122">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="d11ed-123">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d11ed-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="d11ed-124">Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d11ed-124">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d11ed-125">Commenti</span><span class="sxs-lookup"><span data-stu-id="d11ed-125">Remarks</span></span>

<span data-ttu-id="d11ed-126">In .NET Framework versione 3,5 e versioni precedenti, i criteri CAS sono sempre attivi.</span><span class="sxs-lookup"><span data-stu-id="d11ed-126">In the .NET Framework version 3.5 and earlier versions, CAS policy is always in effect.</span></span> <span data-ttu-id="d11ed-127">Nella .NET Framework 4 è necessario abilitare i criteri CAS.</span><span class="sxs-lookup"><span data-stu-id="d11ed-127">In the .NET Framework 4, CAS policy must be enabled.</span></span>

<span data-ttu-id="d11ed-128">I criteri CAS sono specifici della versione.</span><span class="sxs-lookup"><span data-stu-id="d11ed-128">CAS policy is version-specific.</span></span> <span data-ttu-id="d11ed-129">I criteri CAS personalizzati presenti nelle versioni precedenti del .NET Framework devono essere specificati nuovamente nell'.NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d11ed-129">Custom CAS policies that exist in earlier versions of the .NET Framework must be respecified in the .NET Framework 4.</span></span>

<span data-ttu-id="d11ed-130">L'applicazione dell' `<NetFx40_LegacySecurityPolicy>` elemento a un assembly .NET Framework 4 non influisce sul [codice SecurityTransparent](../../../misc/security-transparent-code.md); le regole di trasparenza sono comunque valide.</span><span class="sxs-lookup"><span data-stu-id="d11ed-130">Applying the `<NetFx40_LegacySecurityPolicy>` element to a .NET Framework 4 assembly does not affect [security-transparent code](../../../misc/security-transparent-code.md); the transparency rules still apply.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d11ed-131">L'applicazione dell'elemento può comportare un calo `<NetFx40_LegacySecurityPolicy>` significativo delle prestazioni per gli assembly di immagini native creati dal [Generatore di immagini native (Ngen. exe)](../../../tools/ngen-exe-native-image-generator.md) che non sono installati nel [global assembly cache](../../../app-domains/gac.md).</span><span class="sxs-lookup"><span data-stu-id="d11ed-131">Applying the `<NetFx40_LegacySecurityPolicy>` element can result in significant performance penalties for native image assemblies created by the [Native Image Generator (Ngen.exe)](../../../tools/ngen-exe-native-image-generator.md) that are not installed in the [global assembly cache](../../../app-domains/gac.md).</span></span> <span data-ttu-id="d11ed-132">Il calo delle prestazioni è dovuto al fatto che il runtime non è in grado di caricare gli assembly come immagini native quando viene applicato l'attributo, ottenendo così il caricamento come assembly JIT.</span><span class="sxs-lookup"><span data-stu-id="d11ed-132">The performance degradation is caused by the inability of the runtime to load the assemblies as native images when the attribute is applied, resulting in their being loaded as just-in-time assemblies.</span></span>

> [!NOTE]
> <span data-ttu-id="d11ed-133">Se si specifica una versione di .NET Framework di destinazione precedente alla .NET Framework 4 nelle impostazioni del progetto per il progetto di Visual Studio, verranno abilitati i criteri CAS, inclusi i criteri CAS personalizzati specificati per tale versione.</span><span class="sxs-lookup"><span data-stu-id="d11ed-133">If you specify a target .NET Framework version that is earlier than the .NET Framework 4 in the project settings for your Visual Studio project, CAS policy will be enabled, including any custom CAS policies you specified for that version.</span></span> <span data-ttu-id="d11ed-134">Tuttavia, non sarà possibile usare nuovi tipi e membri di .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d11ed-134">However, you will not be able to use new .NET Framework 4 types and members.</span></span> <span data-ttu-id="d11ed-135">È anche possibile specificare una versione precedente del .NET Framework usando l' [ \<supportedRuntime> elemento](../startup/supportedruntime-element.md) nello schema delle impostazioni di avvio nel file di [configurazione dell'applicazione](../../index.md).</span><span class="sxs-lookup"><span data-stu-id="d11ed-135">You can also specify an earlier version of the .NET Framework by using the [\<supportedRuntime> element](../startup/supportedruntime-element.md) in the startup settings schema in your [application configuration file](../../index.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d11ed-136">La sintassi del file di configurazione distingue tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="d11ed-136">Configuration file syntax is case-sensitive.</span></span> <span data-ttu-id="d11ed-137">È necessario utilizzare la sintassi come indicato nelle sezioni Sintassi ed esempio.</span><span class="sxs-lookup"><span data-stu-id="d11ed-137">You should use the syntax as provided in the Syntax and Example sections.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="d11ed-138">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="d11ed-138">Configuration File</span></span>

<span data-ttu-id="d11ed-139">Questo elemento può essere utilizzato solo nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d11ed-139">This element can be used only in the application configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="d11ed-140">Esempio</span><span class="sxs-lookup"><span data-stu-id="d11ed-140">Example</span></span>

<span data-ttu-id="d11ed-141">Nell'esempio seguente viene illustrato come abilitare i criteri CAS legacy per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d11ed-141">The following example shows how to enable legacy CAS policy for an application.</span></span>

```xml
<configuration>
   <runtime>
      <NetFx40_LegacySecurityPolicy enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="d11ed-142">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="d11ed-142">See also</span></span>

- [<span data-ttu-id="d11ed-143">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="d11ed-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="d11ed-144">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="d11ed-144">Configuration File Schema</span></span>](../index.md)
