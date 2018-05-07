---
title: "Procedura: intercettare l'analisi degli errori (Visual Basic)"
ms.date: 07/20/2015
ms.assetid: 22e9068e-ea58-447b-816e-cd1852c11787
ms.openlocfilehash: aa72b914d4640410a4d47ba49e774dcee31a54c0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-catch-parsing-errors-visual-basic"></a>Procedura: intercettare l'analisi degli errori (Visual Basic)
In questo argomento viene illustrato come rilevare XML non corretto o non valido.  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] viene implementato usando <xref:System.Xml.XmlReader>. Se a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] viene passato XML non corretto o non valido, la classe <xref:System.Xml.XmlReader> sottostante genererà un'eccezione. I vari metodi che analizzano il codice XML, ad esempio <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, non intercettano l'eccezione, che può quindi essere intercettata dall'applicazione.  
  
 Si noti che non è possibile ottenere errori di analisi se si usano valori letterali XML. Il compilatore Visual Basic intercetterà errori di XML non corretto o non valido.  
  
## <a name="example"></a>Esempio  
 Nel codice seguente si tenta di analizzare XML non valido:  
  
```vb  
Try  
    Dim contacts As XElement = XElement.Parse("<Contacts>" & vbCrLf & _  
        "    <Contact>" & vbCrLf & _  
        "        <Name>Jim Wilson</Name>" & vbCrLf & _  
        "    </Contact>" & vbCrLf & _  
        "</Contcts>")  
  
    Console.WriteLine(contacts)  
Catch e As System.Xml.XmlException  
    Console.WriteLine(e.Message)  
End Try  
```  
  
 Quando viene eseguito, questo codice genera la seguente eccezione:  
  
```  
The 'Contacts' start tag on line 1 does not match the end tag of 'Contcts'. Line 5, position 13.  
```  
  
 Per informazioni sulle eccezioni che si può prevedere vengano generate dai metodi <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> e <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>, vedere la documentazione relativa a <xref:System.Xml.XmlReader>.  
  
## <a name="see-also"></a>Vedere anche  
 [Analisi XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
