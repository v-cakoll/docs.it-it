---
title: Supporto per la funzione msxsl:node-set()
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d0cbf517-d9f6-4097-9851-4fa62903decd
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a3dcb45e6aeecb9e54ad48db4130689ac0fdd358
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="support-for-the-msxslnode-set-function"></a><span data-ttu-id="46bec-102">Supporto per la funzione msxsl:node-set()</span><span class="sxs-lookup"><span data-stu-id="46bec-102">Support for the msxsl:node-set() Function</span></span>
<span data-ttu-id="46bec-103">La funzione `msxsl:node-set` consente di convertire un frammento di albero risultato in un set di nodi.</span><span class="sxs-lookup"><span data-stu-id="46bec-103">The `msxsl:node-set` function enables you to convert a result tree fragment into a node set.</span></span> <span data-ttu-id="46bec-104">Il set di nodi risultante contiene sempre un nodo singolo ed è il nodo radice dell'albero.</span><span class="sxs-lookup"><span data-stu-id="46bec-104">The resulting node set always contains a single node and is the root node of the tree.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="46bec-105">La classe <xref:System.Xml.Xsl.XslTransform> è obsoleta in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span><span class="sxs-lookup"><span data-stu-id="46bec-105">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span> <span data-ttu-id="46bec-106">È possibile eseguire le trasformazioni XSLT (Extensible Stylesheet Language for Transformations) usando la classe <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="46bec-106">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="46bec-107">Vedere [utilizzando la classe XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) e [la migrazione dalla classe XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="46bec-107">See [Using the XslCompiledTransform Class](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="46bec-108">La funzione `msxsl:node-set` consente di convertire un frammento di albero risultato in un set di nodi.</span><span class="sxs-lookup"><span data-stu-id="46bec-108">The `msxsl:node-set` function enables you to convert a result tree fragment into a node set.</span></span> <span data-ttu-id="46bec-109">Il set di nodi risultante contiene sempre un nodo singolo ed è il nodo radice dell'albero.</span><span class="sxs-lookup"><span data-stu-id="46bec-109">The resulting node set always contains a single node and is the root node of the tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46bec-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="46bec-110">Example</span></span>  
 <span data-ttu-id="46bec-111">Nell'esempio seguente `$var` è una variabile che rappresenta l'albero dei nodi del foglio di stile.</span><span class="sxs-lookup"><span data-stu-id="46bec-111">In the following example, `$var` is a variable that is a node tree in the style sheet.</span></span> <span data-ttu-id="46bec-112">L'istruzione for-each combinata con la funzione `node-set` consente all'utente di eseguire un'iterazione su questo albero come set di nodi.</span><span class="sxs-lookup"><span data-stu-id="46bec-112">The for-each statement combined with the `node-set` function allows the user to iterate over this node tree as a node set.</span></span>  
  
## <a name="nodesetxsl"></a><span data-ttu-id="46bec-113">nodeset.xsl</span><span class="sxs-lookup"><span data-stu-id="46bec-113">nodeset.xsl</span></span>  
  
```xml  
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform"  
                xmlns:msxsl="urn:schemas-microsoft-com:xslt"  
                xmlns:user="http://www.contoso.com"  
                version="1.0">  
    <xsl:variable name="books">  
        <book author="Michael Howard">Writing Secure Code</book>  
        <book author="Michael Kay">XSLT Reference</book>  
    </xsl:variable>  
  
    <xsl:template match="/">  
        <authors>  
            <xsl:for-each select="msxsl:node-set($books)/book">   
                <author><xsl:value-of select="@author"/)</author>  
            </xsl:for-each>  
        </authors>  
    </xsl:template>  
</xsl:stylesheet>  
```  
  
## <a name="output"></a><span data-ttu-id="46bec-114">Output</span><span class="sxs-lookup"><span data-stu-id="46bec-114">Output</span></span>  
 <span data-ttu-id="46bec-115">Output della trasformazione:</span><span class="sxs-lookup"><span data-stu-id="46bec-115">The output of the transformation is</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<authors><author>Michael Howard</author><author>Michael Kay</author></authors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="46bec-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46bec-116">See Also</span></span>  
 [<span data-ttu-id="46bec-117">Classe XslTransform implementa il processore XSLT</span><span class="sxs-lookup"><span data-stu-id="46bec-117">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
