---
title: Elemento <system.xml.serialization>
description: Questo articolo descrive l'elemento < System. XML. Serialization >, che è l'elemento di livello principale per il controllo della serializzazione XML.
ms.date: 03/30/2017
helpviewer_keywords:
- system.xml.serialization element
- XML serialization, configuration
- <system.xml.serialization> element
ms.assetid: 3ce45919-388a-418c-8968-6df0372c73ec
ms.openlocfilehash: f69e80592e9321de64421b977a63b83d8be2ad9e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "84289486"
---
# <a name="systemxmlserialization-element"></a><span data-ttu-id="6ab14-103">\<system.xml.serialization> Elemento</span><span class="sxs-lookup"><span data-stu-id="6ab14-103">\<system.xml.serialization> Element</span></span>

<span data-ttu-id="6ab14-104">L'elemento di primo livello per il controllo della serializzazione XML.</span><span class="sxs-lookup"><span data-stu-id="6ab14-104">The top-level element for controlling XML serialization.</span></span> <span data-ttu-id="6ab14-105">Per altre informazioni sui file di configurazione, vedere [Schema dei file di configurazione](../../framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="6ab14-105">For more information about configuration files, see [Configuration File Schema](../../framework/configure-apps/file-schema/index.md).</span></span>

\<configuration>\
\<system.xml.serialization>

## <a name="syntax"></a><span data-ttu-id="6ab14-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6ab14-106">Syntax</span></span>

```xml
<system.xml.serialization>
</system.xml.serialization>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6ab14-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6ab14-107">Attributes and Elements</span></span>

<span data-ttu-id="6ab14-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6ab14-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="6ab14-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="6ab14-109">Attributes</span></span>

<span data-ttu-id="6ab14-110">No.</span><span class="sxs-lookup"><span data-stu-id="6ab14-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6ab14-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6ab14-111">Child Elements</span></span>

|<span data-ttu-id="6ab14-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="6ab14-112">Element</span></span>|<span data-ttu-id="6ab14-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6ab14-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6ab14-114">\<dateTimeSerialization>Elemento</span><span class="sxs-lookup"><span data-stu-id="6ab14-114">\<dateTimeSerialization> Element</span></span>](datetimeserialization-element.md)|<span data-ttu-id="6ab14-115">Determina la modalità di serializzazione degli oggetti <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="6ab14-115">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>|
|[<span data-ttu-id="6ab14-116">\<schemaImporterExtensions>Elemento</span><span class="sxs-lookup"><span data-stu-id="6ab14-116">\<schemaImporterExtensions> Element</span></span>](schemaimporterextensions-element.md)|<span data-ttu-id="6ab14-117">Contiene tipi utilizzati da <xref:System.Xml.Serialization.XmlSchemaImporter> per l'esecuzione del mapping dei tipi XSD ai tipi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6ab14-117">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET Framework types.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="6ab14-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6ab14-118">Parent Elements</span></span>

|<span data-ttu-id="6ab14-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="6ab14-119">Element</span></span>|<span data-ttu-id="6ab14-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6ab14-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6ab14-121">\<configuration>Elemento</span><span class="sxs-lookup"><span data-stu-id="6ab14-121">\<configuration> Element</span></span>](../../framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="6ab14-122">Elemento radice in ogni file di configurazione utilizzato dal Common Language Runtime e dalle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6ab14-122">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|

## <a name="example"></a><span data-ttu-id="6ab14-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="6ab14-123">Example</span></span>

<span data-ttu-id="6ab14-124">Nell'esempio di codice riportato di seguito viene illustrato come specificare la modalità di serializzazione di un oggetto <xref:System.DateTime> e l'aggiunta dei tipi usati da <xref:System.Xml.Serialization.XmlSchemaImporter> in caso di esecuzione del mapping di tipi XSD ai tipi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6ab14-124">The following code example illustrates how to specify the serialization mode of a <xref:System.DateTime> object, and the addition of types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET Framework types.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="6ab14-125">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="6ab14-125">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="6ab14-126">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="6ab14-126">Configuration File Schema</span></span>](../../framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="6ab14-127">\<dateTimeSerialization>Elemento</span><span class="sxs-lookup"><span data-stu-id="6ab14-127">\<dateTimeSerialization> Element</span></span>](datetimeserialization-element.md)
- [<span data-ttu-id="6ab14-128">\<schemaImporterExtensions>Elemento</span><span class="sxs-lookup"><span data-stu-id="6ab14-128">\<schemaImporterExtensions> Element</span></span>](schemaimporterextensions-element.md)
- [<span data-ttu-id="6ab14-129">\<add>Elemento per\<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="6ab14-129">\<add> Element for \<schemaImporterExtensions></span></span>](add-element-for-schemaimporterextensions.md)
