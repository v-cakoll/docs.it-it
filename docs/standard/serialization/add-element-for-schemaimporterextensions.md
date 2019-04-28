---
title: Elemento <add> per <schemaImporterExtensions>
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- <add> element for <schemaImporterExtensions> element
ms.assetid: c828a558-094b-441e-9065-790b87315fa0
ms.openlocfilehash: 89196b094d5631c9e243a51a718e53f9c06db20d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61794979"
---
# <a name="add-element-for-schemaimporterextensions"></a><span data-ttu-id="3ec97-102">\<aggiungere > (elemento) per \<schemaImporterExtensions ></span><span class="sxs-lookup"><span data-stu-id="3ec97-102">\<add> Element for \<schemaImporterExtensions></span></span>
<span data-ttu-id="3ec97-103">Aggiunge i tipi usati da <xref:System.Xml.Serialization.XmlSchemaImporter> per l'esecuzione del mapping dei tipi XSD ai tipi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3ec97-103">Adds types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping XSD types to .NET Framework types.</span></span> <span data-ttu-id="3ec97-104">Per altre informazioni sui file di configurazione, vedere [Schema dei file di configurazione](../../../docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="3ec97-104">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
 <span data-ttu-id="3ec97-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="3ec97-105">\<configuration></span></span>  
<span data-ttu-id="3ec97-106">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="3ec97-106">\<system.xml.serialization></span></span>  
<span data-ttu-id="3ec97-107">\<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="3ec97-107">\<schemaImporterExtensions></span></span>  
<span data-ttu-id="3ec97-108">\<add></span><span class="sxs-lookup"><span data-stu-id="3ec97-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ec97-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3ec97-109">Syntax</span></span>  
  
```xml  
<add name = "typeName" type="fully qualified type [,Version=version number] [,Culture=culture] [,PublicKeyToken= token]"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3ec97-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3ec97-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3ec97-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3ec97-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3ec97-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="3ec97-112">Attributes</span></span>  
  
|<span data-ttu-id="3ec97-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="3ec97-113">Attribute</span></span>|<span data-ttu-id="3ec97-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3ec97-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3ec97-115">**name**</span><span class="sxs-lookup"><span data-stu-id="3ec97-115">**name**</span></span>|<span data-ttu-id="3ec97-116">Un nome semplice usato per cercare l'istanza.</span><span class="sxs-lookup"><span data-stu-id="3ec97-116">A simple name that is used to find the instance.</span></span>|  
|<span data-ttu-id="3ec97-117">**type**</span><span class="sxs-lookup"><span data-stu-id="3ec97-117">**type**</span></span>|<span data-ttu-id="3ec97-118">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="3ec97-118">Required.</span></span> <span data-ttu-id="3ec97-119">Specifica la classe delle estensioni dello schema da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="3ec97-119">Specifies the schema  extension class to add.</span></span> <span data-ttu-id="3ec97-120">Il valore dell'attributo **type** deve trovarsi su una riga e includere il nome completo del tipo.</span><span class="sxs-lookup"><span data-stu-id="3ec97-120">The **type** attribute value must be on one line, and include the fully qualified type name.</span></span> <span data-ttu-id="3ec97-121">Quando l'assembly viene inserito nella Global Assembly Cache (GAC) deve includere anche la versione, le impostazioni cultura e il token di chiave pubblica dell'assembly firmato.</span><span class="sxs-lookup"><span data-stu-id="3ec97-121">When the assembly is placed in the Global Assembly Cache (GAC), it must also include the version, culture, and public key token of the signed assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3ec97-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3ec97-122">Child Elements</span></span>  
 <span data-ttu-id="3ec97-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="3ec97-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3ec97-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3ec97-124">Parent Elements</span></span>  
  
|<span data-ttu-id="3ec97-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="3ec97-125">Element</span></span>|<span data-ttu-id="3ec97-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3ec97-126">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3ec97-127">\<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="3ec97-127">\<schemaImporterExtensions></span></span>|<span data-ttu-id="3ec97-128">Contiene i tipi usati da <xref:System.Xml.Serialization.XmlSchemaImporter>.</span><span class="sxs-lookup"><span data-stu-id="3ec97-128">Contains the types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter>.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3ec97-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="3ec97-129">Example</span></span>  
 <span data-ttu-id="3ec97-130">Nell'esempio di codice riportato di seguito viene aggiunto un tipo di estensione utilizzabile da XmlSchemaImporter durante l'esecuzione del mapping dei tipi.</span><span class="sxs-lookup"><span data-stu-id="3ec97-130">The following code example adds an extension type that the XmlSchemaImporter can use when mapping types.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3ec97-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ec97-131">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- [<span data-ttu-id="3ec97-132">Elemento \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="3ec97-132">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
- [<span data-ttu-id="3ec97-133">Elemento \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="3ec97-133">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)
