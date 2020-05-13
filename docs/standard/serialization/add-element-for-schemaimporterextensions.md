---
title: Elemento <add> per <schemaImporterExtensions>
description: L' <add> elemento aggiunge i tipi utilizzati dalla classe XmlSchemaImporter per il mapping dei tipi XSD ai tipi .NET Framework.
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- <add> element for <schemaImporterExtensions> element
ms.assetid: c828a558-094b-441e-9065-790b87315fa0
ms.openlocfilehash: 401d1ba9cc2f97e93d7851f96f73b552e6ed6356
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378472"
---
# <a name="add-element-for-schemaimporterextensions"></a><span data-ttu-id="2619a-103">\<aggiungere> elemento per \< schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="2619a-103">\<add> Element for \<schemaImporterExtensions></span></span>
<span data-ttu-id="2619a-104">Aggiunge i tipi usati da <xref:System.Xml.Serialization.XmlSchemaImporter> per l'esecuzione del mapping dei tipi XSD ai tipi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2619a-104">Adds types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping XSD types to .NET Framework types.</span></span> <span data-ttu-id="2619a-105">Per altre informazioni sui file di configurazione, vedere [Schema dei file di configurazione](../../../docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="2619a-105">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
 <span data-ttu-id="2619a-106">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2619a-106">\<configuration></span></span>  
<span data-ttu-id="2619a-107">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="2619a-107">\<system.xml.serialization></span></span>  
<span data-ttu-id="2619a-108">\<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="2619a-108">\<schemaImporterExtensions></span></span>  
<span data-ttu-id="2619a-109">\<add></span><span class="sxs-lookup"><span data-stu-id="2619a-109">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2619a-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2619a-110">Syntax</span></span>  
  
```xml  
<add name = "typeName" type="fully qualified type [,Version=version number] [,Culture=culture] [,PublicKeyToken= token]"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2619a-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2619a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="2619a-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2619a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2619a-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="2619a-113">Attributes</span></span>  
  
|<span data-ttu-id="2619a-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="2619a-114">Attribute</span></span>|<span data-ttu-id="2619a-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2619a-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2619a-116">**nome**</span><span class="sxs-lookup"><span data-stu-id="2619a-116">**name**</span></span>|<span data-ttu-id="2619a-117">Un nome semplice usato per cercare l'istanza.</span><span class="sxs-lookup"><span data-stu-id="2619a-117">A simple name that is used to find the instance.</span></span>|  
|<span data-ttu-id="2619a-118">**type**</span><span class="sxs-lookup"><span data-stu-id="2619a-118">**type**</span></span>|<span data-ttu-id="2619a-119">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="2619a-119">Required.</span></span> <span data-ttu-id="2619a-120">Specifica la classe delle estensioni dello schema da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="2619a-120">Specifies the schema  extension class to add.</span></span> <span data-ttu-id="2619a-121">Il valore dell'attributo **type** deve trovarsi su una riga e includere il nome completo del tipo.</span><span class="sxs-lookup"><span data-stu-id="2619a-121">The **type** attribute value must be on one line, and include the fully qualified type name.</span></span> <span data-ttu-id="2619a-122">Quando l'assembly viene inserito nella Global Assembly Cache (GAC) deve includere anche la versione, le impostazioni cultura e il token di chiave pubblica dell'assembly firmato.</span><span class="sxs-lookup"><span data-stu-id="2619a-122">When the assembly is placed in the Global Assembly Cache (GAC), it must also include the version, culture, and public key token of the signed assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2619a-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2619a-123">Child Elements</span></span>  
 <span data-ttu-id="2619a-124">No.</span><span class="sxs-lookup"><span data-stu-id="2619a-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2619a-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2619a-125">Parent Elements</span></span>  
  
|<span data-ttu-id="2619a-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="2619a-126">Element</span></span>|<span data-ttu-id="2619a-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2619a-127">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2619a-128">\<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="2619a-128">\<schemaImporterExtensions></span></span>|<span data-ttu-id="2619a-129">Contiene i tipi usati da <xref:System.Xml.Serialization.XmlSchemaImporter>.</span><span class="sxs-lookup"><span data-stu-id="2619a-129">Contains the types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter>.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2619a-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="2619a-130">Example</span></span>  
 <span data-ttu-id="2619a-131">Nell'esempio di codice riportato di seguito viene aggiunto un tipo di estensione utilizzabile da XmlSchemaImporter durante l'esecuzione del mapping dei tipi.</span><span class="sxs-lookup"><span data-stu-id="2619a-131">The following code example adds an extension type that the XmlSchemaImporter can use when mapping types.</span></span>  
  
```xml  
<configuration>  
  <system.xml.serialization>  
    <schemaImporterExtensions>  
       <add name="contoso" type="System.Web.Mobile.MobileCapabilities,
       System.Web.Mobile, Version=2.0.0.0, Culture=neutral,
       PublicKeyToken=b03f5f7f11d50a3a" />
    </schemaImporterExtensions>  
  </system.xml.serialization>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2619a-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2619a-132">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- [<span data-ttu-id="2619a-133">\<System. XML. Serialization> elemento</span><span class="sxs-lookup"><span data-stu-id="2619a-133">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
- [<span data-ttu-id="2619a-134">\<Elemento> schemaImporterExtensions</span><span class="sxs-lookup"><span data-stu-id="2619a-134">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)
