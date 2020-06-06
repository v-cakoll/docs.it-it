---
title: Elemento GCLOHThreshold
ms.date: 11/20/2019
helpviewer_keywords:
- GCLOHThreshold element
- <GCLOHThreshold> element
ms.openlocfilehash: d72dc9d27984f60dfb6296217263ce8b176093c6
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74451220"
---
# <a name="gclohthreshold-element"></a><span data-ttu-id="c709c-102">Elemento GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="c709c-102">GCLOHThreshold element</span></span>

<span data-ttu-id="c709c-103">Specifica la dimensione della soglia, in byte, che fa in modo che il Garbage Collector inserisca gli oggetti nell'heap degli oggetti grandi (LOH).</span><span class="sxs-lookup"><span data-stu-id="c709c-103">Specifies the threshold size, in bytes, that causes the garbage collector to put objects on the large object heap (LOH).</span></span>

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;[\<runtime>](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;\<GCLOHThreshold>

## <a name="syntax"></a><span data-ttu-id="c709c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c709c-104">Syntax</span></span>

```xml
<GCLOHThreshold
   enabled="nnnn"/>
```

## <a name="attributes"></a><span data-ttu-id="c709c-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="c709c-105">Attributes</span></span>

|<span data-ttu-id="c709c-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="c709c-106">Attribute</span></span>|<span data-ttu-id="c709c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c709c-107">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="c709c-108">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="c709c-108">Required attribute.</span></span><br /><br /><span data-ttu-id="c709c-109">Specifica le dimensioni della soglia che determinano l'uso degli oggetti nell'heap degli oggetti grandi.</span><span class="sxs-lookup"><span data-stu-id="c709c-109">Specifies the threshold size that causes objects to go on the large object heap.</span></span>|

### <a name="enabled-attribute"></a><span data-ttu-id="c709c-110">attributo enabled</span><span class="sxs-lookup"><span data-stu-id="c709c-110">enabled attribute</span></span>

|<span data-ttu-id="c709c-111">Valore</span><span class="sxs-lookup"><span data-stu-id="c709c-111">Value</span></span>|<span data-ttu-id="c709c-112">Description</span><span class="sxs-lookup"><span data-stu-id="c709c-112">Description</span></span>|
|-----------|-----------------|
|`nnnn`|<span data-ttu-id="c709c-113">Dimensione della soglia, in byte, che fa sì che gli oggetti vadano nell'heap degli oggetti grandi.</span><span class="sxs-lookup"><span data-stu-id="c709c-113">The threshold size, in bytes, that causes objects to go on the large object heap.</span></span>|

## <a name="child-elements"></a><span data-ttu-id="c709c-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c709c-114">Child elements</span></span>

<span data-ttu-id="c709c-115">No.</span><span class="sxs-lookup"><span data-stu-id="c709c-115">None.</span></span>

## <a name="parent-elements"></a><span data-ttu-id="c709c-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c709c-116">Parent elements</span></span>

|<span data-ttu-id="c709c-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="c709c-117">Element</span></span>|<span data-ttu-id="c709c-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c709c-118">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="c709c-119">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c709c-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="c709c-120">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="c709c-120">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c709c-121">Commenti</span><span class="sxs-lookup"><span data-stu-id="c709c-121">Remarks</span></span>

<span data-ttu-id="c709c-122">Questa impostazione è stata introdotta in .NET Framework 4,8.</span><span class="sxs-lookup"><span data-stu-id="c709c-122">This setting was introduced in .NET Framework 4.8.</span></span>

## <a name="see-also"></a><span data-ttu-id="c709c-123">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="c709c-123">See also</span></span>

- [<span data-ttu-id="c709c-124">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="c709c-124">Run-time settings schema</span></span>](index.md)
- [<span data-ttu-id="c709c-125">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="c709c-125">Configuration file schema</span></span>](../index.md)
- [<span data-ttu-id="c709c-126">Nozioni fondamentali di Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="c709c-126">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="c709c-127">Opzioni di configurazione della fase di esecuzione di NET Core per GC</span><span class="sxs-lookup"><span data-stu-id="c709c-127">NET Core run-time config options for GC</span></span>](../../../../core/run-time-config/garbage-collector.md)
