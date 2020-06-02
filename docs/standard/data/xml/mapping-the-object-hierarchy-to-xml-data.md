---
title: Mapping della gerarchia di oggetti in dati XML
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 450e350b-6a68-4634-a2a5-33f4dc33baf0
ms.openlocfilehash: 8507c4b323f97279c3054b76aaf8d52f14f0d4ad
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289135"
---
# <a name="mapping-the-object-hierarchy-to-xml-data"></a><span data-ttu-id="070b2-102">Mapping della gerarchia di oggetti in dati XML</span><span class="sxs-lookup"><span data-stu-id="070b2-102">Mapping the Object Hierarchy to XML Data</span></span>
<span data-ttu-id="070b2-103">Quando un documento XML è in memoria, la rappresentazione concettuale è un albero.</span><span class="sxs-lookup"><span data-stu-id="070b2-103">When an XML document is in memory, the conceptual representation is a tree.</span></span> <span data-ttu-id="070b2-104">Nella programmazione, è possibile accedere ai nodi dell'albero mediante una gerarchia di oggetti.</span><span class="sxs-lookup"><span data-stu-id="070b2-104">For programming, you have an object hierarchy to access the nodes of the tree.</span></span> <span data-ttu-id="070b2-105">Nell'esempio seguente viene illustrato come il contenuto XML viene convertito in nodi.</span><span class="sxs-lookup"><span data-stu-id="070b2-105">The following example shows you how the XML content becomes nodes.</span></span>  
  
 <span data-ttu-id="070b2-106">Mentre il codice XML viene letto nel DOM (Document Object Model) XML, i dati sono convertiti in nodi in cui vengono conservati metadati aggiuntivi, quali il tipo di nodo e i relativi valori.</span><span class="sxs-lookup"><span data-stu-id="070b2-106">As the XML is read into the XML Document Object Model (DOM), the pieces are translated into nodes, and these nodes retain additional metadata about themselves, such as their node type and values.</span></span> <span data-ttu-id="070b2-107">Il tipo di nodo corrisponde al relativo oggetto e determina le operazioni che possono essere eseguite e le proprietà che possono essere impostate o recuperate.</span><span class="sxs-lookup"><span data-stu-id="070b2-107">The node type is its object and is what determines what actions can be performed and what properties can be set or retrieved.</span></span>  
  
 <span data-ttu-id="070b2-108">Si consideri ad esempio il seguente codice XML:</span><span class="sxs-lookup"><span data-stu-id="070b2-108">If you have the following simple XML:</span></span>  
  
 <span data-ttu-id="070b2-109">**Input**</span><span class="sxs-lookup"><span data-stu-id="070b2-109">**Input**</span></span>  
  
```xml  
<book>  
    <title>The Handmaid's Tale</title>  
</book>  
```  
  
 <span data-ttu-id="070b2-110">L'input è rappresentato in memoria come il seguente albero di nodi con la proprietà del tipo di nodo associata:</span><span class="sxs-lookup"><span data-stu-id="070b2-110">The input is represented in memory as the following node tree with the assigned node type property:</span></span>  
  
 <span data-ttu-id="070b2-111">![Albero nodo esempio](media/simple-xml.gif "Simple_XML")</span><span class="sxs-lookup"><span data-stu-id="070b2-111">![example node tree](media/simple-xml.gif "Simple_XML")</span></span>  
<span data-ttu-id="070b2-112">Rappresentazione dell'albero dei nodi Book e Title</span><span class="sxs-lookup"><span data-stu-id="070b2-112">Book and title node tree representation</span></span>  
  
 <span data-ttu-id="070b2-113">L'elemento `book` viene convertito in un oggetto **XmlElement**, l'elemento successivo `title` viene convertito anch'esso in **XmlElement**, mentre il contenuto degli elementi viene convertito in un oggetto **XmlText**.</span><span class="sxs-lookup"><span data-stu-id="070b2-113">The `book` element becomes an **XmlElement** object, the next element, `title`, also becomes an **XmlElement**, while the element content becomes an **XmlText** object.</span></span> <span data-ttu-id="070b2-114">Osservando i metodi e le proprietà **XmlElement**, si può notare che questi sono diversi dai metodi e dalle proprietà disponibili in un oggetto **XmlText**.</span><span class="sxs-lookup"><span data-stu-id="070b2-114">In looking at the **XmlElement** methods and properties, the methods and properties are different than the methods and properties available on an **XmlText** object.</span></span> <span data-ttu-id="070b2-115">È quindi fondamentale sapere quale tipo di nodo diventerà il markup XML, perché in base a questo vengono determinate le operazioni che possono essere eseguite.</span><span class="sxs-lookup"><span data-stu-id="070b2-115">So knowing what node type the XML markup becomes is vital, as its node type determines the actions that can be performed.</span></span>  
  
 <span data-ttu-id="070b2-116">Nell'esempio seguente vengono letti i dati XML e viene scritto un testo diverso a seconda del tipo di nodo,</span><span class="sxs-lookup"><span data-stu-id="070b2-116">The following example reads in XML data and writes out different text, depending on the node type.</span></span> <span data-ttu-id="070b2-117">usando come input il file di dati XML **items.xml**:</span><span class="sxs-lookup"><span data-stu-id="070b2-117">Using the following XML data file as input, **items.xml**:</span></span>  
  
 <span data-ttu-id="070b2-118">**Input**</span><span class="sxs-lookup"><span data-stu-id="070b2-118">**Input**</span></span>  
  
```xml  
<?xml version="1.0"?>  
<!-- This is a sample XML document -->  
<!DOCTYPE Items [<!ENTITY number "123">]>  
<Items>  
  <Item>Test with an entity: &number;</Item>  
  <Item>test with a child element <more/> stuff</Item>  
  <Item>test with a CDATA section <![CDATA[<456>]]> def</Item>  
  <Item>Test with a char entity: A</Item>  
  <!-- Fourteen chars in this element.-->  
  <Item>1234567890ABCD</Item>  
</Items>  
```  
  
 <span data-ttu-id="070b2-119">L'esempio di codice seguente legge il file **items.xml** e visualizza le informazioni per ogni tipo di nodo.</span><span class="sxs-lookup"><span data-stu-id="070b2-119">The following code example reads the **items.xml** file and displays information for each node type.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
  
Public Class Sample  
    Private Const filename As String = "items.xml"  
  
    Public Shared Sub Main()  
  
        Dim reader As XmlTextReader = Nothing  
  
        Try  
            ' Load the reader with the data file and
            'ignore all white space nodes.
            reader = New XmlTextReader(filename)  
            reader.WhitespaceHandling = WhitespaceHandling.None  
  
            ' Parse the file and display each of the nodes.  
            While reader.Read()  
                Select Case reader.NodeType  
                    Case XmlNodeType.Element  
                        Console.Write("<{0}>", reader.Name)  
                    Case XmlNodeType.Text  
                        Console.Write(reader.Value)  
                    Case XmlNodeType.CDATA  
                        Console.Write("<![CDATA[{0}]]>", reader.Value)  
                    Case XmlNodeType.ProcessingInstruction  
                        Console.Write("<?{0} {1}?>", reader.Name, reader.Value)  
                    Case XmlNodeType.Comment  
                        Console.Write("<!--{0}-->", reader.Value)  
                    Case XmlNodeType.XmlDeclaration  
                        Console.Write("<?xml version='1.0'?>")  
                    Case XmlNodeType.Document  
                    Case XmlNodeType.DocumentType  
                        Console.Write("<!DOCTYPE {0} [{1}]", reader.Name, reader.Value)  
                    Case XmlNodeType.EntityReference  
                        Console.Write(reader.Name)  
                    Case XmlNodeType.EndElement  
                        Console.Write("</{0}>", reader.Name)  
                End Select  
            End While  
  
        Finally  
            If Not (reader Is Nothing) Then  
                reader.Close()  
            End If  
        End Try  
    End Sub 'Main ' End class  
End Class 'Sample  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
  
public class Sample  
{  
    private const String filename = "items.xml";  
  
    public static void Main()  
    {  
        XmlTextReader reader = null;  
  
        try  
        {  
            // Load the reader with the data file and ignore
            // all white space nodes.  
            reader = new XmlTextReader(filename);  
            reader.WhitespaceHandling = WhitespaceHandling.None;  
  
            // Parse the file and display each of the nodes.  
            while (reader.Read())  
            {  
                switch (reader.NodeType)  
                {  
                    case XmlNodeType.Element:  
                        Console.Write("<{0}>", reader.Name);  
                        break;  
                    case XmlNodeType.Text:  
                        Console.Write(reader.Value);  
                        break;  
                    case XmlNodeType.CDATA:  
                        Console.Write("<![CDATA[{0}]]>", reader.Value);  
                        break;  
                    case XmlNodeType.ProcessingInstruction:  
                        Console.Write("<?{0} {1}?>", reader.Name, reader.Value);  
                        break;  
                    case XmlNodeType.Comment:  
                        Console.Write("<!--{0}-->", reader.Value);  
                        break;  
                    case XmlNodeType.XmlDeclaration:  
                        Console.Write("<?xml version='1.0'?>");  
                        break;  
                    case XmlNodeType.Document:  
                        break;  
                    case XmlNodeType.DocumentType:  
                        Console.Write("<!DOCTYPE {0} [{1}]", reader.Name, reader.Value);  
                        break;  
                    case XmlNodeType.EntityReference:  
                        Console.Write(reader.Name);  
                        break;  
                    case XmlNodeType.EndElement:  
                        Console.Write("</{0}>", reader.Name);  
                        break;  
                }  
            }  
        }  
  
        finally  
        {  
            if (reader != null)  
                reader.Close();  
        }  
    }  
} // End class  
```  
  
 <span data-ttu-id="070b2-120">L'output dell'esempio consente di visualizzare il mapping dei dati nei tipi di nodo.</span><span class="sxs-lookup"><span data-stu-id="070b2-120">The output from the example reveals the mapping of the data to the node types.</span></span>  
  
 <span data-ttu-id="070b2-121">**Output**</span><span class="sxs-lookup"><span data-stu-id="070b2-121">**Output**</span></span>  
  
```xml  
<?xml version='1.0'?><!--This is a sample XML document --><!DOCTYPE Items [<!ENTITY number "123">]<Items><Item>Test with an entity: 123</Item><Item>test with a child element <more> stuff</Item><Item>test with a CDATA section <![CDATA[<456>]]> def</Item><Item>Test with a char entity: A</Item><--Fourteen chars in this element.--><Item>1234567890ABCD</Item></Items>
```  
  
 <span data-ttu-id="070b2-122">Esaminando l'input riga per riga e usando l'output generato dal codice, è possibile usare la tabella seguente per analizzare quale verifica del nodo ha generato determinate righe di output e capire quindi quali dati XML sono stati convertiti in un determinato tipo di nodo.</span><span class="sxs-lookup"><span data-stu-id="070b2-122">Taking the input one line at a time and using the output generated from the code, you can use the following table to analyze what node test generated which lines of output, thereby understanding what XML data became what kind of node type.</span></span>  
  
|<span data-ttu-id="070b2-123">Input</span><span class="sxs-lookup"><span data-stu-id="070b2-123">Input</span></span>|<span data-ttu-id="070b2-124">Output</span><span class="sxs-lookup"><span data-stu-id="070b2-124">Output</span></span>|<span data-ttu-id="070b2-125">Verifica del tipo di nodo</span><span class="sxs-lookup"><span data-stu-id="070b2-125">Node Type Test</span></span>|  
|-----------|------------|--------------------|  
|\<?xml version="1.0"?>|\<?xml version='1.0'?>|<span data-ttu-id="070b2-126">XmlNodeType.XmlDeclaration</span><span class="sxs-lookup"><span data-stu-id="070b2-126">XmlNodeType.XmlDeclaration</span></span>|  
|\<!-- This is a sample XML document -->|\<!--This is a sample XML document -->|<span data-ttu-id="070b2-127">XmlNodeType.Comment</span><span class="sxs-lookup"><span data-stu-id="070b2-127">XmlNodeType.Comment</span></span>|  
|<span data-ttu-id="070b2-128">\<!DOCTYPE Items [\<!ENTITY number "123">] ></span><span class="sxs-lookup"><span data-stu-id="070b2-128">\<!DOCTYPE Items [\<!ENTITY number "123">]></span></span>|<span data-ttu-id="070b2-129">\<!DOCTYPE Items [\<!ENTITY number "123">]</span><span class="sxs-lookup"><span data-stu-id="070b2-129">\<!DOCTYPE Items [\<!ENTITY number "123">]</span></span>|<span data-ttu-id="070b2-130">XmlNodeType.DocumentType</span><span class="sxs-lookup"><span data-stu-id="070b2-130">XmlNodeType.DocumentType</span></span>|  
|\<Items>|\<Items>|<span data-ttu-id="070b2-131">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="070b2-131">XmlNodeType.Element</span></span>|  
|\<Item>|\<Item>|<span data-ttu-id="070b2-132">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="070b2-132">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="070b2-133">Test with an entity: &number;</span><span class="sxs-lookup"><span data-stu-id="070b2-133">Test with an entity: &number;</span></span>|<span data-ttu-id="070b2-134">Test with an entity: 123</span><span class="sxs-lookup"><span data-stu-id="070b2-134">Test with an entity: 123</span></span>|<span data-ttu-id="070b2-135">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="070b2-135">XmlNodeType.Text</span></span>|  
|\</Item>|\</Item>|<span data-ttu-id="070b2-136">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="070b2-136">XmlNodeType.EndElement</span></span>|  
|\<Item>|\<Item>|<span data-ttu-id="070b2-137">XmNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="070b2-137">XmNodeType.Element</span></span>|  
|<span data-ttu-id="070b2-138">test with a child element</span><span class="sxs-lookup"><span data-stu-id="070b2-138">test with a child element</span></span>|<span data-ttu-id="070b2-139">test with a child element</span><span class="sxs-lookup"><span data-stu-id="070b2-139">test with a child element</span></span>|<span data-ttu-id="070b2-140">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="070b2-140">XmlNodeType.Text</span></span>|  
|\<more>|\<more>|<span data-ttu-id="070b2-141">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="070b2-141">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="070b2-142">stuff</span><span class="sxs-lookup"><span data-stu-id="070b2-142">stuff</span></span>|<span data-ttu-id="070b2-143">stuff</span><span class="sxs-lookup"><span data-stu-id="070b2-143">stuff</span></span>|<span data-ttu-id="070b2-144">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="070b2-144">XmlNodeType.Text</span></span>|  
|\</Item>|\</Item>|<span data-ttu-id="070b2-145">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="070b2-145">XmlNodeType.EndElement</span></span>|  
|\<Item>|\<Item>|<span data-ttu-id="070b2-146">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="070b2-146">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="070b2-147">test with a CDATA section</span><span class="sxs-lookup"><span data-stu-id="070b2-147">test with a CDATA section</span></span>|<span data-ttu-id="070b2-148">test with a CDATA section</span><span class="sxs-lookup"><span data-stu-id="070b2-148">test with a CDATA section</span></span>|<span data-ttu-id="070b2-149">XmlTest.Text</span><span class="sxs-lookup"><span data-stu-id="070b2-149">XmlTest.Text</span></span>|  
|<span data-ttu-id="070b2-150"><. [CDATA [ \<456> ]]\></span><span class="sxs-lookup"><span data-stu-id="070b2-150"><![CDATA[\<456>]]\></span></span>|<span data-ttu-id="070b2-151"><. [CDATA [ \<456> ]]\></span><span class="sxs-lookup"><span data-stu-id="070b2-151"><![CDATA[\<456>]]\></span></span>|<span data-ttu-id="070b2-152">XmlTest.CDATA</span><span class="sxs-lookup"><span data-stu-id="070b2-152">XmlTest.CDATA</span></span>|  
|<span data-ttu-id="070b2-153">def</span><span class="sxs-lookup"><span data-stu-id="070b2-153">def</span></span>|<span data-ttu-id="070b2-154">def</span><span class="sxs-lookup"><span data-stu-id="070b2-154">def</span></span>|<span data-ttu-id="070b2-155">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="070b2-155">XmlNodeType.Text</span></span>|  
|\</Item>|\</Item>|<span data-ttu-id="070b2-156">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="070b2-156">XmlNodeType.EndElement</span></span>|  
|\<Item>|\<Item>|<span data-ttu-id="070b2-157">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="070b2-157">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="070b2-158">Test with a char entity: &\#65;</span><span class="sxs-lookup"><span data-stu-id="070b2-158">Test with a char entity: &\#65;</span></span>|<span data-ttu-id="070b2-159">Test with a char entity: A</span><span class="sxs-lookup"><span data-stu-id="070b2-159">Test with a char entity: A</span></span>|<span data-ttu-id="070b2-160">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="070b2-160">XmlNodeType.Text</span></span>|  
|\</Item>|\</Item>|<span data-ttu-id="070b2-161">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="070b2-161">XmlNodeType.EndElement</span></span>|  
|\<!-- Fourteen chars in this element.-->|\<--Fourteen chars in this element.-->|<span data-ttu-id="070b2-162">XmlNodeType.Comment</span><span class="sxs-lookup"><span data-stu-id="070b2-162">XmlNodeType.Comment</span></span>|  
|\<Item>|\<Item>|<span data-ttu-id="070b2-163">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="070b2-163">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="070b2-164">1234567890ABCD</span><span class="sxs-lookup"><span data-stu-id="070b2-164">1234567890ABCD</span></span>|<span data-ttu-id="070b2-165">1234567890ABCD</span><span class="sxs-lookup"><span data-stu-id="070b2-165">1234567890ABCD</span></span>|<span data-ttu-id="070b2-166">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="070b2-166">XmlNodeType.Text</span></span>|  
|\</Item>|\</Item>|<span data-ttu-id="070b2-167">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="070b2-167">XmlNodeType.EndElement</span></span>|  
|\</Items>|\</Items>|<span data-ttu-id="070b2-168">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="070b2-168">XmlNodeType.EndElement</span></span>|  
  
 <span data-ttu-id="070b2-169">È necessario sapere quale tipo di nodo viene assegnato, poiché in base al tipo di nodo vengono determinate le operazioni valide e il tipo di proprietà che è possibile impostare e recuperare.</span><span class="sxs-lookup"><span data-stu-id="070b2-169">You must know what node type is assigned, as the node type controls what kinds of actions are valid and what kind of properties you can set and retrieve.</span></span>  
  
 <span data-ttu-id="070b2-170">La creazione di nodi per spazi vuoti viene controllata quando i dati sono caricati nel DOM dal flag **PreserveWhitespace**.</span><span class="sxs-lookup"><span data-stu-id="070b2-170">Node creation for white space is controlled when the data is loaded into the DOM by the **PreserveWhitespace** flag.</span></span> <span data-ttu-id="070b2-171">Per altre informazioni, vedere [Gestione degli spazi vuoti e degli spazi vuoti significativi durante il caricamento del DOM](white-space-and-significant-white-space-handling-when-loading-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="070b2-171">For more information, see [White Space and Significant White Space Handling when Loading the DOM](white-space-and-significant-white-space-handling-when-loading-the-dom.md).</span></span>  
  
 <span data-ttu-id="070b2-172">Per aggiungere nuovi nodi al DOM, vedere [Inserimento di nodi in un documento XML](inserting-nodes-into-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="070b2-172">To add new nodes to the DOM, see [Inserting Nodes into an XML Document](inserting-nodes-into-an-xml-document.md).</span></span> <span data-ttu-id="070b2-173">Per rimuovere nodi dal DOM, vedere [Rimozione di nodi, contenuto e valori da un documento XML](removing-nodes-content-and-values-from-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="070b2-173">To remove nodes from the DOM, see [Removing Nodes, Content, and Values from an XML Document](removing-nodes-content-and-values-from-an-xml-document.md).</span></span> <span data-ttu-id="070b2-174">Per modificare il contenuto dei nodi nel DOM, vedere [Modifica di nodi, contenuto e valori in un documento XML](modifying-nodes-content-and-values-in-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="070b2-174">To modify the content of nodes in the DOM, see [Modifying Nodes, Content, and Values in an XML Document](modifying-nodes-content-and-values-in-an-xml-document.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="070b2-175">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="070b2-175">See also</span></span>

- [<span data-ttu-id="070b2-176">XML DOM (Document Object Model)</span><span class="sxs-lookup"><span data-stu-id="070b2-176">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
