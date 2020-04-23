---
title: <GCCpuGroup> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
ms.openlocfilehash: f1cbe5a7109d6e4aae2e92710920a1c6b3a40d00
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102892"
---
# <a name="gccpugroup-element"></a><span data-ttu-id="bb94b-102">\<Elemento> GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="bb94b-102">\<GCCpuGroup> Element</span></span>

<span data-ttu-id="bb94b-103">Specifica se Garbage Collection supporta più gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="bb94b-103">Specifies whether garbage collection supports multiple CPU groups.</span></span>

<span data-ttu-id="bb94b-104">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="bb94b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="bb94b-105">&nbsp;&nbsp;[**\<>di runtime**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="bb94b-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="bb94b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<>di GCCpuGroup**</span><span class="sxs-lookup"><span data-stu-id="bb94b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<GCCpuGroup>**</span></span>

## <a name="syntax"></a><span data-ttu-id="bb94b-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bb94b-107">Syntax</span></span>

```xml
<GCCpuGroup
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bb94b-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="bb94b-108">Attributes and Elements</span></span>

<span data-ttu-id="bb94b-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="bb94b-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="bb94b-110">Attributes</span><span class="sxs-lookup"><span data-stu-id="bb94b-110">Attributes</span></span>

|<span data-ttu-id="bb94b-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="bb94b-111">Attribute</span></span>|<span data-ttu-id="bb94b-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb94b-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="bb94b-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="bb94b-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="bb94b-114">Specifica se Garbage Collection supporta più gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="bb94b-114">Specifies whether garbage collection supports multiple CPU groups.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="bb94b-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="bb94b-115">enabled Attribute</span></span>

|<span data-ttu-id="bb94b-116">valore</span><span class="sxs-lookup"><span data-stu-id="bb94b-116">Value</span></span>|<span data-ttu-id="bb94b-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb94b-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="bb94b-118">La procedura di Garbage Collection non supporta più gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="bb94b-118">Garbage collection does not support multiple CPU groups.</span></span> <span data-ttu-id="bb94b-119">Questa è la modalità predefinita.</span><span class="sxs-lookup"><span data-stu-id="bb94b-119">This is the default.</span></span>|
|`true`|<span data-ttu-id="bb94b-120">La Garbage Collection supporta più gruppi di CPU, se l'operazione di Garbage Collection per server è abilitata.</span><span class="sxs-lookup"><span data-stu-id="bb94b-120">Garbage collection supports multiple CPU groups, if server garbage collection is enabled.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="bb94b-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="bb94b-121">Child Elements</span></span>

<span data-ttu-id="bb94b-122">No.</span><span class="sxs-lookup"><span data-stu-id="bb94b-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="bb94b-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="bb94b-123">Parent Elements</span></span>

|<span data-ttu-id="bb94b-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="bb94b-124">Element</span></span>|<span data-ttu-id="bb94b-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb94b-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="bb94b-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bb94b-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="bb94b-127">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="bb94b-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="bb94b-128">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="bb94b-128">Remarks</span></span>

<span data-ttu-id="bb94b-129">Quando un computer dispone di più gruppi di CPU e la Garbage Collection del server è abilitata (vedere l'elemento [ \<gallida>),](gcserver-element.md) l'abilitazione di questo elemento estende l'operazione di Garbage Collection in tutti i gruppi di CPU e tiene conto di tutti i core durante la creazione e il bilanciamento degli heap.</span><span class="sxs-lookup"><span data-stu-id="bb94b-129">When a computer has multiple CPU groups and server garbage collection is enabled (see the [\<gcServer>](gcserver-element.md) element), enabling this element extends garbage collection across all CPU groups and takes all cores into account when creating and balancing heaps.</span></span>

> [!NOTE]
> <span data-ttu-id="bb94b-130">Questo elemento si applica solo ai thread di Garbage Collection.This element applies only to garbage collection threads.</span><span class="sxs-lookup"><span data-stu-id="bb94b-130">This element applies only to garbage collection threads.</span></span> <span data-ttu-id="bb94b-131">Per consentire al runtime di distribuire i thread utente tra tutti i gruppi di CPU, è necessario abilitare anche l'elemento [ \<>Thread_UseAllCpuGroups.](thread-useallcpugroups-element.md)</span><span class="sxs-lookup"><span data-stu-id="bb94b-131">To enable the runtime to distribute user threads across all CPU groups, you must also enable the [\<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md) element.</span></span>

## <a name="example"></a><span data-ttu-id="bb94b-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="bb94b-132">Example</span></span>

<span data-ttu-id="bb94b-133">Nell'esempio seguente viene illustrato come abilitare la procedura di Garbage Collection per più gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="bb94b-133">The following example shows how to enable garbage collection for multiple CPU groups.</span></span>

```xml
<configuration>
   <runtime>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="bb94b-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb94b-134">See also</span></span>

- [<span data-ttu-id="bb94b-135">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="bb94b-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="bb94b-136">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="bb94b-136">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="bb94b-137">Disabilitare Garbage Collection simultanea</span><span class="sxs-lookup"><span data-stu-id="bb94b-137">Disable concurrent garbage collection</span></span>](gcconcurrent-element.md#to-disable-background-garbage-collection)
- [<span data-ttu-id="bb94b-138">Operazione di Garbage Collection per workstation e server</span><span class="sxs-lookup"><span data-stu-id="bb94b-138">Workstation and server garbage collection</span></span>](../../../../standard/garbage-collection/workstation-server-gc.md)
