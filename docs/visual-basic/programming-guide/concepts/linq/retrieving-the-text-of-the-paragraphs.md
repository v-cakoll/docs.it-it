---
title: Recupero del testo dei paragrafi
ms.date: 07/20/2015
ms.assetid: 095fa0d9-7b1b-4cbb-9c13-e2c9d8923d31
ms.openlocfilehash: 0f53eec44e0b11a6c23c7afb4892e4d5d876d6d6
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75341595"
---
# <a name="retrieving-the-text-of-the-paragraphs-visual-basic"></a>Recupero del testo dei paragrafi (Visual Basic)
Questo esempio si basa sull'esempio precedente, [recuperando i paragrafi e i relativi stili (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/retrieving-the-paragraphs-and-their-styles.md). Questo nuovo esempio consente di recuperare il testo di ciascun paragrafo sotto forma di stringa.  
  
 Per recuperare il testo, nell'esempio viene aggiunta un'ulteriore query che scorre la raccolta di tipi anonimi e proietta una nuova raccolta di un tipo anonimo con l'aggiunta di un nuovo membro `Text`. Viene usato l'operatore di query standard <xref:System.Linq.Enumerable.Aggregate%2A> per concatenare più stringhe in un'unica stringa.  
  
 Questa tecnica, che prevede dapprima la proiezione di una raccolta di un tipo anonimo e quindi l'uso di questa raccolta per la proiezione in una nuova raccolta di un tipo anonimo, costituisce un idioma comune e utile. Sarebbe stato possibile scrivere la query senza la proiezione nel primo tipo anonimo, tuttavia, a causa della valutazione lazy, tale tecnica non è più onerosa in termini di potenza di elaborazione. L'idioma crea più oggetti temporanei sull'heap, ma senza influire sostanzialmente sulle prestazioni.  
  
 Sarebbe naturalmente possibile scrivere una singola query che contiene la funzionalità per recuperare i paragrafi, nonché lo stile e il testo di ogni paragrafo. Tuttavia, è spesso utile suddividere una query più complessa in più query perché il codice risultante è più modulare e più facilmente gestibile. Se inoltre è necessario riutilizzare parte della query, risulta più agevole effettuare il refactoring se le query sono scritte in questo modo.  
  
 Queste query, che vengono concatenate insieme, usano il modello di elaborazione esaminato in dettaglio nell'argomento [esercitazione: esecuzione posticipata (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-deferred-execution.md).  
  
## <a name="example"></a>Esempio  
 In questo esempio viene elaborato un documento WordprocessingML, determinando il nodo dell'elemento, il nome dello stile e il testo di ciascun paragrafo. Questo esempio si basa su esempi precedenti di questa esercitazione. La nuova query è indicata nei commenti del codice riportato di seguito.  
  
 Per istruzioni sulla creazione del documento di origine per questo esempio, vedere [creazione del documento Office Open XML di origine (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).  
  
 In questo esempio vengono usate classi dell'assembly WindowsBase e i tipi dello spazio dei nomi <xref:System.IO.Packaging?displayProperty=nameWithType>.  
  
```vb  
Imports <xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main">  
  
Module Module1  
    ' Following function is required because Visual Basic does not support short circuit evaluation  
    Private Function GetStyleOfParagraph(ByVal styleNode As XElement, _  
                                         ByVal defaultStyle As String) As String  
        If (styleNode Is Nothing) Then  
            Return defaultStyle  
        Else  
            Return styleNode.@w:val  
        End If  
    End Function  
  
    Sub Main()  
        Dim fileName = "SampleDoc.docx"  
  
        Dim documentRelationshipType = _  
          "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument"  
        Dim stylesRelationshipType = _  
          "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles"  
        Dim wordmlNamespace = _  
          "http://schemas.openxmlformats.org/wordprocessingml/2006/main"  
  
        Dim xDoc As XDocument = Nothing  
        Dim styleDoc As XDocument = Nothing  
        Using wdPackage As Package = Package.Open(fileName, FileMode.Open, FileAccess.Read)  
            Dim docPackageRelationship As PackageRelationship = _  
              wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault()  
            If (docPackageRelationship IsNot Nothing) Then  
                Dim documentUri As Uri = PackUriHelper.ResolvePartUri(New Uri("/", UriKind.Relative), _  
                  docPackageRelationship.TargetUri)  
                Dim documentPart As PackagePart = wdPackage.GetPart(documentUri)  
  
                '  Load the document XML in the part into an XDocument instance.  
                xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()))  
  
                '  Find the styles part. There will only be one.  
                Dim styleRelation As PackageRelationship = _  
                  documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault()  
                If (styleRelation IsNot Nothing) Then  
                    Dim styleUri As Uri = _  
                      PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri)  
                    Dim stylePart As PackagePart = wdPackage.GetPart(styleUri)  
  
                    '  Load the style XML in the part into an XDocument instance.  
                    styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()))  
                End If  
            End If  
        End Using  
  
        Dim defaultStyle As String = _  
            ( _  
                From style In styleDoc.Root.<w:style> _  
                Where style.@w:type = "paragraph" And _  
                      style.@w:default = "1" _  
                Select style _  
            ).First().@w:styleId  
  
        ' Find all paragraphs in the document.  
        Dim paragraphs = _  
            From para In xDoc.Root.<w:body>...<w:p> _  
        Let styleNode As XElement = para.<w:pPr>.<w:pStyle>.FirstOrDefault _  
        Select New With { _  
            .ParagraphNode = para, _  
            .StyleName = GetStyleOfParagraph(styleNode, defaultStyle) _  
        }  
  
        ' Following is the new query that retrieves the text of  
        ' each paragraph.  
        Dim paraWithText = _  
            From para In paragraphs _  
            Select New With { _  
                .ParagraphNode = para.ParagraphNode, _  
                .StyleName = para.StyleName, _  
                .Text = para.ParagraphNode.<w:r>.<w:t> _  
                    .Aggregate(New StringBuilder(), _  
                               Function(s As StringBuilder, i As String) s.Append(CStr(i)), _  
                               Function(s As StringBuilder) s.ToString) _  
            }  
  
        For Each p In paraWithText  
            Console.WriteLine("StyleName:{0} >{1}<", p.StyleName, p.Text)  
        Next  
  
    End Sub  
End Module  
```  
  
 Questo esempio produce l'output seguente quando viene applicato al documento descritto in [creazione del documento Office Open XML di origine (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).  
  
```console  
StyleName:Heading1 >Parsing WordprocessingML with LINQ to XML<  
StyleName:Normal ><  
StyleName:Normal >The following example prints to the console.<  
StyleName:Normal ><  
StyleName:Code >Imports System<  
StyleName:Code ><  
StyleName:Code >Class Program<  
StyleName:Code >    Public Shared  Sub Main(ByVal args() As String)<  
StyleName:Code >        Console.WriteLine("Hello World")<  
StyleName:Code >   End Sub<  
StyleName:Code >End Class<  
StyleName:Normal ><  
StyleName:Normal >This example produces the following output:<  
StyleName:Normal ><  
StyleName:Code >Hello World<  
```  
  
## <a name="next-steps"></a>Passaggi successivi  
 Nell'esempio successivo viene illustrato come usare un metodo di estensione, anziché <xref:System.Linq.Enumerable.Aggregate%2A>, per concatenare più stringhe in un'unica stringa.  
  
- [Refactoring tramite un metodo di estensione (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/refactoring-using-an-extension-method.md)  
  
## <a name="see-also"></a>Vedere anche

- [Esercitazione: modifica del contenuto in un documento WordprocessingML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)
- [Esecuzione posticipata e valutazione lazy in LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)
