---
title: Elemento <system.xml.serialization>
description: Questo articolo descrive l'elemento <System. XML. Serialization>, che è l'elemento di livello principale per il controllo della serializzazione XML.
ms.date: 03/30/2017
helpviewer_keywords:
- system.xml.serialization element
- XML serialization, configuration
- <system.xml.serialization> element
ms.assetid: 3ce45919-388a-418c-8968-6df0372c73ec
ms.openlocfilehash: 1e66220004d561f937d03c506e6f30db4ccc635b
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83380121"
---
# <a name="systemxmlserialization-element"></a><span data-ttu-id="b3e80-103">\<Elemento system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="b3e80-103">\<system.xml.serialization> Element</span></span>

<span data-ttu-id="b3e80-104">L'elemento di primo livello per il controllo della serializzazione XML.</span><span class="sxs-lookup"><span data-stu-id="b3e80-104">The top-level element for controlling XML serialization.</span></span> <span data-ttu-id="b3e80-105">Per altre informazioni sui file di configurazione, vedere [Schema dei file di configurazione](../../../docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="b3e80-105">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>

<span data-ttu-id="b3e80-106">\<> di configurazione </span><span class="sxs-lookup"><span data-stu-id="b3e80-106">\<configuration></span></span>\
<span data-ttu-id="b3e80-107">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="b3e80-107">\<system.xml.serialization></span></span>

## <a name="syntax"></a><span data-ttu-id="b3e80-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b3e80-108">Syntax</span></span>

```xml
<system.xml.serialization>
</system.xml.serialization>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b3e80-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b3e80-109">Attributes and Elements</span></span>

<span data-ttu-id="b3e80-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b3e80-110">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="b3e80-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="b3e80-111">Attributes</span></span>

<span data-ttu-id="b3e80-112">No.</span><span class="sxs-lookup"><span data-stu-id="b3e80-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b3e80-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b3e80-113">Child Elements</span></span>

|<span data-ttu-id="b3e80-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="b3e80-114">Element</span></span>|<span data-ttu-id="b3e80-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b3e80-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b3e80-116">\<Elemento> dateTimeSerialization</span><span class="sxs-lookup"><span data-stu-id="b3e80-116">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)|<span data-ttu-id="b3e80-117">Determina la modalità di serializzazione degli oggetti <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="b3e80-117">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>|
|[<span data-ttu-id="b3e80-118">\<Elemento> schemaImporterExtensions</span><span class="sxs-lookup"><span data-stu-id="b3e80-118">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)|<span data-ttu-id="b3e80-119">Contiene tipi utilizzati da <xref:System.Xml.Serialization.XmlSchemaImporter> per l'esecuzione del mapping dei tipi XSD ai tipi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b3e80-119">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET Framework types.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="b3e80-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b3e80-120">Parent Elements</span></span>

|<span data-ttu-id="b3e80-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="b3e80-121">Element</span></span>|<span data-ttu-id="b3e80-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b3e80-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b3e80-123">\<Configuration>-elemento</span><span class="sxs-lookup"><span data-stu-id="b3e80-123">\<configuration> Element</span></span>](../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="b3e80-124">Elemento radice in ogni file di configurazione utilizzato dal Common Language Runtime e dalle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b3e80-124">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|

## <a name="example"></a><span data-ttu-id="b3e80-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="b3e80-125">Example</span></span>

<span data-ttu-id="b3e80-126">Nell'esempio di codice riportato di seguito viene illustrato come specificare la modalità di serializzazione di un oggetto <xref:System.DateTime> e l'aggiunta dei tipi usati da <xref:System.Xml.Serialization.XmlSchemaImporter> in caso di esecuzione del mapping di tipi XSD ai tipi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b3e80-126">The following code example illustrates how to specify the serialization mode of a <xref:System.DateTime> object, and the addition of types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET Framework types.</span></span>

```xml
<system.xml.serialization>
    <xmlSerializer checkDeserializeAdvances="false" />
    <dateTimeSerialization mode = "Local" />
    <schemaImporterExtensions>
        <add
        name = "MobileCapabilities"
        type = "System.Web.Mobile.MobileCapabilities,
        System.Web.Mobile, Version=2.0.0.0, Culture=neutral,
        PublicKeyToken=b03f5f6f11d40a3a" />
    </schemaImporterExtensions>
</system.xml.serialization>
```

## <a name="see-also"></a><span data-ttu-id="b3e80-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3e80-127">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="b3e80-128">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="b3e80-128">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="b3e80-129">\<Elemento> dateTimeSerialization</span><span class="sxs-lookup"><span data-stu-id="b3e80-129">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)
- [<span data-ttu-id="b3e80-130">\<Elemento> schemaImporterExtensions</span><span class="sxs-lookup"><span data-stu-id="b3e80-130">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)
- [<span data-ttu-id="b3e80-131">\<aggiungere> elemento per \< schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="b3e80-131">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)
