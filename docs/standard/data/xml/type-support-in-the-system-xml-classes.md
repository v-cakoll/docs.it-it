---
title: Supporto di tipi di dati nelle classi System.Xml
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 63570538-06e3-4401-ad4d-ac50be90c7bf
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 14821ef78f20d1ff303afacb42415e4017a92742
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="type-support-in-the-systemxml-classes"></a><span data-ttu-id="69957-102">Supporto di tipi di dati nelle classi System.Xml</span><span class="sxs-lookup"><span data-stu-id="69957-102">Type Support in the System.Xml Classes</span></span>
<span data-ttu-id="69957-103">In .NET Framework versione 2.0 le classi principali XML sono state migliorate per includere funzionalità di supporto dei tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="69957-103">In the .NET Framework version 2.0, the core XML classes have been enhanced to include type support features.</span></span> <span data-ttu-id="69957-104">Le classi <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter> e <xref:System.Xml.XPath.XPathNavigator> includono funzionalità di supporto dei tipi che comprendono la capacità di conversione tra tipi XML Schema e tipi CLR (Common Language Runtime).</span><span class="sxs-lookup"><span data-stu-id="69957-104">The <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, and <xref:System.Xml.XPath.XPathNavigator> classes include type support features including the ability to convert between XML Schema types and common language runtime (CLR) types.</span></span>  
  
 <span data-ttu-id="69957-105">In .NET Framework versione 2.0 le classi <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter> e <xref:System.Xml.XPath.XPathNavigator> sono state migliorate per includere funzionalità di supporto dei tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="69957-105">In the .NET Framework version 2.0, the <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, and <xref:System.Xml.XPath.XPathNavigator> classes have been enhanced to include type support features.</span></span>  
  
-   <span data-ttu-id="69957-106">Il <xref:System.Xml.XmlReader> e <xref:System.Xml.XPath.XPathNavigator> ciascuna delle classi include un **SchemaInfo** proprietà che restituisce le informazioni sullo schema in un nodo.</span><span class="sxs-lookup"><span data-stu-id="69957-106">The <xref:System.Xml.XmlReader> and <xref:System.Xml.XPath.XPathNavigator> classes each include a **SchemaInfo** property that returns the schema information on a node.</span></span>  
  
-   <span data-ttu-id="69957-107">Il **ReadContentAs** e **ReadElementContentAs** e i metodi sulla <xref:System.Xml.XmlReader> classe leggere un valore di testo e convertirlo in un valore CLR con una singola chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="69957-107">The **ReadContentAs** and **ReadElementContentAs** and methods on the <xref:System.Xml.XmlReader> class read a text value and convert it to a CLR value in a single method call.</span></span>  
  
-   <span data-ttu-id="69957-108">Il metodo <xref:System.Xml.XmlWriter.WriteValue%2A> nella classe <xref:System.Xml.XmlWriter> converte un tipo CLR in un tipo XML Schema durante la scrittura XML.</span><span class="sxs-lookup"><span data-stu-id="69957-108">The <xref:System.Xml.XmlWriter.WriteValue%2A> method on the <xref:System.Xml.XmlWriter> class converts a CLR type to an XML Schema type when writing out XML.</span></span>  
  
-   <span data-ttu-id="69957-109">Il **ValueAs** e <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> proprietà la <xref:System.Xml.XPath.XPathNavigator> classe restituisce un valore di nodo e convertirlo in un valore CLR con una singola chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="69957-109">The **ValueAs** and <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> properties on the <xref:System.Xml.XPath.XPathNavigator> class return a node value and convert it to a CLR value in a single method call.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="69957-110">In .NET Framework versione 1.0 era necessario convertire la classe <xref:System.Xml.XmlConvert> tra il tipo XML Schema e il tipo CLR.</span><span class="sxs-lookup"><span data-stu-id="69957-110">In the .NET Framework version 1.0 the <xref:System.Xml.XmlConvert> class was needed to convert between XML Schema and CLR types.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="69957-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="69957-111">In This Section</span></span>  
 [<span data-ttu-id="69957-112">Mapping dei tipi di dati XML ai tipi CLR</span><span class="sxs-lookup"><span data-stu-id="69957-112">Mapping XML Data Types to CLR Types</span></span>](../../../../docs/standard/data/xml/mapping-xml-data-types-to-clr-types.md)  
 <span data-ttu-id="69957-113">Vengono descritti i mapping predefiniti dei tipi di dati XML ai tipi di dati CLR.</span><span class="sxs-lookup"><span data-stu-id="69957-113">Describes the default mappings of XML data types to CLR types.</span></span>  
  
 [<span data-ttu-id="69957-114">Note sull'implementazione di supporto tipo XML</span><span class="sxs-lookup"><span data-stu-id="69957-114">XML Type Support Implementation Notes</span></span>](../../../../docs/standard/data/xml/xml-type-support-implementation-notes.md)  
 <span data-ttu-id="69957-115">Vengono illustrati alcuni dettagli relativi all'implementazione del supporto per i tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="69957-115">Discusses some of the type support implementation details.</span></span>  
  
 [<span data-ttu-id="69957-116">Conversione di tipi di dati XML</span><span class="sxs-lookup"><span data-stu-id="69957-116">Conversion of XML Data Types</span></span>](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)  
 <span data-ttu-id="69957-117">Viene descritto come usare la classe <xref:System.Xml.XmlConvert> per eseguire la conversione tra tipi XML Schema e tipi CLR.</span><span class="sxs-lookup"><span data-stu-id="69957-117">Describes how to use the <xref:System.Xml.XmlConvert> class to convert between XML Schema and CLR types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="69957-118">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="69957-118">Related Sections</span></span>  
 [<span data-ttu-id="69957-119">Accesso sicuro ai dati XML tipizzati con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="69957-119">Accessing Strongly Typed XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/accessing-strongly-typed-xml-data-using-xpathnavigator.md)
