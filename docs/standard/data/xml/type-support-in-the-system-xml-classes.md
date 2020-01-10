---
title: Supporto di tipi di dati nelle classi System.Xml
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 63570538-06e3-4401-ad4d-ac50be90c7bf
ms.openlocfilehash: cec47d40a0353639bc17b880265f7c15f2f53ac4
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710102"
---
# <a name="type-support-in-the-systemxml-classes"></a><span data-ttu-id="db6ab-102">Supporto di tipi di dati nelle classi System.Xml</span><span class="sxs-lookup"><span data-stu-id="db6ab-102">Type Support in the System.Xml Classes</span></span>
<span data-ttu-id="db6ab-103">In .NET Framework versione 2.0 le classi principali XML sono state migliorate per includere funzionalità di supporto dei tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="db6ab-103">In the .NET Framework version 2.0, the core XML classes have been enhanced to include type support features.</span></span> <span data-ttu-id="db6ab-104">Le classi <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter> e <xref:System.Xml.XPath.XPathNavigator> includono funzionalità di supporto dei tipi che comprendono la capacità di conversione tra tipi XML Schema e tipi CLR (Common Language Runtime).</span><span class="sxs-lookup"><span data-stu-id="db6ab-104">The <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, and <xref:System.Xml.XPath.XPathNavigator> classes include type support features including the ability to convert between XML Schema types and common language runtime (CLR) types.</span></span>  
  
 <span data-ttu-id="db6ab-105">In .NET Framework versione 2.0 le classi <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter> e <xref:System.Xml.XPath.XPathNavigator> sono state migliorate per includere funzionalità di supporto dei tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="db6ab-105">In the .NET Framework version 2.0, the <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, and <xref:System.Xml.XPath.XPathNavigator> classes have been enhanced to include type support features.</span></span>  
  
- <span data-ttu-id="db6ab-106">Le classi <xref:System.Xml.XmlReader> e <xref:System.Xml.XPath.XPathNavigator> includono ciascuna una proprietà **SchemaInfo** che consente di restituire le informazioni sullo schema in un nodo.</span><span class="sxs-lookup"><span data-stu-id="db6ab-106">The <xref:System.Xml.XmlReader> and <xref:System.Xml.XPath.XPathNavigator> classes each include a **SchemaInfo** property that returns the schema information on a node.</span></span>  
  
- <span data-ttu-id="db6ab-107">Le proprietà **ReadContentAs** e **ReadElementContentAs** nella classe <xref:System.Xml.XmlReader> leggono un valore di testo e lo convertono in un valore CLR con una singola chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="db6ab-107">The **ReadContentAs** and **ReadElementContentAs** and methods on the <xref:System.Xml.XmlReader> class read a text value and convert it to a CLR value in a single method call.</span></span>  
  
- <span data-ttu-id="db6ab-108">Il metodo <xref:System.Xml.XmlWriter.WriteValue%2A> nella classe <xref:System.Xml.XmlWriter> converte un tipo CLR in un tipo XML Schema durante la scrittura XML.</span><span class="sxs-lookup"><span data-stu-id="db6ab-108">The <xref:System.Xml.XmlWriter.WriteValue%2A> method on the <xref:System.Xml.XmlWriter> class converts a CLR type to an XML Schema type when writing out XML.</span></span>  
  
- <span data-ttu-id="db6ab-109">Le proprietà **ValueAs** e <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> nella classe <xref:System.Xml.XPath.XPathNavigator> restituiscono un valore di nodo e lo convertono in un valore CLR con una singola chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="db6ab-109">The **ValueAs** and <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> properties on the <xref:System.Xml.XPath.XPathNavigator> class return a node value and convert it to a CLR value in a single method call.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="db6ab-110">In .NET Framework versione 1.0 era necessario convertire la classe <xref:System.Xml.XmlConvert> tra il tipo XML Schema e il tipo CLR.</span><span class="sxs-lookup"><span data-stu-id="db6ab-110">In the .NET Framework version 1.0 the <xref:System.Xml.XmlConvert> class was needed to convert between XML Schema and CLR types.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="db6ab-111">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="db6ab-111">In This Section</span></span>  
 [<span data-ttu-id="db6ab-112">Mapping dei tipi di dati XML a tipi di dati CLR</span><span class="sxs-lookup"><span data-stu-id="db6ab-112">Mapping XML Data Types to CLR Types</span></span>](../../../../docs/standard/data/xml/mapping-xml-data-types-to-clr-types.md)  
 <span data-ttu-id="db6ab-113">Vengono descritti i mapping predefiniti dei tipi di dati XML ai tipi di dati CLR.</span><span class="sxs-lookup"><span data-stu-id="db6ab-113">Describes the default mappings of XML data types to CLR types.</span></span>  
  
 [<span data-ttu-id="db6ab-114">Note sull'implementazione del supporto per il tipo XML</span><span class="sxs-lookup"><span data-stu-id="db6ab-114">XML Type Support Implementation Notes</span></span>](../../../../docs/standard/data/xml/xml-type-support-implementation-notes.md)  
 <span data-ttu-id="db6ab-115">Vengono illustrati alcuni dettagli relativi all'implementazione del supporto per i tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="db6ab-115">Discusses some of the type support implementation details.</span></span>  
  
 [<span data-ttu-id="db6ab-116">Conversione dei tipi di dati XML</span><span class="sxs-lookup"><span data-stu-id="db6ab-116">Conversion of XML Data Types</span></span>](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)  
 <span data-ttu-id="db6ab-117">Viene descritto come usare la classe <xref:System.Xml.XmlConvert> per eseguire la conversione tra tipi XML Schema e tipi CLR.</span><span class="sxs-lookup"><span data-stu-id="db6ab-117">Describes how to use the <xref:System.Xml.XmlConvert> class to convert between XML Schema and CLR types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="db6ab-118">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="db6ab-118">Related Sections</span></span>  
 [<span data-ttu-id="db6ab-119">Accesso a dati XML fortemente tipizzati con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="db6ab-119">Accessing Strongly Typed XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/accessing-strongly-typed-xml-data-using-xpathnavigator.md)
