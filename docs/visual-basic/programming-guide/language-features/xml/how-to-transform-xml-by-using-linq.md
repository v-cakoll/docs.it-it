---
title: 'Procedura: Trasformare XML utilizzando LINQ (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], transforming
- LINQ to XML [Visual Basic], transforming XML
ms.assetid: 815687f4-0bc2-4c0b-adc6-d78744aa356f
ms.openlocfilehash: 628af13a4cdea41ade943b69e326ec2d9abcbf1c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536347"
---
# <a name="how-to-transform-xml-by-using-linq-visual-basic"></a>Procedura: Trasformare XML utilizzando LINQ (Visual Basic)
[Valori letterali XML](../../../../visual-basic/language-reference/xml-literals/index.md) semplificano Leggi XML da un'origine e lo trasforma in un nuovo formato XML. È possibile sfruttare i vantaggi delle query LINQ per recuperare il contenuto per trasformare o modificare il contenuto in un documento esistente in un nuovo formato XML.  
  
 Nell'esempio riportato in questo argomento consente di trasformare il contenuto da un documento di origine XML in formato HTML da visualizzare in un browser.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-transform-an-xml-document"></a>Per trasformare un documento XML  
  
1.  Creare un nuovo progetto di Visual Basic in Visual Studio, il **applicazione Console** modello di progetto.  
  
2.  Fare doppio clic sul file Module1.vb creato nel progetto per modificare il codice Visual Basic. Aggiungere il codice seguente per il `Sub Main` del `Module1` modulo. Questo codice crea il documento XML di origine come un <xref:System.Xml.Linq.XDocument> oggetto.  
  
    ```vb  
    Dim catalog =   
      <?xml version="1.0"?>  
        <Catalog>  
          <Book id="bk101">  
            <Author>Garghentini, Davide</Author>  
            <Title>XML Developer's Guide</Title>  
            <Price>44.95</Price>  
            <Description>  
              An in-depth look at creating applications  
              with <technology>XML</technology>. For   
              <audience>beginners</audience> or   
              <audience>advanced</audience> developers.  
            </Description>  
          </Book>  
          <Book id="bk331">  
            <Author>Spencer, Phil</Author>  
            <Title>Developing Applications with Visual Basic .NET</Title>  
            <Price>45.95</Price>  
            <Description>  
              Get the expert insights, practical code samples,   
              and best practices you need   
              to advance your expertise with <technology>Visual   
              Basic .NET</technology>.   
              Learn how to create faster, more reliable applications  
              based on professional,   
              pragmatic guidance by today's top <audience>developers</audience>.  
            </Description>  
          </Book>  
        </Catalog>  
    ```  
  
     [Procedura: Caricare il documento XML da un File, stringa o Stream](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md).  
  
3.  Dopo il codice per creare il documento XML di origine, aggiungere il codice seguente per recuperare tutti i \<Book > elementi dall'oggetto e li trasforma in un documento HTML. L'elenco delle \<Book > viene creato con una query LINQ che restituisce una raccolta di elementi <xref:System.Xml.Linq.XElement> gli oggetti che contengono il codice HTML trasformato. È possibile usare espressioni incorporate per inserire i valori dal documento di origine nel nuovo formato XML.  
  
     Il documento HTML risultante viene scritto in un file usando il <xref:System.Xml.Linq.XElement.Save%2A> (metodo).  
  
    ```vb  
    Dim htmlOutput =   
      <html>  
        <body>  
          <%= From book In catalog.<Catalog>.<Book>   
              Select <div>  
                       <h1><%= book.<Title>.Value %></h1>  
                       <h3><%= "By " & book.<Author>.Value %></h3>  
                        <h3><%= "Price = " & book.<Price>.Value %></h3>  
                        <h2>Description</h2>  
                        <%= TransformDescription(book.<Description>(0)) %>  
                        <hr/>  
                      </div> %>  
        </body>  
      </html>  
  
    htmlOutput.Save("BookDescription.html")  
    ```  
  
4.  Dopo aver `Sub Main` dei `Module1`, aggiungere un nuovo metodo (`Sub`) per trasformare un \<descrizione > nodo in formato HTML specificato. Questo metodo viene chiamato dal codice nel passaggio precedente e viene utilizzato per mantenere il formato del \<descrizione > elementi.  
  
     Questo metodo sostituisce gli elementi secondari del \<descrizione > elemento con il linguaggio HTML. Il `ReplaceWith` metodo viene utilizzato per mantenere la posizione degli elementi secondari. Il contenuto trasformato del \<descrizione > elemento è incluso in un paragrafo HTML (\<p >) elemento. Il <xref:System.Xml.Linq.XContainer.Nodes%2A> proprietà viene utilizzata per recuperare il contenuto trasformato del \<descrizione > elemento. Questo garantisce che i sottoelementi sono incluse nel contenuto trasformato.  
  
     Aggiungere il codice seguente dopo `Sub Main` di `Module1`.  
  
    ```vb  
    Public Function TransformDescription(ByVal desc As XElement) As XElement  
  
      ' Replace <technology> elements with <b>.  
      Dim content = (From element In desc...<technology>).ToList()  
  
      If content.Count > 0 Then  
        For i = 0 To content.Count - 1  
          content(i).ReplaceWith(<b><%= content(i).Value %></b>)  
        Next  
      End If  
  
      ' Replace <audience> elements with <i>.  
      content = (From element In desc...<audience>).ToList()  
  
      If content.Count > 0 Then  
        For i = 0 To content.Count - 1  
          content(i).ReplaceWith(<i><%= content(i).Value %></i>)  
        Next  
      End If  
  
      ' Return the updated contents of the <Description> element.  
      Return <p><%= desc.Nodes %></p>  
    End Function  
    ```  
  
5.  Salvare le modifiche.  
  
6.  Premere F5 per eseguire il codice. Il documento salvato risultante sarà simile al seguente:  
  
    ```  
    <?xml version="1.0"?>  
    <html>  
      <body>  
        <div>  
          <h1>XML Developer's Guide</h1>  
          <h3>By Garghentini, Davide</h3>  
          <h3>Price = 44.95</h3>  
          <h2>Description</h2>  
          <p>  
            An in-depth look at creating applications  
            with <b>XML</b>. For   
            <i>beginners</i> or   
            <i>advanced</i> developers.  
          </p>  
          <hr />  
        </div>  
        <div>  
          <h1>Developing Applications with Visual Basic .NET</h1>  
          <h3>By Spencer, Phil</h3>  
          <h3>Price = 45.95</h3>  
          <h2>Description</h2>  
          <p>  
            Get the expert insights, practical code   
            samples, and best practices you need   
            to advance your expertise with <b>Visual   
            Basic .NET</b>. Learn how to create faster,  
            more reliable applications based on  
            professional, pragmatic guidance by today's   
            top <i>developers</i>.  
          </p>  
          <hr />  
        </div>  
      </body>  
    </html>  
    ```  
  
## <a name="see-also"></a>Vedere anche
- [Valori letterali XML](../../../../visual-basic/language-reference/xml-literals/index.md)
- [Modifica di XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [Procedura: Caricare il documento XML da un File, stringa o Stream](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
