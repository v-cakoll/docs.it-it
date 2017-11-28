---
title: Elemento &lt;system.xml.serialization&gt;
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- system.xml.serialization element
- XML serialization, configuration
- <system.xml.serialization> element
ms.assetid: 3ce45919-388a-418c-8968-6df0372c73ec
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: cfc2b38eba68a8c7f9ddab4a6ee941f6faee7c02
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltsystemxmlserializationgt-element"></a><span data-ttu-id="344c1-102">Elemento &lt;system.xml.serialization&gt;</span><span class="sxs-lookup"><span data-stu-id="344c1-102">&lt;system.xml.serialization&gt; Element</span></span>
<span data-ttu-id="344c1-103">L'elemento di primo livello per il controllo della serializzazione XML.</span><span class="sxs-lookup"><span data-stu-id="344c1-103">The top-level element for controlling XML serialization.</span></span> <span data-ttu-id="344c1-104">Per altre informazioni sui file di configurazione, vedere [Schema dei file di configurazione](../../../docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="344c1-104">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
 <span data-ttu-id="344c1-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="344c1-105">\<configuration></span></span>  
<span data-ttu-id="344c1-106">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="344c1-106">\<system.xml.serialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="344c1-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="344c1-107">Syntax</span></span>  
  
```xml  
<system.xml.serialization>  
</system.xml.serialization>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="344c1-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="344c1-108">Attributes and Elements</span></span>  
 <span data-ttu-id="344c1-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="344c1-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="344c1-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="344c1-110">Attributes</span></span>  
 <span data-ttu-id="344c1-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="344c1-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="344c1-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="344c1-112">Child Elements</span></span>  
  
|<span data-ttu-id="344c1-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="344c1-113">Element</span></span>|<span data-ttu-id="344c1-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="344c1-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="344c1-115">Elemento \<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="344c1-115">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)|<span data-ttu-id="344c1-116">Determina la modalità di serializzazione degli oggetti <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="344c1-116">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>|  
|[<span data-ttu-id="344c1-117">Elemento \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="344c1-117">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)|<span data-ttu-id="344c1-118">Contiene tipi usati da <xref:System.Xml.Serialization.XmlSchemaImporter> per l'esecuzione del mapping dei tipi XSD ai tipi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="344c1-118">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET Framework types.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="344c1-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="344c1-119">Parent Elements</span></span>  
  
|<span data-ttu-id="344c1-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="344c1-120">Element</span></span>|<span data-ttu-id="344c1-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="344c1-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="344c1-122">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="344c1-122">\<configuration> Element</span></span>](../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="344c1-123">Elemento radice in ogni file di configurazione usato dal Common Language Runtime e dalle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="344c1-123">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="344c1-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="344c1-124">Example</span></span>  
 <span data-ttu-id="344c1-125">Nell'esempio di codice riportato di seguito viene illustrato come specificare la modalità di serializzazione di un oggetto <xref:System.DateTime> e l'aggiunta dei tipi usati da <xref:System.Xml.Serialization.XmlSchemaImporter> in caso di esecuzione del mapping di tipi XSD ai tipi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="344c1-125">The following code example illustrates how to specify the serialization mode of a <xref:System.DateTime> object, and the addition of types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET Framework types.</span></span>  
  
```xml  
<system.xml.serialization>  
    <xmlSerializer checkDeserializeAdvances="false" />  
    <dateTimeSerialization mode = "Local" />  
    <schemaImporterExtensions>  
        <add   
        name = "MobileCapabilities"   
        type = "System.Web.Mobile.MobileCapabilities,   
        System.Web.Mobile, Version - 2.0.0.0, Culture = neuutral,   
        PublicKeyToken = b03f5f6f11d40a3a" />  
    </schemaImporterExtensions>  
</system.sxml.serialization>  
```  
  
## <a name="see-also"></a><span data-ttu-id="344c1-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="344c1-126">See Also</span></span>  
 <xref:System.Xml.Serialization.XmlSchemaImporter>  
 <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>  
 [<span data-ttu-id="344c1-127">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="344c1-127">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="344c1-128">Elemento \<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="344c1-128">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)  
 [<span data-ttu-id="344c1-129">Elemento \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="344c1-129">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)  
 [<span data-ttu-id="344c1-130">Elemento \<add> per \<xmlSchemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="344c1-130">\<add> Element for \<xmlSchemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-xmlschemaimporterextensions.md)
