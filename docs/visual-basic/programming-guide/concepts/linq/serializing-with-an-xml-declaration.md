---
title: Serializzazione con una dichiarazione XML (Visual Basic) | Documenti di Microsoft
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
ms.assetid: 8726f79e-2bb0-4ba0-969d-197cca591647
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
ms.openlocfilehash: 50707da956df593f176764bed94adfc6aec3dfa5
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="serializing-with-an-xml-declaration-visual-basic"></a><span data-ttu-id="54475-102">Serializzazione con una dichiarazione XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="54475-102">Serializing with an XML Declaration (Visual Basic)</span></span>
<span data-ttu-id="54475-103">In questo argomento viene descritto come controllare se la serializzazione genera una dichiarazione XML.</span><span class="sxs-lookup"><span data-stu-id="54475-103">This topic describes how to control whether serialization generates an XML declaration.</span></span>  
  
## <a name="xml-declaration-generation"></a><span data-ttu-id="54475-104">Generazione della dichiarazione XML</span><span class="sxs-lookup"><span data-stu-id="54475-104">XML Declaration Generation</span></span>  
 <span data-ttu-id="54475-105">La serializzazione di un <xref:System.IO.File>o un <xref:System.IO.TextWriter>utilizzando il <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName>metodo o <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName>metodo genera una dichiarazione XML.</xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName> </xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName> </xref:System.IO.TextWriter> </xref:System.IO.File></span><span class="sxs-lookup"><span data-stu-id="54475-105">Serializing to a <xref:System.IO.File> or a <xref:System.IO.TextWriter> using the <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName> method or the <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName> method generates an XML declaration.</span></span> <span data-ttu-id="54475-106">Quando si serializza in un <xref:System.Xml.XmlWriter>, le impostazioni del writer (specificate in un <xref:System.Xml.XmlWriterSettings>oggetto) determinano se una dichiarazione XML viene generata o meno.</xref:System.Xml.XmlWriterSettings> </xref:System.Xml.XmlWriter></span><span class="sxs-lookup"><span data-stu-id="54475-106">When you serialize to an <xref:System.Xml.XmlWriter>, the writer settings (specified in an <xref:System.Xml.XmlWriterSettings> object) determine whether an XML declaration is generated or not.</span></span>  
  
 <span data-ttu-id="54475-107">Se si serializza in una stringa tramite il metodo `ToString`, l'XML risultante non includerà una dichiarazione XML.</span><span class="sxs-lookup"><span data-stu-id="54475-107">If you are serializing to a string using the `ToString` method, the resulting XML will not include an XML declaration.</span></span>  
  
### <a name="serializing-with-an-xml-declaration"></a><span data-ttu-id="54475-108">Serializzazione con una dichiarazione XML</span><span class="sxs-lookup"><span data-stu-id="54475-108">Serializing with an XML Declaration</span></span>  
 <span data-ttu-id="54475-109">Nell'esempio seguente viene creato un <xref:System.Xml.Linq.XElement>, Salva il documento in un file e quindi stampato il file nella console:</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="54475-109">The following example creates an <xref:System.Xml.Linq.XElement>, saves the document to a file, and then prints the file to the console:</span></span>  
  
```vb  
Dim root As XElement = <Root>  
                           <Child>child content</Child>  
                       </Root>  
root.Save("Root.xml")  
Dim str As String = File.ReadAllText("Root.xml")  
Console.WriteLine(str)  
```  
  
 <span data-ttu-id="54475-110">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="54475-110">This example produces the following output:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Root>  
  <Child>child content</Child>  
</Root>  
```  
  
### <a name="serializing-without-an-xml-declaration"></a><span data-ttu-id="54475-111">Serializzazione senza una dichiarazione XML</span><span class="sxs-lookup"><span data-stu-id="54475-111">Serializing without an XML Declaration</span></span>  
 <span data-ttu-id="54475-112">Nell'esempio seguente viene illustrato come salvare un <xref:System.Xml.Linq.XElement>a un <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="54475-112">The following example shows how to save an <xref:System.Xml.Linq.XElement> to an <xref:System.Xml.XmlWriter>.</span></span>  
  
```vb  
Dim sb As StringBuilder = New StringBuilder()  
Dim xws As XmlWriterSettings = New XmlWriterSettings()  
xws.OmitXmlDeclaration = True  
  
Using xw As XmlWriter = XmlWriter.Create(sb, xws)  
    Dim root = <Root>  
                   <Child>child content</Child>  
               </Root>  
    root.Save(xw)  
End Using  
Console.WriteLine(sb.ToString())  
```  
  
 <span data-ttu-id="54475-113">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="54475-113">This example produces the following output:</span></span>  
  
```xml  
<Root><Child>child content</Child></Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="54475-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54475-114">See Also</span></span>  
 [<span data-ttu-id="54475-115">La serializzazione di strutture ad albero XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="54475-115">Serializing XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
