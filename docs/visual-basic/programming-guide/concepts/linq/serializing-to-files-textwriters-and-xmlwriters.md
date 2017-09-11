---
title: La serializzazione per il file, TextWriter e XmlWriters3 | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 7a0c24df-79ef-41a0-87f5-e6cf79382da9
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: f8f8672004b0704b00ff60e5b58256f664bcbd82
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="serializing-to-files-textwriters-and-xmlwriters"></a><span data-ttu-id="c4337-102">Serializzazione in base a File, TextWriter e XmlWriter</span><span class="sxs-lookup"><span data-stu-id="c4337-102">Serializing to Files, TextWriters, and XmlWriters</span></span>
<span data-ttu-id="c4337-103">È possibile serializzare gli alberi XML in un <xref:System.IO.File>, <xref:System.IO.TextWriter>, o un <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> </xref:System.IO.TextWriter> </xref:System.IO.File></span><span class="sxs-lookup"><span data-stu-id="c4337-103">You can serialize XML trees to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="c4337-104">È possibile serializzare qualsiasi componente XML, tra cui <xref:System.Xml.Linq.XDocument>e <xref:System.Xml.Linq.XElement>, in una stringa utilizzando il `ToString` (metodo).</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="c4337-104">You can serialize any XML component, including <xref:System.Xml.Linq.XDocument> and <xref:System.Xml.Linq.XElement>, to a string by using the `ToString` method.</span></span>  
  
 <span data-ttu-id="c4337-105">Se si desidera eliminare la formattazione durante la serializzazione in una stringa, è possibile utilizzare il <xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=fullName>(metodo).</xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c4337-105">If you want to suppress formatting when serializing to a string, you can use the <xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=fullName> method.</span></span>  
  
 <span data-ttu-id="c4337-106">Thedefault comportamento durante la serializzazione in un file implica la formattazione (rientri) il documento XML.</span><span class="sxs-lookup"><span data-stu-id="c4337-106">Thedefault behavior when serializing to a file is to format (indent) the resulting XML document.</span></span> <span data-ttu-id="c4337-107">Quando si impostano i rientri, lo spazio vuoto non significativo nell'albero XML non viene conservato.</span><span class="sxs-lookup"><span data-stu-id="c4337-107">When you indent, the insignificant white space in the XML tree is not preserved.</span></span> <span data-ttu-id="c4337-108">Per serializzare e formattare, utilizzare uno degli overload dei metodi seguenti che non accettano <xref:System.Xml.Linq.SaveOptions>come argomento:</xref:System.Xml.Linq.SaveOptions></span><span class="sxs-lookup"><span data-stu-id="c4337-108">To serialize with formatting, use one of the overloads of the following methods that do not take <xref:System.Xml.Linq.SaveOptions> as an argument:</span></span>  
  
-   <span data-ttu-id="c4337-109"><xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c4337-109"><xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></span></span>  
  
-   <span data-ttu-id="c4337-110"><xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c4337-110"><xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></span></span>  
  
 <span data-ttu-id="c4337-111">Se si desidera che l'opzione di non impostare i rientri e conservare lo spazio vuoto non significativo nella struttura ad albero XML, utilizzare uno degli overload dei metodi seguenti che accetta <xref:System.Xml.Linq.SaveOptions>come argomento:</xref:System.Xml.Linq.SaveOptions></span><span class="sxs-lookup"><span data-stu-id="c4337-111">If you want the option not to indent and to preserve the insignificant white space in the XML tree, use one of the overloads of the following methods that takes <xref:System.Xml.Linq.SaveOptions> as an argument:</span></span>  
  
-   <span data-ttu-id="c4337-112"><xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c4337-112"><xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></span></span>  
  
-   <span data-ttu-id="c4337-113"><xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c4337-113"><xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></span></span>  
  
 <span data-ttu-id="c4337-114">Per gli esempi, vedere l'argomento di riferimento appropriato.</span><span class="sxs-lookup"><span data-stu-id="c4337-114">For examples, see the appropriate reference topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4337-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4337-115">See Also</span></span>  
 [<span data-ttu-id="c4337-116">La serializzazione di strutture ad albero XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c4337-116">Serializing XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
