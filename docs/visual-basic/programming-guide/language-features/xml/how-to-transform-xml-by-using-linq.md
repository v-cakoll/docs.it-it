---
title: 'Procedura: trasformare XML utilizzando LINQ'
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], transforming
- LINQ to XML [Visual Basic], transforming XML
ms.assetid: 815687f4-0bc2-4c0b-adc6-d78744aa356f
ms.openlocfilehash: dab394ec45567589e002b5d2ac76ec19fb0f76c6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84374882"
---
# <a name="how-to-transform-xml-by-using-linq-visual-basic"></a>Procedura: trasformare XML utilizzando LINQ (Visual Basic)

I [valori letterali XML](../../../language-reference/xml-literals/index.md) semplificano la lettura di XML da un'origine e la loro trasformazione in un nuovo formato XML. È possibile utilizzare le query LINQ per recuperare il contenuto da trasformare o per modificare il contenuto di un documento esistente in un nuovo formato XML.

Nell'esempio riportato in questo argomento viene trasformato il contenuto di un documento di origine XML in HTML per essere visualizzato in un browser.

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

### <a name="to-transform-an-xml-document"></a>Per trasformare un documento XML

1. In Visual Studio creare un nuovo progetto Visual Basic nel modello di progetto **applicazione console** .

2. Fare doppio clic sul file Module1. vb creato nel progetto per modificare il codice Visual Basic. Aggiungere il codice seguente all'oggetto `Sub Main` del `Module1` modulo. Questo codice crea il documento XML di origine come <xref:System.Xml.Linq.XDocument> oggetto.

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

     [Procedura: caricare XML da un file, da una stringa o da un flusso](how-to-load-xml-from-a-file-string-or-stream.md).

3. Dopo il codice per creare il documento XML di origine, aggiungere il codice seguente per recuperare tutti gli \<Book> elementi dall'oggetto e trasformarli in un documento HTML. L'elenco di \<Book> elementi viene creato usando una query LINQ che restituisce una raccolta di <xref:System.Xml.Linq.XElement> oggetti che contengono il codice HTML trasformato. È possibile utilizzare le espressioni incorporate per inserire i valori dal documento di origine nel nuovo formato XML.

     Il documento HTML risultante viene scritto in un file usando il <xref:System.Xml.Linq.XElement.Save%2A> metodo.

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

4. Dopo `Sub Main` di `Module1` , aggiungere un nuovo metodo ( `Sub` ) per trasformare un \<Description> nodo nel formato HTML specificato. Questo metodo viene chiamato dal codice nel passaggio precedente e viene usato per mantenere il formato degli \<Description> elementi.

     Questo metodo sostituisce gli elementi secondari dell' \<Description> elemento con HTML. Il `ReplaceWith` metodo viene usato per mantenere la posizione dei sottoelementi. Il contenuto trasformato dell' \<Description> elemento è incluso in un elemento Paragraph ( \<p> ) HTML. La <xref:System.Xml.Linq.XContainer.Nodes%2A> proprietà viene utilizzata per recuperare il contenuto trasformato dell' \<Description> elemento. In questo modo si garantisce che gli elementi secondari vengano inclusi nel contenuto trasformato.

     Aggiungere il codice seguente dopo `Sub Main` di `Module1` .

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

5. Salvare le modifiche.

6. Premere F5 per eseguire il codice. Il documento salvato risultante sarà simile al seguente:

    ```html
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

- [Valori letterali XML](../../../language-reference/xml-literals/index.md)
- [Modifica di XML in Visual Basic](manipulating-xml.md)
- [XML](index.md)
- [Procedura: caricare XML da un file, da una stringa o da un flusso](how-to-load-xml-from-a-file-string-or-stream.md)
- [LINQ](../linq/index.md)
- [Introduzione a LINQ in Visual Basic](../linq/introduction-to-linq.md)
