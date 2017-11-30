---
title: Set di nodi nelle trasformazioni
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ad034f0e-ff8b-4a71-9a4c-528c754263c4
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e4d6d2f5a68ce5cef9937edc136e52efcd5366df
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="node-sets-in-transformations"></a><span data-ttu-id="08e8d-102">Set di nodi nelle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="08e8d-102">Node Sets in Transformations</span></span>
<span data-ttu-id="08e8d-103">I set di nodi sono uno dei quattro tipi di dati principali restituiti dalle espressioni XPath (XML Path Language).</span><span class="sxs-lookup"><span data-stu-id="08e8d-103">Node sets are one of four basic data types that are returned from XML Path Language (XPath) expressions.</span></span> <span data-ttu-id="08e8d-104">Un set di nodi, ovvero una raccolta di nodi non ordinati senza duplicati e creati in base all'ordine con cui sono riportati del documento, può essere assegnato a una variabile in un foglio di stile.</span><span class="sxs-lookup"><span data-stu-id="08e8d-104">A node set, which is an unordered collection of nodes without duplicates, created in document order, can be assigned to a variable in a style sheet.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="08e8d-105">La classe <xref:System.Xml.Xsl.XslTransform> è obsoleta in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span><span class="sxs-lookup"><span data-stu-id="08e8d-105">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span> <span data-ttu-id="08e8d-106">È possibile eseguire le trasformazioni XSLT (Extensible Stylesheet Language for Transformations) usando la classe <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="08e8d-106">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="08e8d-107">Vedere [utilizzando la classe XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) e [la migrazione dalla classe XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="08e8d-107">See [Using the XslCompiledTransform Class](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="08e8d-108">I set di nodi sono uno dei quattro tipi di dati principali restituiti dalle espressioni XPath.</span><span class="sxs-lookup"><span data-stu-id="08e8d-108">Node sets are one of four basic data types that are returned from XPath expressions.</span></span> <span data-ttu-id="08e8d-109">Un set di nodi, ovvero una raccolta di nodi non ordinati senza duplicati e creati in base all'ordine con cui sono riportati del documento, può essere assegnato a una variabile in un foglio di stile.</span><span class="sxs-lookup"><span data-stu-id="08e8d-109">A node set, which is an unordered collection of nodes without duplicates, created in document order, can be assigned to a variable in a style sheet.</span></span> <span data-ttu-id="08e8d-110">Il set di nodi risultante da un'espressione XPath usata in un attributo `select` per una trasformazione ha lo stesso comportamento di un set di nodi proveniente dal DOM (Document Object Model) XML.</span><span class="sxs-lookup"><span data-stu-id="08e8d-110">This node set, which is a result of an XPath expression used in a `select` attribute in a transformation, has the same behavior as a node set from the XML Document Object Model (DOM).</span></span> <span data-ttu-id="08e8d-111">È possibile passare un set di nodi usando un set di metodi di [Node Set Navigation utilizzando XPathNavigator](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md), a differenza di un frammento di albero risultato o un frammento di albero risultato, che utilizza il <xref:System.Xml.XPath.XPathNodeIterator> per la navigazione.</span><span class="sxs-lookup"><span data-stu-id="08e8d-111">You can navigate a node set using a set of methods shown in [Node Set Navigation Using XPathNavigator](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md), unlike a result tree fragment or result tree fragment, which uses the <xref:System.Xml.XPath.XPathNodeIterator> for navigation.</span></span>  
  
 <span data-ttu-id="08e8d-112">Nell'esempio di codice seguente viene illustrato come scorrere un set di nodi quando un elemento `variable` o `parameter` di un foglio di stile viene valutato come set di nodi.</span><span class="sxs-lookup"><span data-stu-id="08e8d-112">The following code sample shows how to iterate over a node set when a `variable` or `parameter` element in a style sheet evaluates to a node set.</span></span>  
  
## <a name="style-sheet"></a><span data-ttu-id="08e8d-113">Foglio di stile</span><span class="sxs-lookup"><span data-stu-id="08e8d-113">Style Sheet</span></span>  
  
```xml  
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">  
  
    <xsl:variable name="x" select="bookstore/book/title"></xsl:variable>  
  
    <xsl:template match="/">  
        <xsl:for-each select="$x">  
            ******  
            <xsl:value-of select="."></xsl:value-of>  
            ******  
        </xsl:for-each>  
    </xsl:template>  
  
</xsl:stylesheet>  
```  
  
## <a name="input"></a><span data-ttu-id="08e8d-114">Input</span><span class="sxs-lookup"><span data-stu-id="08e8d-114">Input</span></span>  
  
```xml  
<bookstore>  
   <book style="autobiography">  
      <title>Seven Years in Trenton</title>  
   </book>  
  
   <book style="autobiography">  
      <title>Seven Years in Trenton2</title>  
   </book>  
  
   <book style="textbook">  
      <title>History of Trenton Vol 3</title>  
   </book>  
</bookstore>  
```  
  
## <a name="output"></a><span data-ttu-id="08e8d-115">Output</span><span class="sxs-lookup"><span data-stu-id="08e8d-115">Output</span></span>  
  
```  
******  
Seven Years in Trenton  
******  
  
******  
Seven Years in Trenton2  
******  
  
******  
History of Trenton Vol 3  
******  
```  
  
## <a name="see-also"></a><span data-ttu-id="08e8d-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08e8d-116">See Also</span></span>  
 <xref:System.Xml.XPath.XPathNodeIterator>  
 [<span data-ttu-id="08e8d-117">Trasformazioni XSLT con la classe XslTransform</span><span class="sxs-lookup"><span data-stu-id="08e8d-117">XSLT Transformations with the XslTransform Class</span></span>](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)  
 [<span data-ttu-id="08e8d-118">Classe XslTransform implementa il processore XSLT</span><span class="sxs-lookup"><span data-stu-id="08e8d-118">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
