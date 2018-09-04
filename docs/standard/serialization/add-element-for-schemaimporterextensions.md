---
title: '&lt;aggiungere&gt; (elemento) per &lt;schemaImporterExtensions&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- <add> element for <schemaImporterExtensions> element
ms.assetid: c828a558-094b-441e-9065-790b87315fa0
ms.openlocfilehash: 3d3c72fd64042032d44c49ebde867d111ce03b94
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43542640"
---
# <a name="ltaddgt-element-for-ltschemaimporterextensionsgt"></a><span data-ttu-id="f0eeb-102">&lt;aggiungere&gt; (elemento) per &lt;schemaImporterExtensions&gt;</span><span class="sxs-lookup"><span data-stu-id="f0eeb-102">&lt;add&gt; Element for &lt;schemaImporterExtensions&gt;</span></span>
<span data-ttu-id="f0eeb-103">Aggiunge i tipi usati da <xref:System.Xml.Serialization.XmlSchemaImporter> per l'esecuzione del mapping dei tipi XSD ai tipi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f0eeb-103">Adds types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping XSD types to .NET Framework types.</span></span> <span data-ttu-id="f0eeb-104">Per altre informazioni sui file di configurazione, vedere [Schema dei file di configurazione](../../../docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="f0eeb-104">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
 <span data-ttu-id="f0eeb-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f0eeb-105">\<configuration></span></span>  
<span data-ttu-id="f0eeb-106">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="f0eeb-106">\<system.xml.serialization></span></span>  
<span data-ttu-id="f0eeb-107">\<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="f0eeb-107">\<schemaImporterExtensions></span></span>  
<span data-ttu-id="f0eeb-108">\<add></span><span class="sxs-lookup"><span data-stu-id="f0eeb-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0eeb-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f0eeb-109">Syntax</span></span>  
  
```xml  
<add name = "typeName" type="fully qualified type [,Version=version number] [,Culture=culture] [,PublicKeyToken= token]"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f0eeb-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f0eeb-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f0eeb-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f0eeb-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f0eeb-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="f0eeb-112">Attributes</span></span>  
  
|<span data-ttu-id="f0eeb-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="f0eeb-113">Attribute</span></span>|<span data-ttu-id="f0eeb-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f0eeb-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f0eeb-115">**name**</span><span class="sxs-lookup"><span data-stu-id="f0eeb-115">**name**</span></span>|<span data-ttu-id="f0eeb-116">Un nome semplice usato per cercare l'istanza.</span><span class="sxs-lookup"><span data-stu-id="f0eeb-116">A simple name that is used to find the instance.</span></span>|  
|<span data-ttu-id="f0eeb-117">**type**</span><span class="sxs-lookup"><span data-stu-id="f0eeb-117">**type**</span></span>|<span data-ttu-id="f0eeb-118">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="f0eeb-118">Required.</span></span> <span data-ttu-id="f0eeb-119">Specifica la classe delle estensioni dello schema da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="f0eeb-119">Specifies the schema  extension class to add.</span></span> <span data-ttu-id="f0eeb-120">Il valore dell'attributo **type** deve trovarsi su una riga e includere il nome completo del tipo.</span><span class="sxs-lookup"><span data-stu-id="f0eeb-120">The **type** attribute value must be on one line, and include the fully qualified type name.</span></span> <span data-ttu-id="f0eeb-121">Quando l'assembly viene inserito nella Global Assembly Cache (GAC) deve includere anche la versione, le impostazioni cultura e il token di chiave pubblica dell'assembly firmato.</span><span class="sxs-lookup"><span data-stu-id="f0eeb-121">When the assembly is placed in the Global Assembly Cache (GAC), it must also include the version, culture, and public key token of the signed assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f0eeb-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f0eeb-122">Child Elements</span></span>  
 <span data-ttu-id="f0eeb-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="f0eeb-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f0eeb-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f0eeb-124">Parent Elements</span></span>  
  
|<span data-ttu-id="f0eeb-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="f0eeb-125">Element</span></span>|<span data-ttu-id="f0eeb-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f0eeb-126">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f0eeb-127">\<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="f0eeb-127">\<schemaImporterExtensions></span></span>|<span data-ttu-id="f0eeb-128">Contiene i tipi usati da <xref:System.Xml.Serialization.XmlSchemaImporter>.</span><span class="sxs-lookup"><span data-stu-id="f0eeb-128">Contains the types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter>.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f0eeb-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="f0eeb-129">Example</span></span>  
 <span data-ttu-id="f0eeb-130">Nell'esempio di codice riportato di seguito viene aggiunto un tipo di estensione utilizzabile da XmlSchemaImporter durante l'esecuzione del mapping dei tipi.</span><span class="sxs-lookup"><span data-stu-id="f0eeb-130">The following code example adds an extension type that the XmlSchemaImporter can use when mapping types.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f0eeb-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0eeb-131">See Also</span></span>  
 <xref:System.Xml.Serialization.XmlSchemaImporter>  
 [<span data-ttu-id="f0eeb-132">Elemento \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="f0eeb-132">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)  
 [<span data-ttu-id="f0eeb-133">Elemento \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="f0eeb-133">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)
