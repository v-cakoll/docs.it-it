---
title: 'Procedura: leggere e scrivere un documento codificato (Visual Basic) | Documenti di Microsoft'
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
ms.assetid: 159d868f-5ac8-40f2-95ca-07dd925f35c6
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
ms.openlocfilehash: 5bfc825ca32aaa365b7cc2d0347834a796d3598b
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-read-and-write-an-encoded-document-visual-basic"></a><span data-ttu-id="172ed-102">Procedura: leggere e scrivere un documento codificato (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="172ed-102">How to: Read and Write an Encoded Document (Visual Basic)</span></span>
<span data-ttu-id="172ed-103">Per creare un documento XML codificato, aggiungere un <xref:System.Xml.Linq.XDeclaration>all'albero XML, impostando la codifica per il nome della tabella codici desiderata.</xref:System.Xml.Linq.XDeclaration></span><span class="sxs-lookup"><span data-stu-id="172ed-103">To create an encoded XML document, you add an <xref:System.Xml.Linq.XDeclaration> to the XML tree, setting the encoding to the desired code page name.</span></span>  
  
 <span data-ttu-id="172ed-104">Qualsiasi valore restituito da <xref:System.Text.Encoding.WebName%2A>è un valore valido.</xref:System.Text.Encoding.WebName%2A></span><span class="sxs-lookup"><span data-stu-id="172ed-104">Any value returned by <xref:System.Text.Encoding.WebName%2A> is a valid value.</span></span>  
  
 <span data-ttu-id="172ed-105">Se si legge un documento codificato, la <xref:System.Xml.Linq.XDeclaration.Encoding%2A>verrà impostata per il nome della tabella codici.</xref:System.Xml.Linq.XDeclaration.Encoding%2A></span><span class="sxs-lookup"><span data-stu-id="172ed-105">If you read an encoded document, the <xref:System.Xml.Linq.XDeclaration.Encoding%2A> property will be set to the code page name.</span></span>  
  
 <span data-ttu-id="172ed-106">Se si imposta <xref:System.Xml.Linq.XDeclaration.Encoding%2A>a un nome di tabella codici valido, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] serializzerà con la codifica specificata.</xref:System.Xml.Linq.XDeclaration.Encoding%2A></span><span class="sxs-lookup"><span data-stu-id="172ed-106">If you set <xref:System.Xml.Linq.XDeclaration.Encoding%2A> to a valid code page name, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] will serialize with the specified encoding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="172ed-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="172ed-107">Example</span></span>  
 <span data-ttu-id="172ed-108">Nell'esempio seguente vengono creati due documenti, uno con codifica utf-8 e uno con codifica utf-16.</span><span class="sxs-lookup"><span data-stu-id="172ed-108">The following example creates two documents, one with utf-8 encoding, and one with utf-16 encoding.</span></span> <span data-ttu-id="172ed-109">Vengono quindi caricati i documenti e viene stampata la codifica nella console.</span><span class="sxs-lookup"><span data-stu-id="172ed-109">It then loads the documents and prints the encoding to the console.</span></span>  
  
```vb  
Console.WriteLine("Creating a document with utf-8 encoding")  
Dim encodedDoc8 As XDocument = _  
        <?xml version='1.0' encoding='utf-8' standalone='yes'?>  
        <Root>Content</Root>   
  
encodedDoc8.Save("EncodedUtf8.xml")  
Console.WriteLine("Encoding is:{0}", encodedDoc8.Declaration.Encoding)  
Console.WriteLine()  
  
Console.WriteLine("Creating a document with utf-16 encoding")  
Dim encodedDoc16 As XDocument = _  
        <?xml version='1.0' encoding='utf-16' standalone='yes'?>  
        <Root>Content</Root>  
  
encodedDoc16.Save("EncodedUtf16.xml")  
Console.WriteLine("Encoding is:{0}", encodedDoc16.Declaration.Encoding)  
Console.WriteLine()  
  
Dim newDoc8 As XDocument = XDocument.Load("EncodedUtf8.xml")  
Console.WriteLine("Encoded document:")  
Console.WriteLine(File.ReadAllText("EncodedUtf8.xml"))  
Console.WriteLine()  
Console.WriteLine("Encoding of loaded document is:{0}", newDoc8.Declaration.Encoding)  
Console.WriteLine()  
  
Dim newDoc16 As XDocument = XDocument.Load("EncodedUtf16.xml")  
Console.WriteLine("Encoded document:")  
Console.WriteLine(File.ReadAllText("EncodedUtf16.xml"))  
Console.WriteLine()  
Console.WriteLine("Encoding of loaded document is:{0}", newDoc16.Declaration.Encoding)  
```  
  
 <span data-ttu-id="172ed-110">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="172ed-110">This example produces the following output:</span></span>  
  
```  
Creating a document with utf-8 encoding  
Encoding is:utf-8  
  
Creating a document with utf-16 encoding  
Encoding is:utf-16  
  
Encoded document:  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<Root>Content</Root>  
  
Encoding of loaded document is:utf-8  
  
Encoded document:  
<?xml version="1.0" encoding="utf-16" standalone="yes"?>  
<Root>Content</Root>  
  
Encoding of loaded document is:utf-16  
```  
  
## <a name="see-also"></a><span data-ttu-id="172ed-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="172ed-111">See Also</span></span>  
 <span data-ttu-id="172ed-112"><xref:System.Xml.Linq.XDeclaration.Encoding%2A?displayProperty=fullName></xref:System.Xml.Linq.XDeclaration.Encoding%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="172ed-112"><xref:System.Xml.Linq.XDeclaration.Encoding%2A?displayProperty=fullName></span></span>   
<span data-ttu-id="172ed-113"> [LINQ to XML (Visual Basic) di programmazione avanzata](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)</span><span class="sxs-lookup"><span data-stu-id="172ed-113"> [Advanced LINQ to XML Programming (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)</span></span>
