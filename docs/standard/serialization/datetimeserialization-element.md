---
title: Elemento &lt;dateTimeSerialization&gt;
ms.date: 03/30/2017
helpviewer_keywords:
- dateTimeSerialization element
- XML serialization, configuration
- <dateTimeSerialization> element
ms.assetid: 90fda55c-7730-41e9-bc4b-6423a4b920af
ms.openlocfilehash: cd275cdbc51c86b1d774058db839c38349b319a6
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2018
ms.locfileid: "44706806"
---
# <a name="ltdatetimeserializationgt-element"></a><span data-ttu-id="b745a-102">Elemento &lt;dateTimeSerialization&gt;</span><span class="sxs-lookup"><span data-stu-id="b745a-102">&lt;dateTimeSerialization&gt; Element</span></span>
<span data-ttu-id="b745a-103">Determina la modalità di serializzazione degli oggetti <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="b745a-103">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>  
  
 <span data-ttu-id="b745a-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b745a-104">\<configuration></span></span>  
<span data-ttu-id="b745a-105">\<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="b745a-105">\<dateTimeSerialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b745a-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b745a-106">Syntax</span></span>  
  
```xml  
<dateTimeSerialization  
    mode = "Roundtrip" | "Local"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b745a-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b745a-107">Attributes and Elements</span></span>  
 <span data-ttu-id="b745a-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b745a-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b745a-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="b745a-109">Attributes</span></span>  
  
|<span data-ttu-id="b745a-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="b745a-110">Attributes</span></span>|<span data-ttu-id="b745a-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b745a-111">Description</span></span>|  
|----------------|-----------------|  
|`mode`|<span data-ttu-id="b745a-112">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b745a-112">Optional.</span></span> <span data-ttu-id="b745a-113">Specifica la modalità di serializzazione.</span><span class="sxs-lookup"><span data-stu-id="b745a-113">Specifies the serialization mode.</span></span> <span data-ttu-id="b745a-114">Impostarlo a uno dei valori di <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>.</span><span class="sxs-lookup"><span data-stu-id="b745a-114">Set to one of the <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> values.</span></span> <span data-ttu-id="b745a-115">Il valore predefinito è **RoundTrip**.</span><span class="sxs-lookup"><span data-stu-id="b745a-115">The default is **RoundTrip**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b745a-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b745a-116">Child Elements</span></span>  
 <span data-ttu-id="b745a-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="b745a-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b745a-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b745a-118">Parent Elements</span></span>  
  
|<span data-ttu-id="b745a-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="b745a-119">Element</span></span>|<span data-ttu-id="b745a-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b745a-120">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b745a-121">system.xml.serialization</span><span class="sxs-lookup"><span data-stu-id="b745a-121">system.xml.serialization</span></span>|<span data-ttu-id="b745a-122">L'elemento di primo livello per il controllo della serializzazione XML.</span><span class="sxs-lookup"><span data-stu-id="b745a-122">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b745a-123">Note</span><span class="sxs-lookup"><span data-stu-id="b745a-123">Remarks</span></span>  
 <span data-ttu-id="b745a-124">Nelle versioni 1.0, 1.1, 2.0 e successive di .NET Framework, se la proprietà è impostata su **Local**, gli oggetti <xref:System.DateTime> vengono sempre formattati come ora locale.</span><span class="sxs-lookup"><span data-stu-id="b745a-124">In versions 1.0, 1.1, 2.0 and later versions of the .NET Framework, when this property is set to **Local**, <xref:System.DateTime> objects are always formatted as the local time.</span></span> <span data-ttu-id="b745a-125">Vale a dire che le informazioni relative al fuso orario locale vengono sempre incluse tra dati serializzati.</span><span class="sxs-lookup"><span data-stu-id="b745a-125">That is, local time zone information is always included with the serialized data.</span></span> <span data-ttu-id="b745a-126">Impostare questa proprietà su **Local** per garantire la compatibilità con le versioni precedenti di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b745a-126">Set this property to **Local** to ensure compatibility with older versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="b745a-127">Nella versione 2.0 e nelle versioni successive di .NET Framework in cui la proprietà è impostata su **Roundtrip**, gli oggetti <xref:System.DateTime> vengono esaminati in modo da determinare se si trovano nel fuso orario locale, nel fuso orario UTC o in un fuso orario non specificato.</span><span class="sxs-lookup"><span data-stu-id="b745a-127">In version 2.0 and later versions of the .NET Framework that have this property set to **Roundtrip**, <xref:System.DateTime> objects are examined to determine whether they are in the local, UTC, or an unspecified time zone.</span></span> <span data-ttu-id="b745a-128">Gli oggetti <xref:System.DateTime> vengono quindi serializzati in modo tale che tali informazioni vengano preservate.</span><span class="sxs-lookup"><span data-stu-id="b745a-128">The <xref:System.DateTime> objects are then serialized in such a way that this information is preserved.</span></span> <span data-ttu-id="b745a-129">Si tratta del comportamento predefinito, consigliato per tutte le nuove applicazioni che non comunicano con le versioni precedenti del framework.</span><span class="sxs-lookup"><span data-stu-id="b745a-129">This is the default behavior and is the recommended behavior for all new applications that do not communicate with older versions of the framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b745a-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b745a-130">See also</span></span>

- <xref:System.DateTime>  
- <xref:System.Xml.Serialization.XmlSchemaImporter>  
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>  
- [<span data-ttu-id="b745a-131">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="b745a-131">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)  
- [<span data-ttu-id="b745a-132">Elemento \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="b745a-132">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)  
- [<span data-ttu-id="b745a-133">\<aggiungere > (elemento) per \<schemaImporterExtensions ></span><span class="sxs-lookup"><span data-stu-id="b745a-133">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)  
- [<span data-ttu-id="b745a-134">Elemento \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="b745a-134">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
