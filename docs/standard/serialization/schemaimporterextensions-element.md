---
title: <schemaImporterExtensions> Elemento
description: L' <schemaImporterExtensions> elemento contiene i tipi utilizzati da XmlSchemaImporter per il mapping dei tipi XSD ai tipi .NET Framework.
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- schemaImporterExtensions element
- <schemaImporterExtensions> element
ms.assetid: 465ef2a0-f909-4ac1-9a56-0ead5c849698
ms.openlocfilehash: c46c5cb6e01463723f0f2ce3873fb4a6ec0b4e60
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84278402"
---
# <a name="schemaimporterextensions-element"></a><span data-ttu-id="ff100-103">\<schemaImporterExtensions> Elemento</span><span class="sxs-lookup"><span data-stu-id="ff100-103">\<schemaImporterExtensions> Element</span></span>
<span data-ttu-id="ff100-104">Contiene tipi utilizzati da <xref:System.Xml.Serialization.XmlSchemaImporter> per l'esecuzione del mapping dei tipi XSD ai tipi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ff100-104">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET Framework types.</span></span> <span data-ttu-id="ff100-105">Per altre informazioni sui file di configurazione, vedere [Schema dei file di configurazione](../../framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="ff100-105">For more information about configuration files, see [Configuration File Schema](../../framework/configure-apps/file-schema/index.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff100-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ff100-106">Syntax</span></span>  
  
```xml  
<schemaImporterExtensions>  
    <!-- Add types -->  
</schemaImporterExtensions>  
```  
  
## <a name="child-elements"></a><span data-ttu-id="ff100-107">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ff100-107">Child Elements</span></span>  
  
|<span data-ttu-id="ff100-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="ff100-108">Element</span></span>|<span data-ttu-id="ff100-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ff100-109">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ff100-110">\<add>Elemento per\<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="ff100-110">\<add> Element for \<schemaImporterExtensions></span></span>](add-element-for-schemaimporterextensions.md)|<span data-ttu-id="ff100-111">Aggiunge tipi usati da <xref:System.Xml.Serialization.XmlSchemaImporter> per creare i mapping.</span><span class="sxs-lookup"><span data-stu-id="ff100-111">Adds types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> to create mappings.</span></span>|  
  
## <a name="parent-elements"></a><span data-ttu-id="ff100-112">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ff100-112">Parent Elements</span></span>  
  
|<span data-ttu-id="ff100-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="ff100-113">Element</span></span>|<span data-ttu-id="ff100-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ff100-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ff100-115">\<system.xml.serialization>Elemento</span><span class="sxs-lookup"><span data-stu-id="ff100-115">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)|<span data-ttu-id="ff100-116">L'elemento di primo livello per il controllo della serializzazione XML.</span><span class="sxs-lookup"><span data-stu-id="ff100-116">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ff100-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="ff100-117">Example</span></span>  
 <span data-ttu-id="ff100-118">Nell'esempio di codice riportato di seguito viene illustrato come aggiungere tipi utilizzati da <xref:System.Xml.Serialization.XmlSchemaImporter> in caso di esecuzione del mapping di tipi XSD ai tipi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ff100-118">The following code example illustrates how to add types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET Framework types.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ff100-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff100-119">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="ff100-120">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="ff100-120">Configuration File Schema</span></span>](../../framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="ff100-121">\<dateTimeSerialization>Elemento</span><span class="sxs-lookup"><span data-stu-id="ff100-121">\<dateTimeSerialization> Element</span></span>](datetimeserialization-element.md)
- [<span data-ttu-id="ff100-122">\<add>Elemento per\<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="ff100-122">\<add> Element for \<schemaImporterExtensions></span></span>](add-element-for-schemaimporterextensions.md)
- [<span data-ttu-id="ff100-123">\<system.xml.serialization>Elemento</span><span class="sxs-lookup"><span data-stu-id="ff100-123">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)
