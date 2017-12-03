---
title: Elemento &lt;schemaImporterExtensions&gt;
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML serialization, configuration
- schemaImporterExtensions element
- <schemaImporterExtensions> element
ms.assetid: 465ef2a0-f909-4ac1-9a56-0ead5c849698
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0296b207af0ed439c90374eb6db21fe11e00dd42
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltschemaimporterextensionsgt-element"></a><span data-ttu-id="e8b7d-102">Elemento &lt;schemaImporterExtensions&gt;</span><span class="sxs-lookup"><span data-stu-id="e8b7d-102">&lt;schemaImporterExtensions&gt; Element</span></span>
<span data-ttu-id="e8b7d-103">Contiene tipi usati da <xref:System.Xml.Serialization.XmlSchemaImporter> per l'esecuzione del mapping dei tipi XSD ai tipi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e8b7d-103">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET Framework types.</span></span> <span data-ttu-id="e8b7d-104">Per altre informazioni sui file di configurazione, vedere [Schema dei file di configurazione](../../../docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="e8b7d-104">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8b7d-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e8b7d-105">Syntax</span></span>  
  
```xml  
<schemaImporterExtensions>  
    <!-- Add types -->  
</SchemaImporterExtension>  
```  
  
## <a name="child-elements"></a><span data-ttu-id="e8b7d-106">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e8b7d-106">Child Elements</span></span>  
  
|<span data-ttu-id="e8b7d-107">Elemento</span><span class="sxs-lookup"><span data-stu-id="e8b7d-107">Element</span></span>|<span data-ttu-id="e8b7d-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e8b7d-108">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e8b7d-109">Elemento \<add> per \<xmlSchemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="e8b7d-109">\<add> Element for \<xmlSchemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-xmlschemaimporterextensions.md)|<span data-ttu-id="e8b7d-110">Aggiunge tipi usati da <xref:System.Xml.Serialization.XmlSchemaImporter> per creare i mapping.</span><span class="sxs-lookup"><span data-stu-id="e8b7d-110">Adds types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> to create mappings.</span></span>|  
  
## <a name="parent-elements"></a><span data-ttu-id="e8b7d-111">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e8b7d-111">Parent Elements</span></span>  
  
|<span data-ttu-id="e8b7d-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="e8b7d-112">Element</span></span>|<span data-ttu-id="e8b7d-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e8b7d-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e8b7d-114">Elemento \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="e8b7d-114">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)|<span data-ttu-id="e8b7d-115">L'elemento di primo livello per il controllo della serializzazione XML.</span><span class="sxs-lookup"><span data-stu-id="e8b7d-115">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e8b7d-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="e8b7d-116">Example</span></span>  
 <span data-ttu-id="e8b7d-117">Nell'esempio di codice riportato di seguito viene illustrato come aggiungere tipi utilizzati da <xref:System.Xml.Serialization.XmlSchemaImporter> in caso di esecuzione del mapping di tipi XSD ai tipi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e8b7d-117">The following code example illustrates how to add types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET Framework types.</span></span>  
  
```xml  
<system.xml.serialization>  
    <schemaImporterExtensions>  
        <add name = "MobileCapabilities" type =   
        "System.Web.Mobile.MobileCapabilities,   
        System.Web.Mobile, Version - 2.0.0.0, Culture = neutral,   
        PublicKeyToken = b03f5f6f11d40a3a" />  
    </schemaImporterExtensions>  
/system.sxml.serializaiton>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e8b7d-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8b7d-118">See Also</span></span>  
 <xref:System.Xml.Serialization.XmlSchemaImporter>  
 <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>  
 [<span data-ttu-id="e8b7d-119">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="e8b7d-119">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="e8b7d-120">Elemento \<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="e8b7d-120">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)  
 [<span data-ttu-id="e8b7d-121">Elemento \<add> per \<xmlSchemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="e8b7d-121">\<add> Element for \<xmlSchemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-xmlschemaimporterextensions.md)  
 [<span data-ttu-id="e8b7d-122">Elemento \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="e8b7d-122">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
