---
title: <GCCpuGroup> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9ff646f13c5619b0bfca1b61c86013a981c274e3
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252568"
---
# <a name="gccpugroup-element"></a><span data-ttu-id="0744c-102">\<Elemento > GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="0744c-102">\<GCCpuGroup> Element</span></span>

<span data-ttu-id="0744c-103">Specifica se Garbage Collection supporta più gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="0744c-103">Specifies whether garbage collection supports multiple CPU groups.</span></span>

<span data-ttu-id="0744c-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0744c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0744c-105">&nbsp;&nbsp;[ **\<> di runtime**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="0744c-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="0744c-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<GCCpuGroup>**</span><span class="sxs-lookup"><span data-stu-id="0744c-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<GCCpuGroup>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="0744c-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0744c-107">Syntax</span></span>

```xml
<GCCpuGroup
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0744c-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0744c-108">Attributes and Elements</span></span>

<span data-ttu-id="0744c-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0744c-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="0744c-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="0744c-110">Attributes</span></span>

|<span data-ttu-id="0744c-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="0744c-111">Attribute</span></span>|<span data-ttu-id="0744c-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0744c-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="0744c-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="0744c-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="0744c-114">Specifica se Garbage Collection supporta più gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="0744c-114">Specifies whether garbage collection supports multiple CPU groups.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="0744c-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="0744c-115">enabled Attribute</span></span>

|<span data-ttu-id="0744c-116">Valore</span><span class="sxs-lookup"><span data-stu-id="0744c-116">Value</span></span>|<span data-ttu-id="0744c-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0744c-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="0744c-118">Garbage Collection non supporta più gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="0744c-118">Garbage collection does not support multiple CPU groups.</span></span> <span data-ttu-id="0744c-119">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="0744c-119">This is the default.</span></span>|
|`true`|<span data-ttu-id="0744c-120">Se il server Garbage Collection è abilitato, Garbage Collection supporta più gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="0744c-120">Garbage collection supports multiple CPU groups, if server garbage collection is enabled.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="0744c-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0744c-121">Child Elements</span></span>

<span data-ttu-id="0744c-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="0744c-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0744c-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0744c-123">Parent Elements</span></span>

|<span data-ttu-id="0744c-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="0744c-124">Element</span></span>|<span data-ttu-id="0744c-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0744c-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="0744c-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0744c-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="0744c-127">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="0744c-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="0744c-128">Note</span><span class="sxs-lookup"><span data-stu-id="0744c-128">Remarks</span></span>

<span data-ttu-id="0744c-129">Quando un computer dispone di più gruppi di CPU e Garbage Collection server è abilitato (vedere l' [ \<elemento > gcserver](gcserver-element.md) ), l'abilitazione di questo elemento estende Garbage Collection in tutti i gruppi di CPU e prende in considerazione tutti i core durante la creazione e heap di bilanciamento.</span><span class="sxs-lookup"><span data-stu-id="0744c-129">When a computer has multiple CPU groups and server garbage collection is enabled (see the [\<gcServer>](gcserver-element.md) element), enabling this element extends garbage collection across all CPU groups and takes all cores into account when creating and balancing heaps.</span></span>

> [!NOTE]
> <span data-ttu-id="0744c-130">Questo elemento si applica solo ai thread Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="0744c-130">This element applies only to garbage collection threads.</span></span> <span data-ttu-id="0744c-131">Per consentire al runtime di distribuire i thread utente in tutti i gruppi di CPU, è necessario abilitare anche l' [ \<elemento Thread_UseAllCpuGroups >](thread-useallcpugroups-element.md) .</span><span class="sxs-lookup"><span data-stu-id="0744c-131">To enable the runtime to distribute user threads across all CPU groups, you must also enable the [\<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md) element.</span></span>

## <a name="example"></a><span data-ttu-id="0744c-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="0744c-132">Example</span></span>

<span data-ttu-id="0744c-133">Nell'esempio seguente viene illustrato come abilitare Garbage Collection per più gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="0744c-133">The following example shows how to enable garbage collection for multiple CPU groups.</span></span>

```xml
<configuration>
   <runtime>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="0744c-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0744c-134">See also</span></span>

- [<span data-ttu-id="0744c-135">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="0744c-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="0744c-136">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="0744c-136">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="0744c-137">Per disabilitare Garbage Collection simultanee</span><span class="sxs-lookup"><span data-stu-id="0744c-137">To disable concurrent garbage collection</span></span>](gcconcurrent-element.md#to-disable-background-garbage-collection)
- [<span data-ttu-id="0744c-138">Operazione di Garbage Collection per workstation e server</span><span class="sxs-lookup"><span data-stu-id="0744c-138">Workstation and server garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md#workstation_and_server_garbage_collection)
