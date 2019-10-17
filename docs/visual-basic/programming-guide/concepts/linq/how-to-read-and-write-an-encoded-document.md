---
title: 'Procedura: leggere e scrivere un documento codificato (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 159d868f-5ac8-40f2-95ca-07dd925f35c6
ms.openlocfilehash: 96a490d6915201b4e1069ae0249dea09d761aea6
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321018"
---
# <a name="how-to-read-and-write-an-encoded-document-visual-basic"></a><span data-ttu-id="49ff8-102">Procedura: leggere e scrivere un documento codificato (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="49ff8-102">How to: Read and Write an Encoded Document (Visual Basic)</span></span>
<span data-ttu-id="49ff8-103">Per creare un documento XML codificato, aggiungere un oggetto <xref:System.Xml.Linq.XDeclaration> all'albero XML, impostando la codifica sul nome della tabella codici desiderata.</span><span class="sxs-lookup"><span data-stu-id="49ff8-103">To create an encoded XML document, you add an <xref:System.Xml.Linq.XDeclaration> to the XML tree, setting the encoding to the desired code page name.</span></span>  
  
 <span data-ttu-id="49ff8-104">Qualsiasi valore restituito da <xref:System.Text.Encoding.WebName%2A> è un valore valido.</span><span class="sxs-lookup"><span data-stu-id="49ff8-104">Any value returned by <xref:System.Text.Encoding.WebName%2A> is a valid value.</span></span>  
  
 <span data-ttu-id="49ff8-105">Se si legge un documento codificato, la proprietà <xref:System.Xml.Linq.XDeclaration.Encoding%2A> verrà impostata sul nome della tabella codici.</span><span class="sxs-lookup"><span data-stu-id="49ff8-105">If you read an encoded document, the <xref:System.Xml.Linq.XDeclaration.Encoding%2A> property will be set to the code page name.</span></span>  
  
 <span data-ttu-id="49ff8-106">Se si imposta <xref:System.Xml.Linq.XDeclaration.Encoding%2A> su un nome di tabella codici valido, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] eseguirà la serializzazione con la codifica specificata.</span><span class="sxs-lookup"><span data-stu-id="49ff8-106">If you set <xref:System.Xml.Linq.XDeclaration.Encoding%2A> to a valid code page name, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] will serialize with the specified encoding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49ff8-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="49ff8-107">Example</span></span>  
 <span data-ttu-id="49ff8-108">Nell'esempio seguente vengono creati due documenti, uno con codifica utf-8 e uno con codifica utf-16.</span><span class="sxs-lookup"><span data-stu-id="49ff8-108">The following example creates two documents, one with utf-8 encoding, and one with utf-16 encoding.</span></span> <span data-ttu-id="49ff8-109">Vengono quindi caricati i documenti e viene stampata la codifica nella console.</span><span class="sxs-lookup"><span data-stu-id="49ff8-109">It then loads the documents and prints the encoding to the console.</span></span>  
  
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
  
 <span data-ttu-id="49ff8-110">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="49ff8-110">This example produces the following output:</span></span>  
  
```console  
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
  
## <a name="see-also"></a><span data-ttu-id="49ff8-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49ff8-111">See also</span></span>

- <xref:System.Xml.Linq.XDeclaration.Encoding%2A?displayProperty=nameWithType>
- [<span data-ttu-id="49ff8-112">Programmazione LINQ to XML avanzata (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="49ff8-112">Advanced LINQ to XML Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
