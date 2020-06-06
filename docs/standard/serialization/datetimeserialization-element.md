---
title: <dateTimeSerialization> Elemento
description: Questo articolo descrive l' <dateTimeSerialization> elemento, che determina la modalità di serializzazione degli oggetti DateTime.
ms.date: 03/30/2017
helpviewer_keywords:
- dateTimeSerialization element
- XML serialization, configuration
- <dateTimeSerialization> element
ms.assetid: 90fda55c-7730-41e9-bc4b-6423a4b920af
ms.openlocfilehash: a2684ab72c1fb109d711e333e01836d3399caf86
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "84289642"
---
# <a name="datetimeserialization-element"></a><span data-ttu-id="05d95-103">\<dateTimeSerialization> Elemento</span><span class="sxs-lookup"><span data-stu-id="05d95-103">\<dateTimeSerialization> Element</span></span>
<span data-ttu-id="05d95-104">Determina la modalità di serializzazione degli oggetti <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="05d95-104">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>  
  
 \<configuration>  
\<dateTimeSerialization>  
  
## <a name="syntax"></a><span data-ttu-id="05d95-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="05d95-105">Syntax</span></span>  
  
```xml  
<dateTimeSerialization  
    mode = "Roundtrip|Local"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="05d95-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="05d95-106">Attributes and Elements</span></span>  
 <span data-ttu-id="05d95-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="05d95-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="05d95-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="05d95-108">Attributes</span></span>  
  
|<span data-ttu-id="05d95-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="05d95-109">Attributes</span></span>|<span data-ttu-id="05d95-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="05d95-110">Description</span></span>|  
|----------------|-----------------|  
|`mode`|<span data-ttu-id="05d95-111">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="05d95-111">Optional.</span></span> <span data-ttu-id="05d95-112">Specifica la modalità di serializzazione.</span><span class="sxs-lookup"><span data-stu-id="05d95-112">Specifies the serialization mode.</span></span> <span data-ttu-id="05d95-113">Impostarlo a uno dei valori di <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>.</span><span class="sxs-lookup"><span data-stu-id="05d95-113">Set to one of the <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> values.</span></span> <span data-ttu-id="05d95-114">Il valore predefinito è **RoundTrip**.</span><span class="sxs-lookup"><span data-stu-id="05d95-114">The default is **RoundTrip**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="05d95-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="05d95-115">Child Elements</span></span>  
 <span data-ttu-id="05d95-116">No.</span><span class="sxs-lookup"><span data-stu-id="05d95-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="05d95-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="05d95-117">Parent Elements</span></span>  
  
|<span data-ttu-id="05d95-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="05d95-118">Element</span></span>|<span data-ttu-id="05d95-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="05d95-119">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="05d95-120">system.xml.serialization</span><span class="sxs-lookup"><span data-stu-id="05d95-120">system.xml.serialization</span></span>|<span data-ttu-id="05d95-121">L'elemento di primo livello per il controllo della serializzazione XML.</span><span class="sxs-lookup"><span data-stu-id="05d95-121">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05d95-122">Commenti</span><span class="sxs-lookup"><span data-stu-id="05d95-122">Remarks</span></span>  
 <span data-ttu-id="05d95-123">Nelle versioni 1,0, 1,1, 2,0 e versioni successive del .NET Framework, quando questa proprietà è impostata su **local**, <xref:System.DateTime> gli oggetti vengono sempre formattati come ora locale.</span><span class="sxs-lookup"><span data-stu-id="05d95-123">In versions 1.0, 1.1, 2.0 and later versions of the .NET Framework, when this property is set to **Local**, <xref:System.DateTime> objects are always formatted as the local time.</span></span> <span data-ttu-id="05d95-124">Vale a dire che le informazioni relative al fuso orario locale vengono sempre incluse tra dati serializzati.</span><span class="sxs-lookup"><span data-stu-id="05d95-124">That is, local time zone information is always included with the serialized data.</span></span> <span data-ttu-id="05d95-125">Impostare questa proprietà su **Local** per garantire la compatibilità con le versioni precedenti di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="05d95-125">Set this property to **Local** to ensure compatibility with older versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="05d95-126">Nella versione 2,0 e nelle versioni successive del .NET Framework la cui proprietà è impostata su **round trip**, <xref:System.DateTime> gli oggetti vengono esaminati per determinare se si trovano in locale, UTC o in un fuso orario non specificato.</span><span class="sxs-lookup"><span data-stu-id="05d95-126">In version 2.0 and later versions of the .NET Framework that have this property set to **Roundtrip**, <xref:System.DateTime> objects are examined to determine whether they are in the local, UTC, or an unspecified time zone.</span></span> <span data-ttu-id="05d95-127">Gli oggetti <xref:System.DateTime> vengono quindi serializzati in modo tale che tali informazioni vengano preservate.</span><span class="sxs-lookup"><span data-stu-id="05d95-127">The <xref:System.DateTime> objects are then serialized in such a way that this information is preserved.</span></span> <span data-ttu-id="05d95-128">Si tratta del comportamento predefinito, consigliato per tutte le nuove applicazioni che non comunicano con le versioni precedenti del framework.</span><span class="sxs-lookup"><span data-stu-id="05d95-128">This is the default behavior and is the recommended behavior for all new applications that do not communicate with older versions of the framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05d95-129">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="05d95-129">See also</span></span>

- <xref:System.DateTime>
- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="05d95-130">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="05d95-130">Configuration File Schema</span></span>](../../framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="05d95-131">\<schemaImporterExtensions>Elemento</span><span class="sxs-lookup"><span data-stu-id="05d95-131">\<schemaImporterExtensions> Element</span></span>](schemaimporterextensions-element.md)
- [<span data-ttu-id="05d95-132">\<add>Elemento per\<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="05d95-132">\<add> Element for \<schemaImporterExtensions></span></span>](add-element-for-schemaimporterextensions.md)
- [<span data-ttu-id="05d95-133">\<system.xml.serialization>Elemento</span><span class="sxs-lookup"><span data-stu-id="05d95-133">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)
