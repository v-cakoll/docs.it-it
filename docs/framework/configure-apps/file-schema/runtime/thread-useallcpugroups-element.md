---
title: Elemento <Thread_UseAllCpuGroups>
ms.date: 03/30/2017
ms.assetid: d30fe7c5-8469-46e2-b804-e3eec7b24256
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e964f1b2861926803b0449be06cbfd9567ac74a3
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252280"
---
# <a name="thread_useallcpugroups-element"></a><span data-ttu-id="e8270-102">\<Elemento > Thread_UseAllCpuGroups</span><span class="sxs-lookup"><span data-stu-id="e8270-102">\<Thread_UseAllCpuGroups> Element</span></span>

<span data-ttu-id="e8270-103">Specifica se il runtime distribuisce i thread gestiti tra tutti i gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="e8270-103">Specifies whether the runtime distributes managed threads across all CPU groups.</span></span>

<span data-ttu-id="e8270-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e8270-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e8270-105">&nbsp;&nbsp;[ **\<> di runtime**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="e8270-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="e8270-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<> Thread_UseAllCpuGroups**</span><span class="sxs-lookup"><span data-stu-id="e8270-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Thread_UseAllCpuGroups>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="e8270-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e8270-107">Syntax</span></span>

```xml
<Thread_UseAllCpuGroups
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e8270-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e8270-108">Attributes and Elements</span></span>

<span data-ttu-id="e8270-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e8270-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="e8270-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="e8270-110">Attributes</span></span>

|<span data-ttu-id="e8270-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="e8270-111">Attribute</span></span>|<span data-ttu-id="e8270-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e8270-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="e8270-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="e8270-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="e8270-114">Specifica se il runtime distribuisce i thread gestiti tra tutti i gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="e8270-114">Specifies whether the runtime distributes managed threads across all CPU groups.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="e8270-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="e8270-115">enabled Attribute</span></span>

|<span data-ttu-id="e8270-116">Valore</span><span class="sxs-lookup"><span data-stu-id="e8270-116">Value</span></span>|<span data-ttu-id="e8270-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e8270-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="e8270-118">Il runtime non distribuisce i thread gestiti tra più gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="e8270-118">The runtime does not distribute managed threads across multiple CPU groups.</span></span> <span data-ttu-id="e8270-119">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="e8270-119">This is the default.</span></span>|
|`true`|<span data-ttu-id="e8270-120">Il runtime distribuisce i thread gestiti tra più gruppi di CPU, se il computer dispone di più gruppi di CPU e l' [ \<elemento > GCCpuGroup](gccpugroup-element.md) è abilitato.</span><span class="sxs-lookup"><span data-stu-id="e8270-120">The runtime distributes managed threads across multiple CPU groups, if the computer has multiple CPU groups and the [\<GCCpuGroup>](gccpugroup-element.md) element is enabled.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="e8270-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e8270-121">Child Elements</span></span>

<span data-ttu-id="e8270-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="e8270-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e8270-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e8270-123">Parent Elements</span></span>

|<span data-ttu-id="e8270-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="e8270-124">Element</span></span>|<span data-ttu-id="e8270-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e8270-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="e8270-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e8270-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="e8270-127">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="e8270-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e8270-128">Note</span><span class="sxs-lookup"><span data-stu-id="e8270-128">Remarks</span></span>

<span data-ttu-id="e8270-129">Quando un computer dispone di più gruppi di CPU, l'abilitazione di questo elemento fa sì che il runtime distribuisca i thread gestiti in tutti i gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="e8270-129">When a computer has multiple CPU groups, enabling this element causes the runtime to distribute managed threads across all CPU groups.</span></span> <span data-ttu-id="e8270-130">Per usare questa funzionalità, è necessario abilitare anche l'elemento [ \<> GCCpuGroup](gccpugroup-element.md) , che estende Garbage Collection a tutti i gruppi di CPU e prende in considerazione tutti i core quando crea e bilancia gli heap.</span><span class="sxs-lookup"><span data-stu-id="e8270-130">To use this feature, you must also enable the [\<GCCpuGroup>](gccpugroup-element.md) element, which extends garbage collection to all CPU groups and takes all cores into account when creating and balancing heaps.</span></span> <span data-ttu-id="e8270-131">L'abilitazione dell' [ \<elemento > GCCpuGroup](gccpugroup-element.md) richiede l'abilitazione dell'elemento [ \<> di gcserver](gcserver-element.md) .</span><span class="sxs-lookup"><span data-stu-id="e8270-131">Enabling the [\<GCCpuGroup>](gccpugroup-element.md) element requires enabling the [\<gcServer>](gcserver-element.md) element.</span></span> <span data-ttu-id="e8270-132">Se questi elementi non sono abilitati, l' `<Thread_UseAllCpuGroups>` abilitazione dell'elemento non ha alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="e8270-132">If these elements are not enabled, enabling the `<Thread_UseAllCpuGroups>` element has no effect.</span></span>

## <a name="example"></a><span data-ttu-id="e8270-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="e8270-133">Example</span></span>

<span data-ttu-id="e8270-134">Nell'esempio seguente viene illustrato come abilitare il supporto per più gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="e8270-134">The following example shows how to enable support for multiple CPU groups.</span></span>

```xml
<configuration>
   <runtime>
      <Thread_UseAllCpuGroups enabled="true"/>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="e8270-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8270-135">See also</span></span>

- [<span data-ttu-id="e8270-136">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="e8270-136">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e8270-137">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="e8270-137">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="e8270-138">\<Elemento > GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="e8270-138">\<GCCpuGroup> Element</span></span>](gccpugroup-element.md)
