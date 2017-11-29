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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b3cc5e75cded5d468323a2b953bc61271f89e3e8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltschemaimporterextensionsgt-element"></a><span data-ttu-id="3ecb1-102">Elemento &lt;schemaImporterExtensions&gt;</span><span class="sxs-lookup"><span data-stu-id="3ecb1-102">&lt;schemaImporterExtensions&gt; Element</span></span>
<span data-ttu-id="3ecb1-103">Contiene tipi usati da <xref:System.Xml.Serialization.XmlSchemaImporter> per l'esecuzione del mapping dei tipi XSD ai tipi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3ecb1-103">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET Framework types.</span></span> <span data-ttu-id="3ecb1-104">Per altre informazioni sui file di configurazione, vedere [Schema dei file di configurazione](../../../docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="3ecb1-104">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ecb1-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3ecb1-105">Syntax</span></span>  
  
```xml  
<schemaImporterExtensions>  
    <!-- Add types -->  
</SchemaImporterExtension>  
```  
  
## <a name="child-elements"></a><span data-ttu-id="3ecb1-106">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3ecb1-106">Child Elements</span></span>  
  
|<span data-ttu-id="3ecb1-107">Elemento</span><span class="sxs-lookup"><span data-stu-id="3ecb1-107">Element</span></span>|<span data-ttu-id="3ecb1-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3ecb1-108">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3ecb1-109">Elemento \<add> per \<xmlSchemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="3ecb1-109">\<add> Element for \<xmlSchemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-xmlschemaimporterextensions.md)|<span data-ttu-id="3ecb1-110">Aggiunge tipi usati da <xref:System.Xml.Serialization.XmlSchemaImporter> per creare i mapping.</span><span class="sxs-lookup"><span data-stu-id="3ecb1-110">Adds types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> to create mappings.</span></span>|  
  
## <a name="parent-elements"></a><span data-ttu-id="3ecb1-111">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3ecb1-111">Parent Elements</span></span>  
  
|<span data-ttu-id="3ecb1-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="3ecb1-112">Element</span></span>|<span data-ttu-id="3ecb1-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3ecb1-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3ecb1-114">Elemento \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="3ecb1-114">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)|<span data-ttu-id="3ecb1-115">L'elemento di primo livello per il controllo della serializzazione XML.</span><span class="sxs-lookup"><span data-stu-id="3ecb1-115">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3ecb1-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="3ecb1-116">Example</span></span>  
 <span data-ttu-id="3ecb1-117">Nell'esempio di codice riportato di seguito viene illustrato come aggiungere tipi utilizzati da <xref:System.Xml.Serialization.XmlSchemaImporter> in caso di esecuzione del mapping di tipi XSD ai tipi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3ecb1-117">The following code example illustrates how to add types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET Framework types.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3ecb1-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ecb1-118">See Also</span></span>  
 <xref:System.Xml.Serialization.XmlSchemaImporter>  
 <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>  
 [<span data-ttu-id="3ecb1-119">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="3ecb1-119">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="3ecb1-120">Elemento \<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="3ecb1-120">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)  
 [<span data-ttu-id="3ecb1-121">Elemento \<add> per \<xmlSchemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="3ecb1-121">\<add> Element for \<xmlSchemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-xmlschemaimporterextensions.md)  
 [<span data-ttu-id="3ecb1-122">Elemento \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="3ecb1-122">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
