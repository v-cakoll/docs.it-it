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
# <a name="datetimeserialization-element"></a><span data-ttu-id="a6451-102">\<elemento > dateTimeSerialization</span><span class="sxs-lookup"><span data-stu-id="a6451-102">\<dateTimeSerialization> Element</span></span>
<span data-ttu-id="a6451-103">Determina la modalità di serializzazione degli oggetti <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="a6451-103">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>  
  
 <span data-ttu-id="a6451-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a6451-104">\<configuration></span></span>  
<span data-ttu-id="a6451-105">\<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="a6451-105">\<dateTimeSerialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6451-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a6451-106">Syntax</span></span>  
  
```xml  
<dateTimeSerialization  
    mode = "Roundtrip|Local"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a6451-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a6451-107">Attributes and Elements</span></span>  
 <span data-ttu-id="a6451-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a6451-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a6451-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="a6451-109">Attributes</span></span>  
  
|<span data-ttu-id="a6451-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="a6451-110">Attributes</span></span>|<span data-ttu-id="a6451-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a6451-111">Description</span></span>|  
|----------------|-----------------|  
|`mode`|<span data-ttu-id="a6451-112">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="a6451-112">Optional.</span></span> <span data-ttu-id="a6451-113">Specifica la modalità di serializzazione.</span><span class="sxs-lookup"><span data-stu-id="a6451-113">Specifies the serialization mode.</span></span> <span data-ttu-id="a6451-114">Impostarlo a uno dei valori di <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>.</span><span class="sxs-lookup"><span data-stu-id="a6451-114">Set to one of the <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> values.</span></span> <span data-ttu-id="a6451-115">Il valore predefinito è **RoundTrip**.</span><span class="sxs-lookup"><span data-stu-id="a6451-115">The default is **RoundTrip**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a6451-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a6451-116">Child Elements</span></span>  
 <span data-ttu-id="a6451-117">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="a6451-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a6451-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a6451-118">Parent Elements</span></span>  
  
|<span data-ttu-id="a6451-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="a6451-119">Element</span></span>|<span data-ttu-id="a6451-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a6451-120">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a6451-121">system.xml.serialization</span><span class="sxs-lookup"><span data-stu-id="a6451-121">system.xml.serialization</span></span>|<span data-ttu-id="a6451-122">L'elemento di primo livello per il controllo della serializzazione XML.</span><span class="sxs-lookup"><span data-stu-id="a6451-122">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6451-123">Note</span><span class="sxs-lookup"><span data-stu-id="a6451-123">Remarks</span></span>  
 <span data-ttu-id="a6451-124">Nelle versioni 1.0, 1.1, 2.0 e successive di .NET Framework, se la proprietà è impostata su **Local**, gli oggetti <xref:System.DateTime> vengono sempre formattati come ora locale.</span><span class="sxs-lookup"><span data-stu-id="a6451-124">In versions 1.0, 1.1, 2.0 and later versions of the .NET Framework, when this property is set to **Local**, <xref:System.DateTime> objects are always formatted as the local time.</span></span> <span data-ttu-id="a6451-125">Vale a dire che le informazioni relative al fuso orario locale vengono sempre incluse tra dati serializzati.</span><span class="sxs-lookup"><span data-stu-id="a6451-125">That is, local time zone information is always included with the serialized data.</span></span> <span data-ttu-id="a6451-126">Impostare questa proprietà su **Local** per garantire la compatibilità con le versioni precedenti di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a6451-126">Set this property to **Local** to ensure compatibility with older versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="a6451-127">Nella versione 2.0 e nelle versioni successive di .NET Framework in cui la proprietà è impostata su **Roundtrip**, gli oggetti <xref:System.DateTime> vengono esaminati in modo da determinare se si trovano nel fuso orario locale, nel fuso orario UTC o in un fuso orario non specificato.</span><span class="sxs-lookup"><span data-stu-id="a6451-127">In version 2.0 and later versions of the .NET Framework that have this property set to **Roundtrip**, <xref:System.DateTime> objects are examined to determine whether they are in the local, UTC, or an unspecified time zone.</span></span> <span data-ttu-id="a6451-128">Gli oggetti <xref:System.DateTime> vengono quindi serializzati in modo tale che tali informazioni vengano preservate.</span><span class="sxs-lookup"><span data-stu-id="a6451-128">The <xref:System.DateTime> objects are then serialized in such a way that this information is preserved.</span></span> <span data-ttu-id="a6451-129">Si tratta del comportamento predefinito, consigliato per tutte le nuove applicazioni che non comunicano con le versioni precedenti del framework.</span><span class="sxs-lookup"><span data-stu-id="a6451-129">This is the default behavior and is the recommended behavior for all new applications that do not communicate with older versions of the framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6451-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6451-130">See also</span></span>

- <xref:System.DateTime>
- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="a6451-131">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="a6451-131">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="a6451-132">Elemento \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="a6451-132">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)
- [<span data-ttu-id="a6451-133">\<aggiungere > elemento per \<schemaImporterExtensions ></span><span class="sxs-lookup"><span data-stu-id="a6451-133">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)
- [<span data-ttu-id="a6451-134">Elemento \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="a6451-134">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
