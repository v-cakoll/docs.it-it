---
title: Come leggere e scrivere un documento codificato (C
ms.date: 07/20/2015
ms.assetid: 84f64e71-39a6-42c6-ad68-f052bb158a03
ms.openlocfilehash: fa28c26845a0c6019943e0532ea0692a6dffd5a9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75347673"
---
# <a name="how-to-read-and-write-an-encoded-document-c"></a>Come leggere e scrivere un documento codificato (C
Per creare un documento XML codificato, aggiungere un oggetto <xref:System.Xml.Linq.XDeclaration> all'albero XML, impostando la codifica sul nome della tabella codici desiderata.  
  
 Qualsiasi valore restituito da <xref:System.Text.Encoding.WebName%2A> è un valore valido.  
  
 Se si legge un documento codificato, la proprietà <xref:System.Xml.Linq.XDeclaration.Encoding%2A> verrà impostata sul nome della tabella codici.  
  
 Se si imposta <xref:System.Xml.Linq.XDeclaration.Encoding%2A> su un nome di tabella codici valido, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] eseguirà la serializzazione con la codifica specificata.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono creati due documenti, uno con codifica utf-8 e uno con codifica utf-16. Vengono quindi caricati i documenti e viene stampata la codifica nella console.  
  
```csharp  
Console.WriteLine("Creating a document with utf-8 encoding");  
XDocument encodedDoc8 = new XDocument(  
    new XDeclaration("1.0", "utf-8", "yes"),  
    new XElement("Root", "Content")  
);  
encodedDoc8.Save("EncodedUtf8.xml");  
Console.WriteLine("Encoding is:{0}", encodedDoc8.Declaration.Encoding);  
Console.WriteLine();  
  
Console.WriteLine("Creating a document with utf-16 encoding");  
XDocument encodedDoc16 = new XDocument(  
    new XDeclaration("1.0", "utf-16", "yes"),  
    new XElement("Root", "Content")  
);  
encodedDoc16.Save("EncodedUtf16.xml");  
Console.WriteLine("Encoding is:{0}", encodedDoc16.Declaration.Encoding);  
Console.WriteLine();  
  
XDocument newDoc8 = XDocument.Load("EncodedUtf8.xml");  
Console.WriteLine("Encoded document:");  
Console.WriteLine(File.ReadAllText("EncodedUtf8.xml"));  
Console.WriteLine();  
Console.WriteLine("Encoding of loaded document is:{0}", newDoc8.Declaration.Encoding);  
Console.WriteLine();  
  
XDocument newDoc16 = XDocument.Load("EncodedUtf16.xml");  
Console.WriteLine("Encoded document:");  
Console.WriteLine(File.ReadAllText("EncodedUtf16.xml"));  
Console.WriteLine();  
Console.WriteLine("Encoding of loaded document is:{0}", newDoc16.Declaration.Encoding);  
```  
  
 Nell'esempio viene prodotto l'output seguente:  
  
```output  
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
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.Linq.XDeclaration.Encoding%2A?displayProperty=nameWithType>
