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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 7cd79acbdef09acb0a05c818d8358cd612c3bcdf
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="support-for-the-msxslnode-set-function"></a><span data-ttu-id="70dc6-102">Supporto per la funzione msxsl:node-set()</span><span class="sxs-lookup"><span data-stu-id="70dc6-102">Support for the msxsl:node-set() Function</span></span>
<span data-ttu-id="70dc6-103">La funzione `msxsl:node-set` consente di convertire un frammento di albero risultato in un set di nodi.</span><span class="sxs-lookup"><span data-stu-id="70dc6-103">The `msxsl:node-set` function enables you to convert a result tree fragment into a node set.</span></span> <span data-ttu-id="70dc6-104">Il set di nodi risultante contiene sempre un nodo singolo ed è il nodo radice dell'albero.</span><span class="sxs-lookup"><span data-stu-id="70dc6-104">The resulting node set always contains a single node and is the root node of the tree.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="70dc6-105">La classe <xref:System.Xml.Xsl.XslTransform> è obsoleta in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span><span class="sxs-lookup"><span data-stu-id="70dc6-105">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span> <span data-ttu-id="70dc6-106">È possibile eseguire le trasformazioni XSLT (Extensible Stylesheet Language for Transformations) usando la classe <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="70dc6-106">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="70dc6-107">Per altre informazioni, vedere [Utilizzo della classe XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) e [Migrazione dalla classe XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md).</span><span class="sxs-lookup"><span data-stu-id="70dc6-107">See [Using the XslCompiledTransform Class](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="70dc6-108">La funzione `msxsl:node-set` consente di convertire un frammento di albero risultato in un set di nodi.</span><span class="sxs-lookup"><span data-stu-id="70dc6-108">The `msxsl:node-set` function enables you to convert a result tree fragment into a node set.</span></span> <span data-ttu-id="70dc6-109">Il set di nodi risultante contiene sempre un nodo singolo ed è il nodo radice dell'albero.</span><span class="sxs-lookup"><span data-stu-id="70dc6-109">The resulting node set always contains a single node and is the root node of the tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70dc6-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="70dc6-110">Example</span></span>  
 <span data-ttu-id="70dc6-111">Nell'esempio seguente `$var` è una variabile che rappresenta l'albero dei nodi del foglio di stile.</span><span class="sxs-lookup"><span data-stu-id="70dc6-111">In the following example, `$var` is a variable that is a node tree in the style sheet.</span></span> <span data-ttu-id="70dc6-112">L'istruzione for-each combinata con la funzione `node-set` consente all'utente di eseguire un'iterazione su questo albero come set di nodi.</span><span class="sxs-lookup"><span data-stu-id="70dc6-112">The for-each statement combined with the `node-set` function allows the user to iterate over this node tree as a node set.</span></span>  
  
## <a name="nodesetxsl"></a><span data-ttu-id="70dc6-113">nodeset.xsl</span><span class="sxs-lookup"><span data-stu-id="70dc6-113">nodeset.xsl</span></span>  
  
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
  
## <a name="output"></a><span data-ttu-id="70dc6-114">Output</span><span class="sxs-lookup"><span data-stu-id="70dc6-114">Output</span></span>  
 <span data-ttu-id="70dc6-115">Output della trasformazione:</span><span class="sxs-lookup"><span data-stu-id="70dc6-115">The output of the transformation is</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<authors><author>Michael Howard</author><author>Michael Kay</author></authors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="70dc6-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70dc6-116">See Also</span></span>  
 [<span data-ttu-id="70dc6-117">Implementazione del processore XSLT da parte della classe XslTransform</span><span class="sxs-lookup"><span data-stu-id="70dc6-117">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
