---
title: Elemento <add> per <schemaImporterExtensions>
description: L' <add> elemento aggiunge i tipi utilizzati dalla classe XmlSchemaImporter per il mapping dei tipi XSD ai tipi .NET Framework.
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- <add> element for <schemaImporterExtensions> element
ms.assetid: c828a558-094b-441e-9065-790b87315fa0
ms.openlocfilehash: 6fd8113ad39a22c927035fca574151ae8f002685
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288329"
---
# <a name="add-element-for-schemaimporterextensions"></a><span data-ttu-id="3233e-103">Elemento \<add> per \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="3233e-103">\<add> Element for \<schemaImporterExtensions></span></span>
<span data-ttu-id="3233e-104">Aggiunge i tipi usati da <xref:System.Xml.Serialization.XmlSchemaImporter> per l'esecuzione del mapping dei tipi XSD ai tipi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3233e-104">Adds types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping XSD types to .NET Framework types.</span></span> <span data-ttu-id="3233e-105">Per altre informazioni sui file di configurazione, vedere [Schema dei file di configurazione](../../framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="3233e-105">For more information about configuration files, see [Configuration File Schema](../../framework/configure-apps/file-schema/index.md).</span></span>  
  
 \<configuration>  
\<system.xml.serialization>  
\<schemaImporterExtensions>  
\<add>  
  
## <a name="syntax"></a><span data-ttu-id="3233e-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3233e-106">Syntax</span></span>  
  
```xml  
<add name = "typeName" type="fully qualified type [,Version=version number] [,Culture=culture] [,PublicKeyToken= token]"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3233e-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3233e-107">Attributes and Elements</span></span>  
 <span data-ttu-id="3233e-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3233e-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3233e-109">Attributes</span><span class="sxs-lookup"><span data-stu-id="3233e-109">Attributes</span></span>  
  
|<span data-ttu-id="3233e-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="3233e-110">Attribute</span></span>|<span data-ttu-id="3233e-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3233e-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3233e-112">**nome**</span><span class="sxs-lookup"><span data-stu-id="3233e-112">**name**</span></span>|<span data-ttu-id="3233e-113">Un nome semplice usato per cercare l'istanza.</span><span class="sxs-lookup"><span data-stu-id="3233e-113">A simple name that is used to find the instance.</span></span>|  
|<span data-ttu-id="3233e-114">**type**</span><span class="sxs-lookup"><span data-stu-id="3233e-114">**type**</span></span>|<span data-ttu-id="3233e-115">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="3233e-115">Required.</span></span> <span data-ttu-id="3233e-116">Specifica la classe delle estensioni dello schema da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="3233e-116">Specifies the schema  extension class to add.</span></span> <span data-ttu-id="3233e-117">Il valore dell'attributo **type** deve trovarsi su una riga e includere il nome completo del tipo.</span><span class="sxs-lookup"><span data-stu-id="3233e-117">The **type** attribute value must be on one line, and include the fully qualified type name.</span></span> <span data-ttu-id="3233e-118">Quando l'assembly viene inserito nella Global Assembly Cache (GAC) deve includere anche la versione, le impostazioni cultura e il token di chiave pubblica dell'assembly firmato.</span><span class="sxs-lookup"><span data-stu-id="3233e-118">When the assembly is placed in the Global Assembly Cache (GAC), it must also include the version, culture, and public key token of the signed assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3233e-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3233e-119">Child Elements</span></span>  
 <span data-ttu-id="3233e-120">No.</span><span class="sxs-lookup"><span data-stu-id="3233e-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3233e-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3233e-121">Parent Elements</span></span>  
  
|<span data-ttu-id="3233e-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="3233e-122">Element</span></span>|<span data-ttu-id="3233e-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3233e-123">Description</span></span>|  
|-------------|-----------------|  
|\<schemaImporterExtensions>|<span data-ttu-id="3233e-124">Contiene i tipi usati da <xref:System.Xml.Serialization.XmlSchemaImporter>.</span><span class="sxs-lookup"><span data-stu-id="3233e-124">Contains the types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter>.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3233e-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="3233e-125">Example</span></span>  
 <span data-ttu-id="3233e-126">Nell'esempio di codice riportato di seguito viene aggiunto un tipo di estensione utilizzabile da XmlSchemaImporter durante l'esecuzione del mapping dei tipi.</span><span class="sxs-lookup"><span data-stu-id="3233e-126">The following code example adds an extension type that the XmlSchemaImporter can use when mapping types.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3233e-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3233e-127">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- [<span data-ttu-id="3233e-128">\<system.xml.serialization>Elemento</span><span class="sxs-lookup"><span data-stu-id="3233e-128">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)
- [<span data-ttu-id="3233e-129">\<schemaImporterExtensions>Elemento</span><span class="sxs-lookup"><span data-stu-id="3233e-129">\<schemaImporterExtensions> Element</span></span>](schemaimporterextensions-element.md)
