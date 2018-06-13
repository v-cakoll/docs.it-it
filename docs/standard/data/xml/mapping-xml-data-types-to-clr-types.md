---
title: Mapping dei tipi di dati XML a tipi di dati CLR
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: cabdfcad-f359-479b-b71c-8b2fad42ca49
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d06876b91c72b939768d480e40631a8e85170bc9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33568544"
---
# <a name="mapping-xml-data-types-to-clr-types"></a><span data-ttu-id="1c327-102">Mapping dei tipi di dati XML a tipi di dati CLR</span><span class="sxs-lookup"><span data-stu-id="1c327-102">Mapping XML Data Types to CLR Types</span></span>
<span data-ttu-id="1c327-103">Nella tabella seguente viene descritto il mapping predefinito tra i tipi di dati XML e i tipi CLR (Common Language Runtime).</span><span class="sxs-lookup"><span data-stu-id="1c327-103">The following table describes the default mapping between the XML data types and the common language runtime (CLR) types.</span></span>  
  
## <a name="the-following-table-describes-the-default-mappings-of-an-xml-data-type-to-a-clr-type"></a><span data-ttu-id="1c327-104">Nella tabella seguente vengono descritti i mapping predefiniti di un tipo di dati XML a un tipo CLR.</span><span class="sxs-lookup"><span data-stu-id="1c327-104">The following table describes the default mappings of an XML data type to a CLR type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1c327-105">I prefissi `xs` e `xdt` vengono mappati rispettivamente negli URI dello spazio dei nomi http://www.w3.org/2001/XMLSchema e http://www.w3.org/2003/05/xpath-datatypes.</span><span class="sxs-lookup"><span data-stu-id="1c327-105">The `xs` and the `xdt` prefixes are mapped to the http://www.w3.org/2001/XMLSchema and the http://www.w3.org/2003/05/xpath-datatypes namespace URIs respectively.</span></span>  
  
|<span data-ttu-id="1c327-106">Tipo XML</span><span class="sxs-lookup"><span data-stu-id="1c327-106">XML Type</span></span>|<span data-ttu-id="1c327-107">Tipo CLR</span><span class="sxs-lookup"><span data-stu-id="1c327-107">CLR Type</span></span>|  
|--------------|--------------|  
|`xs:anyURI`|<xref:System.Uri>|  
|`xs:base64Binary`|`Byte[]`|  
|`xs:boolean`|<xref:System.Boolean>|  
|`xs:byte`|<xref:System.SByte>|  
|`xs:date`|<xref:System.DateTime>|  
|`xs:dateTime`|<xref:System.DateTime>|  
|`xs:decimal`|<xref:System.Decimal>|  
|`xs:double`|<xref:System.Double>|  
|`xs:duration`|<xref:System.TimeSpan>|  
|`xs:ENTITIES`|`String[]`|  
|`xs:ENTITY`|<xref:System.String>|  
|`xs:float`|<xref:System.Single>|  
|`xs:gDay`|<xref:System.DateTime>|  
|`xs:gMonthDay`|<xref:System.DateTime>|  
|`xs:gYear`|<xref:System.DateTime>|  
|`xs:gYearMonth`|<xref:System.DateTime>|  
|`xs:hexBinary`|`Byte[]`|  
|`xs:ID`|<xref:System.String>|  
|`xs:IDREF`|<xref:System.String>|  
|`xs:IDREFS`|`String[]`|  
|`xs:int`|<xref:System.Int32>|  
|`xs:integer`|<xref:System.Decimal>|  
|`xs:language`|<xref:System.String>|  
|`xs:long`|<xref:System.Int64>|  
|`xs:gMmonth`|<xref:System.DateTime>|  
|`xs:Name`|<xref:System.String>|  
|`xs:NCName`|<xref:System.String>|  
|`xs:negativeInteger`|<xref:System.Decimal>|  
|`xs:NMTOKEN`|<xref:System.String>|  
|`xs:NMTOKENS`|`String[]`|  
|`xs:nonNegativeInteger`|<xref:System.Decimal>|  
|`xs:nonPositiveInteger`|<xref:System.Decimal>|  
|`xs:normalizedString`|<xref:System.String>|  
|`xs:NOTATION`|<xref:System.Xml.XmlQualifiedName>|  
|`xs:positiveInteger`|<xref:System.Decimal>|  
|`xs:QName`|<xref:System.Xml.XmlQualifiedName>|  
|`xs:short`|<xref:System.Int16>|  
|`xs:string`|<xref:System.String>|  
|`xs:time`|<xref:System.DateTime>|  
|`xs:token`|<xref:System.String>|  
|`xs:unsignedByte`|<xref:System.Byte>|  
|`xs:unsignedInt`|<xref:System.UInt32>|  
|`xs:unsignedLong`|<xref:System.UInt64>|  
|`xs:unsignedShort`|<xref:System.UInt16>|  
|`xdt:dayTimeDuration`|<xref:System.TimeSpan>|  
|`xdt:yearMonthDuration`|<xref:System.TimeSpan>|  
|`xdt:untypedAtomic`|<xref:System.String>|  
|`xdt:anyAtomicType`|<xref:System.Object>|  
|`xs:anySimpleType`|<xref:System.String>|  
|<span data-ttu-id="1c327-108">Nodo documento</span><span class="sxs-lookup"><span data-stu-id="1c327-108">Document node</span></span>|<xref:System.Xml.XPath.XPathNavigator>|  
|<span data-ttu-id="1c327-109">Nodo elemento</span><span class="sxs-lookup"><span data-stu-id="1c327-109">Element node</span></span>|<xref:System.Xml.XPath.XPathNavigator>|  
|<span data-ttu-id="1c327-110">Nodo attributo</span><span class="sxs-lookup"><span data-stu-id="1c327-110">Attribute node</span></span>|<xref:System.Xml.XPath.XPathNavigator>|  
|<span data-ttu-id="1c327-111">Nodo spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="1c327-111">Namespace node</span></span>|<xref:System.Xml.XPath.XPathNavigator>|  
|<span data-ttu-id="1c327-112">Nodo testo</span><span class="sxs-lookup"><span data-stu-id="1c327-112">Text node</span></span>|<xref:System.Xml.XPath.XPathNavigator>|  
|<span data-ttu-id="1c327-113">Nodo commento</span><span class="sxs-lookup"><span data-stu-id="1c327-113">Comment node</span></span>|<xref:System.Xml.XPath.XPathNavigator>|  
|<span data-ttu-id="1c327-114">Nodo istruzione di elaborazione</span><span class="sxs-lookup"><span data-stu-id="1c327-114">Processing instruction node</span></span>|<xref:System.Xml.XPath.XPathNavigator>|  
  
## <a name="see-also"></a><span data-ttu-id="1c327-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c327-115">See Also</span></span>  
 [<span data-ttu-id="1c327-116">Supporto di tipi di dati nelle classi System.Xml</span><span class="sxs-lookup"><span data-stu-id="1c327-116">Type Support in the System.Xml Classes</span></span>](../../../../docs/standard/data/xml/type-support-in-the-system-xml-classes.md)
