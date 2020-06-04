---
title: 'Procedura: Leggere e scrivere un documento codificato'
ms.date: 07/20/2015
ms.assetid: 159d868f-5ac8-40f2-95ca-07dd925f35c6
ms.openlocfilehash: f66737429950e04f447dfbd58cf47b6434a22976
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397908"
---
# <a name="how-to-read-and-write-an-encoded-document-visual-basic"></a>Procedura: leggere e scrivere un documento codificato (Visual Basic)

Per creare un documento XML codificato, aggiungere un oggetto <xref:System.Xml.Linq.XDeclaration> all'albero XML, impostando la codifica sul nome della tabella codici desiderata.

Qualsiasi valore restituito da <xref:System.Text.Encoding.WebName%2A> è un valore valido.

Se si legge un documento codificato, la proprietà <xref:System.Xml.Linq.XDeclaration.Encoding%2A> verrà impostata sul nome della tabella codici.

Se si imposta <xref:System.Xml.Linq.XDeclaration.Encoding%2A> su un nome di tabella codici valido, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] eseguirà la serializzazione con la codifica specificata.

## <a name="example"></a>Esempio

Nell'esempio seguente vengono creati due documenti, uno con codifica utf-8 e uno con codifica utf-16. Vengono quindi caricati i documenti e viene stampata la codifica nella console.

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

Nell'esempio viene prodotto l'output seguente:

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

## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.Linq.XDeclaration.Encoding%2A?displayProperty=nameWithType>
- [Programmazione LINQ to XML avanzata (Visual Basic)](advanced-linq-to-xml-programming.md)
