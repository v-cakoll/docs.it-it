---
title: <dateTimeSerialization> Elemento
description: Questo articolo descrive l' <dateTimeSerialization> elemento, che determina la modalità di serializzazione degli oggetti DateTime.
ms.date: 03/30/2017
helpviewer_keywords:
- dateTimeSerialization element
- XML serialization, configuration
- <dateTimeSerialization> element
ms.assetid: 90fda55c-7730-41e9-bc4b-6423a4b920af
ms.openlocfilehash: 652a88e25f59cd905e47ef71351e47e67f375286
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83375817"
---
# <a name="datetimeserialization-element"></a><span data-ttu-id="b6e75-103">\<Elemento dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="b6e75-103">\<dateTimeSerialization> Element</span></span>
<span data-ttu-id="b6e75-104">Determina la modalità di serializzazione degli oggetti <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="b6e75-104">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>  
  
 <span data-ttu-id="b6e75-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b6e75-105">\<configuration></span></span>  
<span data-ttu-id="b6e75-106">\<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="b6e75-106">\<dateTimeSerialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6e75-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b6e75-107">Syntax</span></span>  
  
```xml  
<dateTimeSerialization  
    mode = "Roundtrip|Local"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b6e75-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b6e75-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b6e75-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b6e75-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b6e75-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="b6e75-110">Attributes</span></span>  
  
|<span data-ttu-id="b6e75-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="b6e75-111">Attributes</span></span>|<span data-ttu-id="b6e75-112">Description</span><span class="sxs-lookup"><span data-stu-id="b6e75-112">Description</span></span>|  
|----------------|-----------------|  
|`mode`|<span data-ttu-id="b6e75-113">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="b6e75-113">Optional.</span></span> <span data-ttu-id="b6e75-114">Specifica la modalità di serializzazione.</span><span class="sxs-lookup"><span data-stu-id="b6e75-114">Specifies the serialization mode.</span></span> <span data-ttu-id="b6e75-115">Impostarlo a uno dei valori di <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>.</span><span class="sxs-lookup"><span data-stu-id="b6e75-115">Set to one of the <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> values.</span></span> <span data-ttu-id="b6e75-116">Il valore predefinito è **RoundTrip**.</span><span class="sxs-lookup"><span data-stu-id="b6e75-116">The default is **RoundTrip**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b6e75-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b6e75-117">Child Elements</span></span>  
 <span data-ttu-id="b6e75-118">No.</span><span class="sxs-lookup"><span data-stu-id="b6e75-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b6e75-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b6e75-119">Parent Elements</span></span>  
  
|<span data-ttu-id="b6e75-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="b6e75-120">Element</span></span>|<span data-ttu-id="b6e75-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6e75-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b6e75-122">system.xml.serialization</span><span class="sxs-lookup"><span data-stu-id="b6e75-122">system.xml.serialization</span></span>|<span data-ttu-id="b6e75-123">L'elemento di primo livello per il controllo della serializzazione XML.</span><span class="sxs-lookup"><span data-stu-id="b6e75-123">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6e75-124">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b6e75-124">Remarks</span></span>  
 <span data-ttu-id="b6e75-125">Nelle versioni 1,0, 1,1, 2,0 e versioni successive del .NET Framework, quando questa proprietà è impostata su **local**, <xref:System.DateTime> gli oggetti vengono sempre formattati come ora locale.</span><span class="sxs-lookup"><span data-stu-id="b6e75-125">In versions 1.0, 1.1, 2.0 and later versions of the .NET Framework, when this property is set to **Local**, <xref:System.DateTime> objects are always formatted as the local time.</span></span> <span data-ttu-id="b6e75-126">Vale a dire che le informazioni relative al fuso orario locale vengono sempre incluse tra dati serializzati.</span><span class="sxs-lookup"><span data-stu-id="b6e75-126">That is, local time zone information is always included with the serialized data.</span></span> <span data-ttu-id="b6e75-127">Impostare questa proprietà su **Local** per garantire la compatibilità con le versioni precedenti di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b6e75-127">Set this property to **Local** to ensure compatibility with older versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="b6e75-128">Nella versione 2,0 e nelle versioni successive del .NET Framework la cui proprietà è impostata su **round trip**, <xref:System.DateTime> gli oggetti vengono esaminati per determinare se si trovano in locale, UTC o in un fuso orario non specificato.</span><span class="sxs-lookup"><span data-stu-id="b6e75-128">In version 2.0 and later versions of the .NET Framework that have this property set to **Roundtrip**, <xref:System.DateTime> objects are examined to determine whether they are in the local, UTC, or an unspecified time zone.</span></span> <span data-ttu-id="b6e75-129">Gli oggetti <xref:System.DateTime> vengono quindi serializzati in modo tale che tali informazioni vengano preservate.</span><span class="sxs-lookup"><span data-stu-id="b6e75-129">The <xref:System.DateTime> objects are then serialized in such a way that this information is preserved.</span></span> <span data-ttu-id="b6e75-130">Si tratta del comportamento predefinito, consigliato per tutte le nuove applicazioni che non comunicano con le versioni precedenti del framework.</span><span class="sxs-lookup"><span data-stu-id="b6e75-130">This is the default behavior and is the recommended behavior for all new applications that do not communicate with older versions of the framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6e75-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6e75-131">See also</span></span>

- <xref:System.DateTime>
- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="b6e75-132">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="b6e75-132">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="b6e75-133">\<Elemento> schemaImporterExtensions</span><span class="sxs-lookup"><span data-stu-id="b6e75-133">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)
- [<span data-ttu-id="b6e75-134">\<aggiungere> elemento per \< schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="b6e75-134">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)
- [<span data-ttu-id="b6e75-135">\<System. XML. Serialization> elemento</span><span class="sxs-lookup"><span data-stu-id="b6e75-135">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
