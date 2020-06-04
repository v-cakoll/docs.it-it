---
title: 'Procedura: Recuperare una raccolta di attributi (LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: a07e9645-b45b-403b-b698-f652f904c7d2
ms.openlocfilehash: be7abac736f9a70ae3f0c9efe2074cfe79821ddb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397882"
---
# <a name="how-to-retrieve-a-collection-of-attributes-linq-to-xml-visual-basic"></a>Procedura: recuperare una raccolta di attributi (LINQ to XML) (Visual Basic)
In questo argomento viene descritto il metodo <xref:System.Xml.Linq.XElement.Attributes%2A>, che consente di recuperare gli attributi di un elemento.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come scorrere la raccolta di attributi di un elemento.  
  
```vb  
Dim val = _  
    <Value ID="1243" Type="int" ConvertableTo="double">100</Value>  
Dim listOfAttributes As IEnumerable(Of XAttribute) = _  
    From att In val.Attributes() _  
    Select att  
For Each att As XAttribute In listOfAttributes  
    Console.WriteLine(att)  
Next  
```  
  
 L'output del codice è il seguente:  
  
```console  
ID="1243"  
Type="int"  
ConvertableTo="double"  
```  
  
## <a name="see-also"></a>Vedere anche

- [Assi LINQ to XML (Visual Basic)](linq-to-xml-axes.md)
