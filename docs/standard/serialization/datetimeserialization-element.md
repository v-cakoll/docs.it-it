---
title: <dateTimeSerialization> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- dateTimeSerialization element
- XML serialization, configuration
- <dateTimeSerialization> element
ms.assetid: 90fda55c-7730-41e9-bc4b-6423a4b920af
ms.openlocfilehash: 180a4942dd4b701b56fe4788d5f8cd8607faaedd
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459270"
---
# <a name="datetimeserialization-element"></a><span data-ttu-id="24226-102">\<Elemento dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="24226-102">\<dateTimeSerialization> Element</span></span>
<span data-ttu-id="24226-103">Determina la modalità di serializzazione degli oggetti <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="24226-103">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>  
  
 <span data-ttu-id="24226-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="24226-104">\<configuration></span></span>  
<span data-ttu-id="24226-105">\<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="24226-105">\<dateTimeSerialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24226-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="24226-106">Syntax</span></span>  
  
```xml  
<dateTimeSerialization  
    mode = "Roundtrip|Local"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="24226-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="24226-107">Attributes and Elements</span></span>  
 <span data-ttu-id="24226-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="24226-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="24226-109">Attributes</span><span class="sxs-lookup"><span data-stu-id="24226-109">Attributes</span></span>  
  
|<span data-ttu-id="24226-110">Attributes</span><span class="sxs-lookup"><span data-stu-id="24226-110">Attributes</span></span>|<span data-ttu-id="24226-111">Description</span><span class="sxs-lookup"><span data-stu-id="24226-111">Description</span></span>|  
|----------------|-----------------|  
|`mode`|<span data-ttu-id="24226-112">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="24226-112">Optional.</span></span> <span data-ttu-id="24226-113">Specifica la modalità di serializzazione.</span><span class="sxs-lookup"><span data-stu-id="24226-113">Specifies the serialization mode.</span></span> <span data-ttu-id="24226-114">Impostarlo a uno dei valori di <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>.</span><span class="sxs-lookup"><span data-stu-id="24226-114">Set to one of the <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> values.</span></span> <span data-ttu-id="24226-115">Il valore predefinito è **RoundTrip**.</span><span class="sxs-lookup"><span data-stu-id="24226-115">The default is **RoundTrip**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="24226-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="24226-116">Child Elements</span></span>  
 <span data-ttu-id="24226-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="24226-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="24226-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="24226-118">Parent Elements</span></span>  
  
|<span data-ttu-id="24226-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="24226-119">Element</span></span>|<span data-ttu-id="24226-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="24226-120">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="24226-121">system.xml.serialization</span><span class="sxs-lookup"><span data-stu-id="24226-121">system.xml.serialization</span></span>|<span data-ttu-id="24226-122">L'elemento di primo livello per il controllo della serializzazione XML.</span><span class="sxs-lookup"><span data-stu-id="24226-122">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="24226-123">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="24226-123">Remarks</span></span>  
 <span data-ttu-id="24226-124">Nelle versioni 1,0, 1,1, 2,0 e versioni successive del .NET Framework, quando questa proprietà è impostata su **local**, <xref:System.DateTime> gli oggetti vengono sempre formattati come ora locale.</span><span class="sxs-lookup"><span data-stu-id="24226-124">In versions 1.0, 1.1, 2.0 and later versions of the .NET Framework, when this property is set to **Local**, <xref:System.DateTime> objects are always formatted as the local time.</span></span> <span data-ttu-id="24226-125">Vale a dire che le informazioni relative al fuso orario locale vengono sempre incluse tra dati serializzati.</span><span class="sxs-lookup"><span data-stu-id="24226-125">That is, local time zone information is always included with the serialized data.</span></span> <span data-ttu-id="24226-126">Impostare questa proprietà su **Local** per garantire la compatibilità con le versioni precedenti di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="24226-126">Set this property to **Local** to ensure compatibility with older versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="24226-127">Nella versione 2,0 e nelle versioni successive del .NET Framework la cui proprietà è impostata su **round trip**, <xref:System.DateTime> gli oggetti vengono esaminati per determinare se si trovano in locale, UTC o in un fuso orario non specificato.</span><span class="sxs-lookup"><span data-stu-id="24226-127">In version 2.0 and later versions of the .NET Framework that have this property set to **Roundtrip**, <xref:System.DateTime> objects are examined to determine whether they are in the local, UTC, or an unspecified time zone.</span></span> <span data-ttu-id="24226-128">Gli oggetti <xref:System.DateTime> vengono quindi serializzati in modo tale che tali informazioni vengano preservate.</span><span class="sxs-lookup"><span data-stu-id="24226-128">The <xref:System.DateTime> objects are then serialized in such a way that this information is preserved.</span></span> <span data-ttu-id="24226-129">Si tratta del comportamento predefinito, consigliato per tutte le nuove applicazioni che non comunicano con le versioni precedenti del framework.</span><span class="sxs-lookup"><span data-stu-id="24226-129">This is the default behavior and is the recommended behavior for all new applications that do not communicate with older versions of the framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24226-130">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="24226-130">See also</span></span>

- <xref:System.DateTime>
- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="24226-131">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="24226-131">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="24226-132">\<Elemento> schemaImporterExtensions</span><span class="sxs-lookup"><span data-stu-id="24226-132">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)
- [<span data-ttu-id="24226-133">\<aggiungere> elemento per \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="24226-133">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)
- [<span data-ttu-id="24226-134">\<System. XML. Serialization> elemento</span><span class="sxs-lookup"><span data-stu-id="24226-134">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
