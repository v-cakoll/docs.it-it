---
title: Recupero dei paragrafi e gli stili (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9ed2238-d38e-4ad4-b88b-db7859df9bde
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 95c85b4731a9ada0a6af1a9d825bef9b873e89ee
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="retrieving-the-paragraphs-and-their-styles-visual-basic"></a>Recupero dei paragrafi e gli stili (Visual Basic)
In questo esempio viene scritta una query che recupera i nodi dei paragrafi da un documento WordprocessingML. Viene inoltre identificato lo stile di ciascun paragrafo.  
  
 Questa query si basa su query nell'esempio precedente, [ricerca lo stile del paragrafo predefinito (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/finding-the-default-paragraph-style.md), che consente di recuperare lo stile predefinito dall'elenco di stili. Queste informazioni sono necessarie per consentire alla query di identificare gli stili dei paragrafi per i quali non è stato impostato uno stile in modo esplicito. Gli stili dei paragrafi vengono impostati tramite l'elemento `w:pPr`. Se un paragrafo non contiene tale elemento, verrà formattato con lo stile predefinito.  
  
 In questo argomento viene spiegata l'importanza di alcune parti della query e quindi viene illustrata la query in un esempio completo e funzionante.  
  
## <a name="example"></a>Esempio  
 L'origine della query per recuperare tutti i paragrafi di un documento e i relativi stili è la seguente:  
  
```vb  
xDoc.Root.<w:body>...<w:p>  
```  
  
 Questa espressione è simile all'origine della query nell'esempio precedente, [ricerca lo stile del paragrafo predefinito (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/finding-the-default-paragraph-style.md). La differenza principale è data dall'utilizzo dell'asse <xref:System.Xml.Linq.XContainer.Descendants%2A>, anziché dell'asse <xref:System.Xml.Linq.XContainer.Elements%2A>. La query usa l'asse <xref:System.Xml.Linq.XContainer.Descendants%2A> perché nei documenti suddivisi in sezioni i paragrafi non saranno elementi figlio diretti dell'elemento del corpo, ma si troveranno due livelli più sotto nella gerarchia. Usando l'asse <xref:System.Xml.Linq.XContainer.Descendants%2A>, il codice verrà eseguito correttamente anche se nel documento vengono usate sezioni.  
  
## <a name="example"></a>Esempio  
 La query usa una clausola `Let` per determinare l'elemento che contiene il nodo dello stile. Se non è presente nessun elemento, `styleNode` viene impostato su `Nothing`.  
  
```vb  
Let styleNode As XElement = para.<w:pPr>.<w:pStyle>.FirstOrDefault()  
```  
  
 La clausola `Let` usa dapprima l'asse <xref:System.Xml.Linq.XContainer.Elements%2A> per individuare tutti gli elementi denominati `pPr`, quindi il metodo di estensione <xref:System.Xml.Linq.Extensions.Elements%2A> per individuare tutti gli elementi figlio denominati `pStyle` e infine l'operatore di query standard <xref:System.Linq.Enumerable.FirstOrDefault%2A> per convertire la raccolta in un singleton. Se la raccolta è vuota, `styleNode` viene impostato su `Nothing`. Si tratta di un idioma utile per cercare il nodo dell'elemento discendente `pStyle`. Notare che se il nodo figlio `pPr` non esiste, il codice non viene eseguito e viene generata un'eccezione. `styleNode` viene invece impostato su `Nothing`, che corrisponde al comportamento desiderato della clausola `Let`.  
  
 La query proietta una raccolta di un tipo anonimo con due membri, `StyleName` e `ParagraphNode`.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene elaborato un documento WordprocessingML, recuperandone i nodi dei paragrafi da un documento WordprocessingML. Viene inoltre identificato lo stile di ciascun paragrafo. Questo esempio si basa su esempi precedenti di questa esercitazione. La nuova query è indicata nei commenti del codice riportato di seguito.  
  
 È possibile trovare istruzioni per la creazione del documento di origine per questo esempio in [l'origine documento Office Open XML (Visual Basic) di creazione](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).  
  
 In questo esempio vengono usate classi dell'assembly WindowsBase e i tipi dello spazio dei nomi <xref:System.IO.Packaging?displayProperty=nameWithType>.  
  
```vb  
Imports <xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main">  
  
Module Module1  
    Private Function GetStyleOfParagraph(ByVal styleNode As XElement, ByVal defaultStyle As String) As String  
        If (styleNode Is Nothing) Then  
            Return defaultStyle  
        Else  
            Return styleNode.@w:val  
        End If  
    End Function  
  
    Sub Main()  
        Dim fileName = "SampleDoc.docx"  
  
        Dim documentRelationshipType = "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument"  
        Dim stylesRelationshipType = "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles"  
        Dim wordmlNamespace = "http://schemas.openxmlformats.org/wordprocessingml/2006/main"  
  
        Dim xDoc As XDocument = Nothing  
        Dim styleDoc As XDocument = Nothing  
        Using wdPackage As Package = Package.Open(fileName, FileMode.Open, FileAccess.Read)  
            Dim docPackageRelationship As PackageRelationship = wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault()  
            If (docPackageRelationship IsNot Nothing) Then  
                Dim documentUri As Uri = PackUriHelper.ResolvePartUri(New Uri("/", UriKind.Relative), docPackageRelationship.TargetUri)  
                Dim documentPart As PackagePart = wdPackage.GetPart(documentUri)  
  
                '  Load the document XML in the part into an XDocument instance.  
                xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()))  
  
                '  Find the styles part. There will only be one.  
                Dim styleRelation As PackageRelationship = documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault()  
                If (styleRelation IsNot Nothing) Then  
                    Dim styleUri As Uri = PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri)  
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
  
        ' Following is the new query that finds all paragraphs in the  
        ' document and their styles.  
        Dim paragraphs = _  
            From para In xDoc.Root.<w:body>...<w:p> _  
        Let styleNode As XElement = para.<w:pPr>.<w:pStyle>.FirstOrDefault() _  
        Select New With { _  
            .ParagraphNode = para, _  
            .StyleName = GetStyleOfParagraph(styleNode, defaultStyle) _  
        }  
  
        For Each p In paragraphs  
            Console.WriteLine("StyleName:{0}", p.StyleName)  
        Next  
  
    End Sub  
End Module  
```  
  
 In questo esempio produce il seguente output quando viene applicato al documento descritto in [l'origine documento Office Open XML (Visual Basic) di creazione](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).  
  
```  
StyleName:Heading1  
StyleName:Normal  
StyleName:Normal  
StyleName:Normal  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Code  
StyleName:Normal  
StyleName:Normal  
StyleName:Normal  
StyleName:Code  
```  
  
## <a name="next-steps"></a>Passaggi successivi  
 Nell'argomento successivo, [recuperando il testo dei paragrafi (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/retrieving-the-text-of-the-paragraphs.md), si creerà una query per recuperare il testo dei paragrafi.  
  
## <a name="see-also"></a>Vedere anche  
 [Esercitazione: Manipolazione di contenuto in un documento WordprocessingML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)
