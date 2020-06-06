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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74802121"
---
# <a name="netfx45_cultureawarecomparergethashcode_longstrings-element"></a><span data-ttu-id="ac3d1-102">\<NetFx45_CultureAwareComparerGetHashCode_LongStrings> Elemento</span><span class="sxs-lookup"><span data-stu-id="ac3d1-102">\<NetFx45_CultureAwareComparerGetHashCode_LongStrings> Element</span></span>

<span data-ttu-id="ac3d1-103">Specifica se il runtime utilizza una quantità di memoria fissa per calcolare i codici hash per il metodo <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="ac3d1-103">Specifies whether the runtime uses a fixed amount of memory to calculate hash codes for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<NetFx45_CultureAwareComparerGetHashCode_LongStrings>**  

## <a name="syntax"></a><span data-ttu-id="ac3d1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ac3d1-104">Syntax</span></span>

```xml
<NetFx45_CultureAwareComparerGetHashCode_LongStrings enabled="0|1">
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ac3d1-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ac3d1-105">Attributes and Elements</span></span>

<span data-ttu-id="ac3d1-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ac3d1-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="ac3d1-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="ac3d1-107">Attributes</span></span>

|<span data-ttu-id="ac3d1-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="ac3d1-108">Attribute</span></span>|<span data-ttu-id="ac3d1-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ac3d1-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="ac3d1-110">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="ac3d1-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="ac3d1-111">Specifica se tramite Common Language Runtime viene allocata una quantità di memoria fissa durante il calcolo dei codici hash.</span><span class="sxs-lookup"><span data-stu-id="ac3d1-111">Specifies whether the common language runtime allocates a fixed amount of memory when calculating hash codes.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="ac3d1-112">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="ac3d1-112">enabled Attribute</span></span>

|<span data-ttu-id="ac3d1-113">Valore</span><span class="sxs-lookup"><span data-stu-id="ac3d1-113">Value</span></span>|<span data-ttu-id="ac3d1-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ac3d1-114">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="ac3d1-115">0</span><span class="sxs-lookup"><span data-stu-id="ac3d1-115">0</span></span>|<span data-ttu-id="ac3d1-116">Specifica se tramite Common Language Runtime viene allocata una quantità di memoria variabile al metodo <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> per il calcolo dei codici hash.</span><span class="sxs-lookup"><span data-stu-id="ac3d1-116">The common language runtime allocates a variable amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method to calculate hash codes.</span></span> <span data-ttu-id="ac3d1-117">Questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="ac3d1-117">This is the default.</span></span>|
|<span data-ttu-id="ac3d1-118">1</span><span class="sxs-lookup"><span data-stu-id="ac3d1-118">1</span></span>|<span data-ttu-id="ac3d1-119">Specifica se tramite Common Language Runtime viene allocata una quantità di memoria fissa al metodo <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> per il calcolo dei codici hash.</span><span class="sxs-lookup"><span data-stu-id="ac3d1-119">The common language runtime allocates a fixed amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method to calculate hash codes.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="ac3d1-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ac3d1-120">Child Elements</span></span>

<span data-ttu-id="ac3d1-121">No.</span><span class="sxs-lookup"><span data-stu-id="ac3d1-121">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ac3d1-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ac3d1-122">Parent Elements</span></span>

|<span data-ttu-id="ac3d1-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="ac3d1-123">Element</span></span>|<span data-ttu-id="ac3d1-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ac3d1-124">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="ac3d1-125">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ac3d1-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="ac3d1-126">Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ac3d1-126">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ac3d1-127">Commenti</span><span class="sxs-lookup"><span data-stu-id="ac3d1-127">Remarks</span></span>

<span data-ttu-id="ac3d1-128">Per impostazione predefinita, tramite Common Language Runtime viene allocata una quantità di memoria variabile per il metodo <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> e <xref:System.ArgumentException> può essere generata quando il metodo tenta di calcolare il codice hash di stringhe di dimensioni considerevoli (oltre diversi milioni di caratteri).</span><span class="sxs-lookup"><span data-stu-id="ac3d1-128">By default, the common language runtime allocates a variable amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method, and an <xref:System.ArgumentException> can be thrown when the method attempts to compute the hash code of very large strings (over several million characters long).</span></span> <span data-ttu-id="ac3d1-129">Aggiungendo questo elemento a un file di configurazione dell'applicazione e impostando il relativo attributo `enabled` su "1", è possibile specificare che il metodo <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> utilizza un algoritmo alternativo che alloca una quantità di memoria fissa per il calcolo di codici hash.</span><span class="sxs-lookup"><span data-stu-id="ac3d1-129">By adding this element to an application configuration file and setting its `enabled` attribute to "1", you can specify that the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method use an alternate algorithm that allocates a fixed amount of memory for the computation of hash codes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ac3d1-130">L' `<NetFx45_CultureAwareComparerGetHashCode_LongStrings>` elemento non viene usato in Windows 8 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="ac3d1-130">The `<NetFx45_CultureAwareComparerGetHashCode_LongStrings>` element is not used in Windows 8 and later versions.</span></span>

## <a name="see-also"></a><span data-ttu-id="ac3d1-131">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="ac3d1-131">See also</span></span>

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- [<span data-ttu-id="ac3d1-132">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="ac3d1-132">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="ac3d1-133">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="ac3d1-133">Configuration File Schema</span></span>](../index.md)
