---
title: La serializzazione per il file, TextWriter e XmlWriters3
ms.date: 07/20/2015
ms.assetid: 7a0c24df-79ef-41a0-87f5-e6cf79382da9
ms.openlocfilehash: a9908f04e2621da15f065a86feccc5af5cdac96d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54658991"
---
# <a name="serializing-to-files-textwriters-and-xmlwriters"></a><span data-ttu-id="5b332-102">Serializzazione in base a File, TextWriter e XmlWriter</span><span class="sxs-lookup"><span data-stu-id="5b332-102">Serializing to Files, TextWriters, and XmlWriters</span></span>
<span data-ttu-id="5b332-103">È possibile serializzare gli alberi XML in un oggetto <xref:System.IO.File>, <xref:System.IO.TextWriter> o <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="5b332-103">You can serialize XML trees to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="5b332-104">È possibile serializzare qualsiasi componente XML, incluso <xref:System.Xml.Linq.XDocument> e <xref:System.Xml.Linq.XElement>, in una stringa usando il metodo `ToString`.</span><span class="sxs-lookup"><span data-stu-id="5b332-104">You can serialize any XML component, including <xref:System.Xml.Linq.XDocument> and <xref:System.Xml.Linq.XElement>, to a string by using the `ToString` method.</span></span>  
  
 <span data-ttu-id="5b332-105">Per eliminare la formattazione quando si esegue la serializzazione in una stringa, usare il metodo <xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5b332-105">If you want to suppress formatting when serializing to a string, you can use the <xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="5b332-106">Il comportamento predefinito quando si esegue la serializzazione in un file implica la formattazione, ovvero l'impostazione di rientri, nel documento XML.</span><span class="sxs-lookup"><span data-stu-id="5b332-106">Thedefault behavior when serializing to a file is to format (indent) the resulting XML document.</span></span> <span data-ttu-id="5b332-107">Quando si impostano i rientri, lo spazio vuoto non significativo nell'albero XML non viene conservato.</span><span class="sxs-lookup"><span data-stu-id="5b332-107">When you indent, the insignificant white space in the XML tree is not preserved.</span></span> <span data-ttu-id="5b332-108">Per serializzare e formattare al contempo il documento, usare uno degli overload dei metodi seguenti che non accettano <xref:System.Xml.Linq.SaveOptions> come argomento:</span><span class="sxs-lookup"><span data-stu-id="5b332-108">To serialize with formatting, use one of the overloads of the following methods that do not take <xref:System.Xml.Linq.SaveOptions> as an argument:</span></span>  
  
-   <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="5b332-109">Se si desidera applicare l'opzione per non impostare i rientri e conservare lo spazio vuoto non significativo nell'albero XML, usare uno degli overload dei metodi seguenti che accettano <xref:System.Xml.Linq.SaveOptions> come argomento:</span><span class="sxs-lookup"><span data-stu-id="5b332-109">If you want the option not to indent and to preserve the insignificant white space in the XML tree, use one of the overloads of the following methods that takes <xref:System.Xml.Linq.SaveOptions> as an argument:</span></span>  
  
-   <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="5b332-110">Per gli esempi, vedere l'argomento di riferimento appropriato.</span><span class="sxs-lookup"><span data-stu-id="5b332-110">For examples, see the appropriate reference topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b332-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b332-111">See also</span></span>
- [<span data-ttu-id="5b332-112">Serializzazione di alberi XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5b332-112">Serializing XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
