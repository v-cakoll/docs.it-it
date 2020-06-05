---
title: Ricerca dello stile di paragrafo predefinito
ms.date: 07/20/2015
ms.assetid: 9d094a4a-ec8c-41b0-b7ab-a3deb2a01d45
ms.openlocfilehash: b70ae72c293d00c4f7b7a2601bfd20b85702b6d5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84398077"
---
# <a name="finding-the-default-paragraph-style-visual-basic"></a>Ricerca dello stile di paragrafo predefinito (Visual Basic)
La prima attività dell'esercitazione Modifica di informazioni in un documento WordprocessingML consiste nell'individuare lo stile predefinito dei paragrafi del documento.  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>Descrizione  
 Nell'esempio seguente viene aperto un documento WordprocessingML di Office Open XML, vengono individuate le parti del package relative a documento e stile, quindi viene eseguita una query che trova il nome dello stile predefinito. Per informazioni sui pacchetti di documenti Office Open XML e sulle parti da cui sono costituiti, vedere la pagina relativa ai [Dettagli dei documenti WordprocessingML di Office Open XML (Visual Basic)](details-of-office-open-xml-wordprocessingml-documents.md).  
  
 La query cerca un nodo denominato `w:style` che ha un attributo denominato `w:type` con il valore "paragraph" e un attributo denominato `w:default` con il valore "1". Poiché sarà disponibile un solo nodo XML con questi attributi, la query usa l'operatore <xref:System.Linq.Enumerable.First%2A?displayProperty=nameWithType> per convertire una raccolta in un Singleton. Ottiene quindi il valore dell'attributo con il nome `w:styleId`.  
  
 In questo esempio vengono usate classi dell'assembly WindowsBase e i tipi dello spazio dei nomi <xref:System.IO.Packaging?displayProperty=nameWithType>.  
  
### <a name="code"></a>Codice  
  
```vb  
Imports <xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main">  
  
Module Module1  
  
    Sub Main()  
  
        Const fileName As String = "SampleDoc.docx"  
  
        Const documentRelationshipType As String = _  
          "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument"  
        Const stylesRelationshipType As String = _  
          "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles"  
  
        Dim xDoc As XDocument = Nothing  
        Dim styleDoc As XDocument = Nothing  
  
        Using wdPackage As Package = Package.Open(fileName, FileMode.Open, FileAccess.Read)  
            Dim docPackageRelationship As PackageRelationship = _  
              wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault()  
            If docPackageRelationship IsNot Nothing Then  
                Dim documentUri As Uri = PackUriHelper.ResolvePartUri(New Uri("/", UriKind.Relative), _  
                  docPackageRelationship.TargetUri)  
                Dim documentPart As PackagePart = wdPackage.GetPart(documentUri)  
  
                ' Load the document XML in the part into an XDocument instance.  
                xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()))  
  
                ' Find the styles part. There will only be one.  
                Dim styleRelation As PackageRelationship = _  
                  documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault()  
                If styleRelation IsNot Nothing Then  
                    Dim styleUri As Uri = _  
                      PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri)  
                    Dim stylePart As PackagePart = wdPackage.GetPart(styleUri)  
  
                    ' Load the style XML in the part into an XDocument instance.  
                    styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()))  
                End If  
            End If  
        End Using  
  
        ' The following query finds all the paragraphs that have the default style.  
        Dim defParas As IEnumerable(Of XElement) = _  
            From style In styleDoc.Root.<w:style> _  
            Where style.@w:type.Equals("paragraph") And _  
                   style.@w:default.Equals("1") _  
            Select style  
        ' Then find the style of the first.  
        Dim defaultStyle As String = defParas.First().@w:styleId  
  
        Console.WriteLine("The default style is: " & defaultStyle)  
    End Sub  
End Module  
```  
  
### <a name="comments"></a>Commenti  
 Nell'esempio viene prodotto l'output seguente:  
  
```console  
The default style is: Normal  
```  
  
## <a name="next-steps"></a>Passaggi successivi  
 Nell'esempio successivo verrà creata una query simile che trova tutti i paragrafi in un documento e i relativi stili:  
  
- [Recupero dei paragrafi e dei relativi stili (Visual Basic)](retrieving-the-paragraphs-and-their-styles.md)  
  
## <a name="see-also"></a>Vedere anche

- [Esercitazione: modifica del contenuto in un documento WordprocessingML (Visual Basic)](tutorial-manipulating-content-in-a-wordprocessingml-document.md)
