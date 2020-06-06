---
title: Elemento <Thread_UseAllCpuGroups>
ms.date: 03/30/2017
ms.assetid: d30fe7c5-8469-46e2-b804-e3eec7b24256
ms.openlocfilehash: a3a612c0ffbcb211157b9623d298ce8ad7a13e94
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73115403"
---
# <a name="thread_useallcpugroups-element"></a><span data-ttu-id="1ec4a-102">\<Thread_UseAllCpuGroups> Elemento</span><span class="sxs-lookup"><span data-stu-id="1ec4a-102">\<Thread_UseAllCpuGroups> Element</span></span>

<span data-ttu-id="1ec4a-103">Specifica se il runtime distribuisce i thread gestiti tra tutti i gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="1ec4a-103">Specifies whether the runtime distributes managed threads across all CPU groups.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<Thread_UseAllCpuGroups>**  

## <a name="syntax"></a><span data-ttu-id="1ec4a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1ec4a-104">Syntax</span></span>

```xml
<Thread_UseAllCpuGroups
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1ec4a-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1ec4a-105">Attributes and Elements</span></span>

<span data-ttu-id="1ec4a-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1ec4a-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="1ec4a-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="1ec4a-107">Attributes</span></span>

|<span data-ttu-id="1ec4a-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="1ec4a-108">Attribute</span></span>|<span data-ttu-id="1ec4a-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1ec4a-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="1ec4a-110">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="1ec4a-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="1ec4a-111">Specifica se il runtime distribuisce i thread gestiti tra tutti i gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="1ec4a-111">Specifies whether the runtime distributes managed threads across all CPU groups.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="1ec4a-112">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="1ec4a-112">enabled Attribute</span></span>

|<span data-ttu-id="1ec4a-113">Valore</span><span class="sxs-lookup"><span data-stu-id="1ec4a-113">Value</span></span>|<span data-ttu-id="1ec4a-114">Description</span><span class="sxs-lookup"><span data-stu-id="1ec4a-114">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="1ec4a-115">Il runtime non distribuisce i thread gestiti tra più gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="1ec4a-115">The runtime does not distribute managed threads across multiple CPU groups.</span></span> <span data-ttu-id="1ec4a-116">Questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="1ec4a-116">This is the default.</span></span>|
|`true`|<span data-ttu-id="1ec4a-117">Il runtime distribuisce i thread gestiti tra più gruppi di CPU, se il computer dispone di più gruppi di CPU e l' [\<GCCpuGroup>](gccpugroup-element.md) elemento è abilitato.</span><span class="sxs-lookup"><span data-stu-id="1ec4a-117">The runtime distributes managed threads across multiple CPU groups, if the computer has multiple CPU groups and the [\<GCCpuGroup>](gccpugroup-element.md) element is enabled.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="1ec4a-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1ec4a-118">Child Elements</span></span>

<span data-ttu-id="1ec4a-119">No.</span><span class="sxs-lookup"><span data-stu-id="1ec4a-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1ec4a-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1ec4a-120">Parent Elements</span></span>

|<span data-ttu-id="1ec4a-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="1ec4a-121">Element</span></span>|<span data-ttu-id="1ec4a-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1ec4a-122">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="1ec4a-123">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1ec4a-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="1ec4a-124">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="1ec4a-124">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="1ec4a-125">Commenti</span><span class="sxs-lookup"><span data-stu-id="1ec4a-125">Remarks</span></span>

<span data-ttu-id="1ec4a-126">Quando un computer dispone di più gruppi di CPU, l'abilitazione di questo elemento fa sì che il runtime distribuisca i thread gestiti in tutti i gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="1ec4a-126">When a computer has multiple CPU groups, enabling this element causes the runtime to distribute managed threads across all CPU groups.</span></span> <span data-ttu-id="1ec4a-127">Per usare questa funzionalità, è necessario abilitare anche l' [\<GCCpuGroup>](gccpugroup-element.md) elemento, che estende Garbage Collection a tutti i gruppi di CPU e prende in considerazione tutti i core quando crea e bilancia gli heap.</span><span class="sxs-lookup"><span data-stu-id="1ec4a-127">To use this feature, you must also enable the [\<GCCpuGroup>](gccpugroup-element.md) element, which extends garbage collection to all CPU groups and takes all cores into account when creating and balancing heaps.</span></span> <span data-ttu-id="1ec4a-128">L'abilitazione dell' [\<GCCpuGroup>](gccpugroup-element.md) elemento richiede l'abilitazione dell' [\<gcServer>](gcserver-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="1ec4a-128">Enabling the [\<GCCpuGroup>](gccpugroup-element.md) element requires enabling the [\<gcServer>](gcserver-element.md) element.</span></span> <span data-ttu-id="1ec4a-129">Se questi elementi non sono abilitati, l'abilitazione dell' `<Thread_UseAllCpuGroups>` elemento non ha alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="1ec4a-129">If these elements are not enabled, enabling the `<Thread_UseAllCpuGroups>` element has no effect.</span></span>

## <a name="example"></a><span data-ttu-id="1ec4a-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="1ec4a-130">Example</span></span>

<span data-ttu-id="1ec4a-131">Nell'esempio seguente viene illustrato come abilitare il supporto per più gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="1ec4a-131">The following example shows how to enable support for multiple CPU groups.</span></span>

```xml
<configuration>
   <runtime>
      <Thread_UseAllCpuGroups enabled="true"/>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="1ec4a-132">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="1ec4a-132">See also</span></span>

- [<span data-ttu-id="1ec4a-133">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="1ec4a-133">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="1ec4a-134">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="1ec4a-134">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="1ec4a-135">\<GCCpuGroup>Elemento</span><span class="sxs-lookup"><span data-stu-id="1ec4a-135">\<GCCpuGroup> Element</span></span>](gccpugroup-element.md)
