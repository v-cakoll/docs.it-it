---
title: <schemaImporterExtensions> Elemento
description: L' <schemaImporterExtensions> elemento contiene i tipi utilizzati da XmlSchemaImporter per il mapping dei tipi XSD ai tipi .NET Framework.
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- schemaImporterExtensions element
- <schemaImporterExtensions> element
ms.assetid: 465ef2a0-f909-4ac1-9a56-0ead5c849698
ms.openlocfilehash: 5b9820ccdf2c75bed9beda72358c4c4d82ff9ff7
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379795"
---
# <a name="schemaimporterextensions-element"></a><span data-ttu-id="ae8e2-103">\<Elemento schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="ae8e2-103">\<schemaImporterExtensions> Element</span></span>
<span data-ttu-id="ae8e2-104">Contiene tipi utilizzati da <xref:System.Xml.Serialization.XmlSchemaImporter> per l'esecuzione del mapping dei tipi XSD ai tipi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ae8e2-104">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET Framework types.</span></span> <span data-ttu-id="ae8e2-105">Per altre informazioni sui file di configurazione, vedere [Schema dei file di configurazione](../../../docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="ae8e2-105">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae8e2-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ae8e2-106">Syntax</span></span>  
  
```xml  
<schemaImporterExtensions>  
    <!-- Add types -->  
</schemaImporterExtensions>  
```  
  
## <a name="child-elements"></a><span data-ttu-id="ae8e2-107">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ae8e2-107">Child Elements</span></span>  
  
|<span data-ttu-id="ae8e2-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="ae8e2-108">Element</span></span>|<span data-ttu-id="ae8e2-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ae8e2-109">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ae8e2-110">\<aggiungere> elemento per \< schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="ae8e2-110">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)|<span data-ttu-id="ae8e2-111">Aggiunge tipi usati da <xref:System.Xml.Serialization.XmlSchemaImporter> per creare i mapping.</span><span class="sxs-lookup"><span data-stu-id="ae8e2-111">Adds types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> to create mappings.</span></span>|  
  
## <a name="parent-elements"></a><span data-ttu-id="ae8e2-112">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ae8e2-112">Parent Elements</span></span>  
  
|<span data-ttu-id="ae8e2-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="ae8e2-113">Element</span></span>|<span data-ttu-id="ae8e2-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ae8e2-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ae8e2-115">\<System. XML. Serialization> elemento</span><span class="sxs-lookup"><span data-stu-id="ae8e2-115">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)|<span data-ttu-id="ae8e2-116">L'elemento di primo livello per il controllo della serializzazione XML.</span><span class="sxs-lookup"><span data-stu-id="ae8e2-116">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ae8e2-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="ae8e2-117">Example</span></span>  
 <span data-ttu-id="ae8e2-118">Nell'esempio di codice riportato di seguito viene illustrato come aggiungere tipi utilizzati da <xref:System.Xml.Serialization.XmlSchemaImporter> in caso di esecuzione del mapping di tipi XSD ai tipi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ae8e2-118">The following code example illustrates how to add types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET Framework types.</span></span>  
  
```xml  
<system.xml.serialization>  
    <schemaImporterExtensions>  
        <add name = "MobileCapabilities" type =
        "System.Web.Mobile.MobileCapabilities,
        System.Web.Mobile, Version - 2.0.0.0, Culture = neutral,
        PublicKeyToken = b03f5f6f11d40a3a" />  
    </schemaImporterExtensions>  
</system.xml.serialization>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ae8e2-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae8e2-119">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="ae8e2-120">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="ae8e2-120">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="ae8e2-121">\<Elemento> dateTimeSerialization</span><span class="sxs-lookup"><span data-stu-id="ae8e2-121">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)
- [<span data-ttu-id="ae8e2-122">\<aggiungere> elemento per \< schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="ae8e2-122">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)
- [<span data-ttu-id="ae8e2-123">\<System. XML. Serialization> elemento</span><span class="sxs-lookup"><span data-stu-id="ae8e2-123">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
