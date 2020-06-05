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
# <a name="how-to-transform-xml-by-using-linq-visual-basic"></a><span data-ttu-id="7ac39-102">Procedura: trasformare XML utilizzando LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7ac39-102">How to: Transform XML by Using LINQ (Visual Basic)</span></span>

<span data-ttu-id="7ac39-103">I [valori letterali XML](../../../language-reference/xml-literals/index.md) semplificano la lettura di XML da un'origine e la loro trasformazione in un nuovo formato XML.</span><span class="sxs-lookup"><span data-stu-id="7ac39-103">[XML Literals](../../../language-reference/xml-literals/index.md) make it easy to read XML from one source and transform it to a new XML format.</span></span> <span data-ttu-id="7ac39-104">È possibile utilizzare le query LINQ per recuperare il contenuto da trasformare o per modificare il contenuto di un documento esistente in un nuovo formato XML.</span><span class="sxs-lookup"><span data-stu-id="7ac39-104">You can take advantage of LINQ queries to retrieve the content to transform, or change content in an existing document to a new XML format.</span></span>

<span data-ttu-id="7ac39-105">Nell'esempio riportato in questo argomento viene trasformato il contenuto di un documento di origine XML in HTML per essere visualizzato in un browser.</span><span class="sxs-lookup"><span data-stu-id="7ac39-105">The example in this topic transforms content from an XML source document to HTML to be viewed in a browser.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

### <a name="to-transform-an-xml-document"></a><span data-ttu-id="7ac39-106">Per trasformare un documento XML</span><span class="sxs-lookup"><span data-stu-id="7ac39-106">To transform an XML document</span></span>

1. <span data-ttu-id="7ac39-107">In Visual Studio creare un nuovo progetto Visual Basic nel modello di progetto **applicazione console** .</span><span class="sxs-lookup"><span data-stu-id="7ac39-107">In Visual Studio, create a new Visual Basic project in the **Console Application** project template.</span></span>

2. <span data-ttu-id="7ac39-108">Fare doppio clic sul file Module1. vb creato nel progetto per modificare il codice Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="7ac39-108">Double-click the Module1.vb file created in the project to modify the Visual Basic code.</span></span> <span data-ttu-id="7ac39-109">Aggiungere il codice seguente all'oggetto `Sub Main` del `Module1` modulo.</span><span class="sxs-lookup"><span data-stu-id="7ac39-109">Add the following code to the `Sub Main` of the `Module1` module.</span></span> <span data-ttu-id="7ac39-110">Questo codice crea il documento XML di origine come <xref:System.Xml.Linq.XDocument> oggetto.</span><span class="sxs-lookup"><span data-stu-id="7ac39-110">This code creates the source XML document as an <xref:System.Xml.Linq.XDocument> object.</span></span>

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

     <span data-ttu-id="7ac39-111">[Procedura: caricare XML da un file, da una stringa o da un flusso](how-to-load-xml-from-a-file-string-or-stream.md).</span><span class="sxs-lookup"><span data-stu-id="7ac39-111">[How to: Load XML from a File, String, or Stream](how-to-load-xml-from-a-file-string-or-stream.md).</span></span>

3. <span data-ttu-id="7ac39-112">Dopo il codice per creare il documento XML di origine, aggiungere il codice seguente per recuperare tutti gli \<Book> elementi dall'oggetto e trasformarli in un documento HTML.</span><span class="sxs-lookup"><span data-stu-id="7ac39-112">After the code to create the source XML document, add the following code to retrieve all the \<Book> elements from the object and transform them into an HTML document.</span></span> <span data-ttu-id="7ac39-113">L'elenco di \<Book> elementi viene creato usando una query LINQ che restituisce una raccolta di <xref:System.Xml.Linq.XElement> oggetti che contengono il codice HTML trasformato.</span><span class="sxs-lookup"><span data-stu-id="7ac39-113">The list of \<Book> elements is created by using a LINQ query that returns a collection of <xref:System.Xml.Linq.XElement> objects that contain the transformed HTML.</span></span> <span data-ttu-id="7ac39-114">È possibile utilizzare le espressioni incorporate per inserire i valori dal documento di origine nel nuovo formato XML.</span><span class="sxs-lookup"><span data-stu-id="7ac39-114">You can use embedded expressions to put the values from the source document in the new XML format.</span></span>

     <span data-ttu-id="7ac39-115">Il documento HTML risultante viene scritto in un file usando il <xref:System.Xml.Linq.XElement.Save%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="7ac39-115">The resulting HTML document is written to a file by using the <xref:System.Xml.Linq.XElement.Save%2A> method.</span></span>

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

4. <span data-ttu-id="7ac39-116">Dopo `Sub Main` di `Module1` , aggiungere un nuovo metodo ( `Sub` ) per trasformare un \<Description> nodo nel formato HTML specificato.</span><span class="sxs-lookup"><span data-stu-id="7ac39-116">After `Sub Main` of `Module1`, add a new method (`Sub`) to transform a \<Description> node into the specified HTML format.</span></span> <span data-ttu-id="7ac39-117">Questo metodo viene chiamato dal codice nel passaggio precedente e viene usato per mantenere il formato degli \<Description> elementi.</span><span class="sxs-lookup"><span data-stu-id="7ac39-117">This method is called by the code in the previous step and is used to preserve the format of the \<Description> elements.</span></span>

     <span data-ttu-id="7ac39-118">Questo metodo sostituisce gli elementi secondari dell' \<Description> elemento con HTML.</span><span class="sxs-lookup"><span data-stu-id="7ac39-118">This method replaces sub-elements of the \<Description> element with HTML.</span></span> <span data-ttu-id="7ac39-119">Il `ReplaceWith` metodo viene usato per mantenere la posizione dei sottoelementi.</span><span class="sxs-lookup"><span data-stu-id="7ac39-119">The `ReplaceWith` method is used to preserve the location of the sub-elements.</span></span> <span data-ttu-id="7ac39-120">Il contenuto trasformato dell' \<Description> elemento è incluso in un elemento Paragraph ( \<p> ) HTML.</span><span class="sxs-lookup"><span data-stu-id="7ac39-120">The transformed content of the \<Description> element is included in an HTML paragraph (\<p>) element.</span></span> <span data-ttu-id="7ac39-121">La <xref:System.Xml.Linq.XContainer.Nodes%2A> proprietà viene utilizzata per recuperare il contenuto trasformato dell' \<Description> elemento.</span><span class="sxs-lookup"><span data-stu-id="7ac39-121">The <xref:System.Xml.Linq.XContainer.Nodes%2A> property is used to retrieve the transformed content of the \<Description> element.</span></span> <span data-ttu-id="7ac39-122">In questo modo si garantisce che gli elementi secondari vengano inclusi nel contenuto trasformato.</span><span class="sxs-lookup"><span data-stu-id="7ac39-122">This ensures that sub-elements are included in the transformed content.</span></span>

     <span data-ttu-id="7ac39-123">Aggiungere il codice seguente dopo `Sub Main` di `Module1` .</span><span class="sxs-lookup"><span data-stu-id="7ac39-123">Add the following code after `Sub Main` of `Module1`.</span></span>

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

5. <span data-ttu-id="7ac39-124">Salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="7ac39-124">Save your changes.</span></span>

6. <span data-ttu-id="7ac39-125">Premere F5 per eseguire il codice.</span><span class="sxs-lookup"><span data-stu-id="7ac39-125">Press F5 to run the code.</span></span> <span data-ttu-id="7ac39-126">Il documento salvato risultante sarà simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="7ac39-126">The resulting saved document will resemble the following:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="7ac39-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ac39-127">See also</span></span>

- [<span data-ttu-id="7ac39-128">Valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="7ac39-128">XML Literals</span></span>](../../../language-reference/xml-literals/index.md)
- [<span data-ttu-id="7ac39-129">Modifica di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7ac39-129">Manipulating XML in Visual Basic</span></span>](manipulating-xml.md)
- [<span data-ttu-id="7ac39-130">XML</span><span class="sxs-lookup"><span data-stu-id="7ac39-130">XML</span></span>](index.md)
- [<span data-ttu-id="7ac39-131">Procedura: caricare XML da un file, da una stringa o da un flusso</span><span class="sxs-lookup"><span data-stu-id="7ac39-131">How to: Load XML from a File, String, or Stream</span></span>](how-to-load-xml-from-a-file-string-or-stream.md)
- [<span data-ttu-id="7ac39-132">LINQ</span><span class="sxs-lookup"><span data-stu-id="7ac39-132">LINQ</span></span>](../linq/index.md)
- [<span data-ttu-id="7ac39-133">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7ac39-133">Introduction to LINQ in Visual Basic</span></span>](../linq/introduction-to-linq.md)
