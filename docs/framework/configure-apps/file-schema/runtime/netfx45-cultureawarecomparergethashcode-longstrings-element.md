---
title: Elemento <NetFx45_CultureAwareComparerGetHashCode_LongStrings>
ms.date: 03/30/2017
helpviewer_keywords:
- NetFx45_CultureAwareComparerGetHashCode_LongStrings element
- <NetFx45_CultureAwareComparerGetHashCode_LongStrings> element
- GetHashCode method
- hash codes, calculating
ms.assetid: 3a5f38d1-ebc8-44de-aaeb-2929f6e6b48f
ms.openlocfilehash: 413eb6c6e61b509135601c65cf045eabd849e8b3
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802121"
---
# <a name="netfx45_cultureawarecomparergethashcode_longstrings-element"></a><span data-ttu-id="f8b15-102">\<NetFx45_CultureAwareComparerGetHashCode_LongStrings elemento ></span><span class="sxs-lookup"><span data-stu-id="f8b15-102">\<NetFx45_CultureAwareComparerGetHashCode_LongStrings> Element</span></span>

<span data-ttu-id="f8b15-103">Specifica se il runtime utilizza una quantità di memoria fissa per calcolare i codici hash per il metodo <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="f8b15-103">Specifies whether the runtime uses a fixed amount of memory to calculate hash codes for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="f8b15-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f8b15-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f8b15-105">&nbsp;&nbsp;[ **\<runtime >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="f8b15-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="f8b15-106">&nbsp;&nbsp; **&nbsp;&nbsp;\<NetFx45_CultureAwareComparerGetHashCode_LongStrings >**</span><span class="sxs-lookup"><span data-stu-id="f8b15-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<NetFx45_CultureAwareComparerGetHashCode_LongStrings>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="f8b15-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f8b15-107">Syntax</span></span>

```xml
<NetFx45_CultureAwareComparerGetHashCode_LongStrings enabled="0|1">
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f8b15-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f8b15-108">Attributes and Elements</span></span>

<span data-ttu-id="f8b15-109">Le sezioni seguenti descrivono gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f8b15-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="f8b15-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="f8b15-110">Attributes</span></span>

|<span data-ttu-id="f8b15-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="f8b15-111">Attribute</span></span>|<span data-ttu-id="f8b15-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8b15-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="f8b15-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="f8b15-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="f8b15-114">Specifica se tramite Common Language Runtime viene allocata una quantità di memoria fissa durante il calcolo dei codici hash.</span><span class="sxs-lookup"><span data-stu-id="f8b15-114">Specifies whether the common language runtime allocates a fixed amount of memory when calculating hash codes.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="f8b15-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="f8b15-115">enabled Attribute</span></span>

|<span data-ttu-id="f8b15-116">Valore</span><span class="sxs-lookup"><span data-stu-id="f8b15-116">Value</span></span>|<span data-ttu-id="f8b15-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8b15-117">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="f8b15-118">0</span><span class="sxs-lookup"><span data-stu-id="f8b15-118">0</span></span>|<span data-ttu-id="f8b15-119">Specifica se tramite Common Language Runtime viene allocata una quantità di memoria variabile al metodo <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> per il calcolo dei codici hash.</span><span class="sxs-lookup"><span data-stu-id="f8b15-119">The common language runtime allocates a variable amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method to calculate hash codes.</span></span> <span data-ttu-id="f8b15-120">Questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="f8b15-120">This is the default.</span></span>|
|<span data-ttu-id="f8b15-121">1</span><span class="sxs-lookup"><span data-stu-id="f8b15-121">1</span></span>|<span data-ttu-id="f8b15-122">Specifica se tramite Common Language Runtime viene allocata una quantità di memoria fissa al metodo <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> per il calcolo dei codici hash.</span><span class="sxs-lookup"><span data-stu-id="f8b15-122">The common language runtime allocates a fixed amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method to calculate hash codes.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="f8b15-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f8b15-123">Child Elements</span></span>

<span data-ttu-id="f8b15-124">nessuna.</span><span class="sxs-lookup"><span data-stu-id="f8b15-124">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f8b15-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f8b15-125">Parent Elements</span></span>

|<span data-ttu-id="f8b15-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="f8b15-126">Element</span></span>|<span data-ttu-id="f8b15-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8b15-127">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="f8b15-128">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f8b15-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="f8b15-129">Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f8b15-129">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f8b15-130">Note</span><span class="sxs-lookup"><span data-stu-id="f8b15-130">Remarks</span></span>

<span data-ttu-id="f8b15-131">Per impostazione predefinita, tramite Common Language Runtime viene allocata una quantità di memoria variabile per il metodo <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> e <xref:System.ArgumentException> può essere generata quando il metodo tenta di calcolare il codice hash di stringhe di dimensioni considerevoli (oltre diversi milioni di caratteri).</span><span class="sxs-lookup"><span data-stu-id="f8b15-131">By default, the common language runtime allocates a variable amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method, and an <xref:System.ArgumentException> can be thrown when the method attempts to compute the hash code of very large strings (over several million characters long).</span></span> <span data-ttu-id="f8b15-132">Aggiungendo questo elemento a un file di configurazione dell'applicazione e impostando il relativo attributo `enabled` su "1", è possibile specificare che il metodo <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> utilizza un algoritmo alternativo che alloca una quantità di memoria fissa per il calcolo di codici hash.</span><span class="sxs-lookup"><span data-stu-id="f8b15-132">By adding this element to an application configuration file and setting its `enabled` attribute to "1", you can specify that the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method use an alternate algorithm that allocates a fixed amount of memory for the computation of hash codes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f8b15-133">L'elemento `<NetFx45_CultureAwareComparerGetHashCode_LongStrings>` non viene usato in Windows 8 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="f8b15-133">The `<NetFx45_CultureAwareComparerGetHashCode_LongStrings>` element is not used in Windows 8 and later versions.</span></span>

## <a name="see-also"></a><span data-ttu-id="f8b15-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8b15-134">See also</span></span>

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- [<span data-ttu-id="f8b15-135">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="f8b15-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f8b15-136">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="f8b15-136">Configuration File Schema</span></span>](../index.md)
