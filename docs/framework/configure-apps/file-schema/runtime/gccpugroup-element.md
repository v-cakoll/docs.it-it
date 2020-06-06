---
title: <GCCpuGroup> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
ms.openlocfilehash: f1cbe5a7109d6e4aae2e92710920a1c6b3a40d00
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "82102892"
---
# <a name="gccpugroup-element"></a><span data-ttu-id="4d534-102">\<GCCpuGroup> Elemento</span><span class="sxs-lookup"><span data-stu-id="4d534-102">\<GCCpuGroup> Element</span></span>

<span data-ttu-id="4d534-103">Specifica se Garbage Collection supporta più gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="4d534-103">Specifies whether garbage collection supports multiple CPU groups.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<GCCpuGroup>**

## <a name="syntax"></a><span data-ttu-id="4d534-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4d534-104">Syntax</span></span>

```xml
<GCCpuGroup
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4d534-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4d534-105">Attributes and Elements</span></span>

<span data-ttu-id="4d534-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4d534-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="4d534-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="4d534-107">Attributes</span></span>

|<span data-ttu-id="4d534-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="4d534-108">Attribute</span></span>|<span data-ttu-id="4d534-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4d534-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="4d534-110">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="4d534-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="4d534-111">Specifica se Garbage Collection supporta più gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="4d534-111">Specifies whether garbage collection supports multiple CPU groups.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="4d534-112">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="4d534-112">enabled Attribute</span></span>

|<span data-ttu-id="4d534-113">Valore</span><span class="sxs-lookup"><span data-stu-id="4d534-113">Value</span></span>|<span data-ttu-id="4d534-114">Description</span><span class="sxs-lookup"><span data-stu-id="4d534-114">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="4d534-115">Garbage Collection non supporta più gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="4d534-115">Garbage collection does not support multiple CPU groups.</span></span> <span data-ttu-id="4d534-116">Questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="4d534-116">This is the default.</span></span>|
|`true`|<span data-ttu-id="4d534-117">Se il server Garbage Collection è abilitato, Garbage Collection supporta più gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="4d534-117">Garbage collection supports multiple CPU groups, if server garbage collection is enabled.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="4d534-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4d534-118">Child Elements</span></span>

<span data-ttu-id="4d534-119">No.</span><span class="sxs-lookup"><span data-stu-id="4d534-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="4d534-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4d534-120">Parent Elements</span></span>

|<span data-ttu-id="4d534-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="4d534-121">Element</span></span>|<span data-ttu-id="4d534-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4d534-122">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="4d534-123">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4d534-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="4d534-124">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="4d534-124">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4d534-125">Commenti</span><span class="sxs-lookup"><span data-stu-id="4d534-125">Remarks</span></span>

<span data-ttu-id="4d534-126">Quando un computer dispone di più gruppi di CPU e il Garbage Collection server è abilitato (vedere l' [\<gcServer>](gcserver-element.md) elemento), l'abilitazione di questo elemento estende Garbage Collection in tutti i gruppi di CPU e prende in considerazione tutti i core quando crea e bilancia gli heap.</span><span class="sxs-lookup"><span data-stu-id="4d534-126">When a computer has multiple CPU groups and server garbage collection is enabled (see the [\<gcServer>](gcserver-element.md) element), enabling this element extends garbage collection across all CPU groups and takes all cores into account when creating and balancing heaps.</span></span>

> [!NOTE]
> <span data-ttu-id="4d534-127">Questo elemento si applica solo ai thread Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="4d534-127">This element applies only to garbage collection threads.</span></span> <span data-ttu-id="4d534-128">Per consentire al runtime di distribuire i thread utente in tutti i gruppi di CPU, è necessario abilitare anche l' [\<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="4d534-128">To enable the runtime to distribute user threads across all CPU groups, you must also enable the [\<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md) element.</span></span>

## <a name="example"></a><span data-ttu-id="4d534-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="4d534-129">Example</span></span>

<span data-ttu-id="4d534-130">Nell'esempio seguente viene illustrato come abilitare Garbage Collection per più gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="4d534-130">The following example shows how to enable garbage collection for multiple CPU groups.</span></span>

```xml
<configuration>
   <runtime>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="4d534-131">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="4d534-131">See also</span></span>

- [<span data-ttu-id="4d534-132">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="4d534-132">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="4d534-133">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="4d534-133">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="4d534-134">Disabilitare Garbage Collection simultanee</span><span class="sxs-lookup"><span data-stu-id="4d534-134">Disable concurrent garbage collection</span></span>](gcconcurrent-element.md#to-disable-background-garbage-collection)
- [<span data-ttu-id="4d534-135">Operazione di Garbage Collection per workstation e server</span><span class="sxs-lookup"><span data-stu-id="4d534-135">Workstation and server garbage collection</span></span>](../../../../standard/garbage-collection/workstation-server-gc.md)
