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
# <a name="how-to-transform-xml-by-using-linq-visual-basic"></a><span data-ttu-id="77fcf-102">Procedura: Trasformare XML utilizzando LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="77fcf-102">How to: Transform XML by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="77fcf-103">[Valori letterali XML](../../../../visual-basic/language-reference/xml-literals/index.md) semplificano Leggi XML da un'origine e lo trasforma in un nuovo formato XML.</span><span class="sxs-lookup"><span data-stu-id="77fcf-103">[XML Literals](../../../../visual-basic/language-reference/xml-literals/index.md) make it easy to read XML from one source and transform it to a new XML format.</span></span> <span data-ttu-id="77fcf-104">È possibile sfruttare i vantaggi delle query LINQ per recuperare il contenuto per trasformare o modificare il contenuto in un documento esistente in un nuovo formato XML.</span><span class="sxs-lookup"><span data-stu-id="77fcf-104">You can take advantage of LINQ queries to retrieve the content to transform, or change content in an existing document to a new XML format.</span></span>  
  
 <span data-ttu-id="77fcf-105">Nell'esempio riportato in questo argomento consente di trasformare il contenuto da un documento di origine XML in formato HTML da visualizzare in un browser.</span><span class="sxs-lookup"><span data-stu-id="77fcf-105">The example in this topic transforms content from an XML source document to HTML to be viewed in a browser.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-transform-an-xml-document"></a><span data-ttu-id="77fcf-106">Per trasformare un documento XML</span><span class="sxs-lookup"><span data-stu-id="77fcf-106">To transform an XML document</span></span>  
  
1.  <span data-ttu-id="77fcf-107">Creare un nuovo progetto di Visual Basic in Visual Studio, il **applicazione Console** modello di progetto.</span><span class="sxs-lookup"><span data-stu-id="77fcf-107">In Visual Studio, create a new Visual Basic project in the **Console Application** project template.</span></span>  
  
2.  <span data-ttu-id="77fcf-108">Fare doppio clic sul file Module1.vb creato nel progetto per modificare il codice Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="77fcf-108">Double-click the Module1.vb file created in the project to modify the Visual Basic code.</span></span> <span data-ttu-id="77fcf-109">Aggiungere il codice seguente per il `Sub Main` del `Module1` modulo.</span><span class="sxs-lookup"><span data-stu-id="77fcf-109">Add the following code to the `Sub Main` of the `Module1` module.</span></span> <span data-ttu-id="77fcf-110">Questo codice crea il documento XML di origine come un <xref:System.Xml.Linq.XDocument> oggetto.</span><span class="sxs-lookup"><span data-stu-id="77fcf-110">This code creates the source XML document as an <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
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
  
     <span data-ttu-id="77fcf-111">[Procedura: Caricare il documento XML da un File, stringa o Stream](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md).</span><span class="sxs-lookup"><span data-stu-id="77fcf-111">[How to: Load XML from a File, String, or Stream](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md).</span></span>  
  
3.  <span data-ttu-id="77fcf-112">Dopo il codice per creare il documento XML di origine, aggiungere il codice seguente per recuperare tutti i \<Book > elementi dall'oggetto e li trasforma in un documento HTML.</span><span class="sxs-lookup"><span data-stu-id="77fcf-112">After the code to create the source XML document, add the following code to retrieve all the \<Book> elements from the object and transform them into an HTML document.</span></span> <span data-ttu-id="77fcf-113">L'elenco delle \<Book > viene creato con una query LINQ che restituisce una raccolta di elementi <xref:System.Xml.Linq.XElement> gli oggetti che contengono il codice HTML trasformato.</span><span class="sxs-lookup"><span data-stu-id="77fcf-113">The list of \<Book> elements is created by using a LINQ query that returns a collection of <xref:System.Xml.Linq.XElement> objects that contain the transformed HTML.</span></span> <span data-ttu-id="77fcf-114">È possibile usare espressioni incorporate per inserire i valori dal documento di origine nel nuovo formato XML.</span><span class="sxs-lookup"><span data-stu-id="77fcf-114">You can use embedded expressions to put the values from the source document in the new XML format.</span></span>  
  
     <span data-ttu-id="77fcf-115">Il documento HTML risultante viene scritto in un file usando il <xref:System.Xml.Linq.XElement.Save%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="77fcf-115">The resulting HTML document is written to a file by using the <xref:System.Xml.Linq.XElement.Save%2A> method.</span></span>  
  
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
  
4.  <span data-ttu-id="77fcf-116">Dopo aver `Sub Main` dei `Module1`, aggiungere un nuovo metodo (`Sub`) per trasformare un \<descrizione > nodo in formato HTML specificato.</span><span class="sxs-lookup"><span data-stu-id="77fcf-116">After `Sub Main` of `Module1`, add a new method (`Sub`) to transform a \<Description> node into the specified HTML format.</span></span> <span data-ttu-id="77fcf-117">Questo metodo viene chiamato dal codice nel passaggio precedente e viene utilizzato per mantenere il formato del \<descrizione > elementi.</span><span class="sxs-lookup"><span data-stu-id="77fcf-117">This method is called by the code in the previous step and is used to preserve the format of the \<Description> elements.</span></span>  
  
     <span data-ttu-id="77fcf-118">Questo metodo sostituisce gli elementi secondari del \<descrizione > elemento con il linguaggio HTML.</span><span class="sxs-lookup"><span data-stu-id="77fcf-118">This method replaces sub-elements of the \<Description> element with HTML.</span></span> <span data-ttu-id="77fcf-119">Il `ReplaceWith` metodo viene utilizzato per mantenere la posizione degli elementi secondari.</span><span class="sxs-lookup"><span data-stu-id="77fcf-119">The `ReplaceWith` method is used to preserve the location of the sub-elements.</span></span> <span data-ttu-id="77fcf-120">Il contenuto trasformato del \<descrizione > elemento è incluso in un paragrafo HTML (\<p >) elemento.</span><span class="sxs-lookup"><span data-stu-id="77fcf-120">The transformed content of the \<Description> element is included in an HTML paragraph (\<p>) element.</span></span> <span data-ttu-id="77fcf-121">Il <xref:System.Xml.Linq.XContainer.Nodes%2A> proprietà viene utilizzata per recuperare il contenuto trasformato del \<descrizione > elemento.</span><span class="sxs-lookup"><span data-stu-id="77fcf-121">The <xref:System.Xml.Linq.XContainer.Nodes%2A> property is used to retrieve the transformed content of the \<Description> element.</span></span> <span data-ttu-id="77fcf-122">Questo garantisce che i sottoelementi sono incluse nel contenuto trasformato.</span><span class="sxs-lookup"><span data-stu-id="77fcf-122">This ensures that sub-elements are included in the transformed content.</span></span>  
  
     <span data-ttu-id="77fcf-123">Aggiungere il codice seguente dopo `Sub Main` di `Module1`.</span><span class="sxs-lookup"><span data-stu-id="77fcf-123">Add the following code after `Sub Main` of `Module1`.</span></span>  
  
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
  
5.  <span data-ttu-id="77fcf-124">Salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="77fcf-124">Save your changes.</span></span>  
  
6.  <span data-ttu-id="77fcf-125">Premere F5 per eseguire il codice.</span><span class="sxs-lookup"><span data-stu-id="77fcf-125">Press F5 to run the code.</span></span> <span data-ttu-id="77fcf-126">Il documento salvato risultante sarà simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="77fcf-126">The resulting saved document will resemble the following:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="77fcf-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77fcf-127">See also</span></span>
- [<span data-ttu-id="77fcf-128">Valori letterali XML</span><span class="sxs-lookup"><span data-stu-id="77fcf-128">XML Literals</span></span>](../../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="77fcf-129">Modifica di XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="77fcf-129">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
- [<span data-ttu-id="77fcf-130">XML</span><span class="sxs-lookup"><span data-stu-id="77fcf-130">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="77fcf-131">Procedura: Caricare il documento XML da un File, stringa o Stream</span><span class="sxs-lookup"><span data-stu-id="77fcf-131">How to: Load XML from a File, String, or Stream</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)
- [<span data-ttu-id="77fcf-132">LINQ</span><span class="sxs-lookup"><span data-stu-id="77fcf-132">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="77fcf-133">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="77fcf-133">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
