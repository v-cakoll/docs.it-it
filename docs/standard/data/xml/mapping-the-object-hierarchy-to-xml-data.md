---
title: Mapping della gerarchia di oggetti in dati XML
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 450e350b-6a68-4634-a2a5-33f4dc33baf0
ms.openlocfilehash: 642a7e5321d0150865f74a66a811914bc9f5d21d
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78160027"
---
# <a name="mapping-the-object-hierarchy-to-xml-data"></a><span data-ttu-id="12c41-102">Mapping della gerarchia di oggetti in dati XML</span><span class="sxs-lookup"><span data-stu-id="12c41-102">Mapping the Object Hierarchy to XML Data</span></span>
<span data-ttu-id="12c41-103">Quando un documento XML è in memoria, la rappresentazione concettuale è un albero.</span><span class="sxs-lookup"><span data-stu-id="12c41-103">When an XML document is in memory, the conceptual representation is a tree.</span></span> <span data-ttu-id="12c41-104">Nella programmazione, è possibile accedere ai nodi dell'albero mediante una gerarchia di oggetti.</span><span class="sxs-lookup"><span data-stu-id="12c41-104">For programming, you have an object hierarchy to access the nodes of the tree.</span></span> <span data-ttu-id="12c41-105">Nell'esempio seguente viene illustrato come il contenuto XML viene convertito in nodi.</span><span class="sxs-lookup"><span data-stu-id="12c41-105">The following example shows you how the XML content becomes nodes.</span></span>  
  
 <span data-ttu-id="12c41-106">Mentre il codice XML viene letto nel DOM (Document Object Model) XML, i dati sono convertiti in nodi in cui vengono conservati metadati aggiuntivi, quali il tipo di nodo e i relativi valori.</span><span class="sxs-lookup"><span data-stu-id="12c41-106">As the XML is read into the XML Document Object Model (DOM), the pieces are translated into nodes, and these nodes retain additional metadata about themselves, such as their node type and values.</span></span> <span data-ttu-id="12c41-107">Il tipo di nodo corrisponde al relativo oggetto e determina le operazioni che possono essere eseguite e le proprietà che possono essere impostate o recuperate.</span><span class="sxs-lookup"><span data-stu-id="12c41-107">The node type is its object and is what determines what actions can be performed and what properties can be set or retrieved.</span></span>  
  
 <span data-ttu-id="12c41-108">Si consideri ad esempio il seguente codice XML:</span><span class="sxs-lookup"><span data-stu-id="12c41-108">If you have the following simple XML:</span></span>  
  
 <span data-ttu-id="12c41-109">**Input**</span><span class="sxs-lookup"><span data-stu-id="12c41-109">**Input**</span></span>  
  
```xml  
<book>  
    <title>The Handmaid's Tale</title>  
</book>  
```  
  
 <span data-ttu-id="12c41-110">L'input è rappresentato in memoria come il seguente albero di nodi con la proprietà del tipo di nodo associata:</span><span class="sxs-lookup"><span data-stu-id="12c41-110">The input is represented in memory as the following node tree with the assigned node type property:</span></span>  
  
 <span data-ttu-id="12c41-111">![Albero nodo esempio](../../../../docs/standard/data/xml/media/simple-xml.gif "Simple_XML")</span><span class="sxs-lookup"><span data-stu-id="12c41-111">![example node tree](../../../../docs/standard/data/xml/media/simple-xml.gif "Simple_XML")</span></span>  
<span data-ttu-id="12c41-112">Rappresentazione dell'albero dei nodi Book e Title</span><span class="sxs-lookup"><span data-stu-id="12c41-112">Book and title node tree representation</span></span>  
  
 <span data-ttu-id="12c41-113">L'elemento `book` viene convertito in un oggetto **XmlElement**, l'elemento successivo `title` viene convertito anch'esso in **XmlElement**, mentre il contenuto degli elementi viene convertito in un oggetto **XmlText**.</span><span class="sxs-lookup"><span data-stu-id="12c41-113">The `book` element becomes an **XmlElement** object, the next element, `title`, also becomes an **XmlElement**, while the element content becomes an **XmlText** object.</span></span> <span data-ttu-id="12c41-114">Osservando i metodi e le proprietà **XmlElement**, si può notare che questi sono diversi dai metodi e dalle proprietà disponibili in un oggetto **XmlText**.</span><span class="sxs-lookup"><span data-stu-id="12c41-114">In looking at the **XmlElement** methods and properties, the methods and properties are different than the methods and properties available on an **XmlText** object.</span></span> <span data-ttu-id="12c41-115">È quindi fondamentale sapere quale tipo di nodo diventerà il markup XML, perché in base a questo vengono determinate le operazioni che possono essere eseguite.</span><span class="sxs-lookup"><span data-stu-id="12c41-115">So knowing what node type the XML markup becomes is vital, as its node type determines the actions that can be performed.</span></span>  
  
 <span data-ttu-id="12c41-116">Nell'esempio seguente vengono letti i dati XML e viene scritto un testo diverso a seconda del tipo di nodo,</span><span class="sxs-lookup"><span data-stu-id="12c41-116">The following example reads in XML data and writes out different text, depending on the node type.</span></span> <span data-ttu-id="12c41-117">usando come input il file di dati XML **items.xml**:</span><span class="sxs-lookup"><span data-stu-id="12c41-117">Using the following XML data file as input, **items.xml**:</span></span>  
  
 <span data-ttu-id="12c41-118">**Input**</span><span class="sxs-lookup"><span data-stu-id="12c41-118">**Input**</span></span>  
  
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
  
 <span data-ttu-id="12c41-119">L'esempio di codice seguente legge il file **items.xml** e visualizza le informazioni per ogni tipo di nodo.</span><span class="sxs-lookup"><span data-stu-id="12c41-119">The following code example reads the **items.xml** file and displays information for each node type.</span></span>  
  
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
  
 <span data-ttu-id="12c41-120">L'output dell'esempio consente di visualizzare il mapping dei dati nei tipi di nodo.</span><span class="sxs-lookup"><span data-stu-id="12c41-120">The output from the example reveals the mapping of the data to the node types.</span></span>  
  
 <span data-ttu-id="12c41-121">**Output**</span><span class="sxs-lookup"><span data-stu-id="12c41-121">**Output**</span></span>  
  
```xml  
<?xml version='1.0'?><!--This is a sample XML document --><!DOCTYPE Items [<!ENTITY number "123">]<Items><Item>Test with an entity: 123</Item><Item>test with a child element <more> stuff</Item><Item>test with a CDATA section <![CDATA[<456>]]> def</Item><Item>Test with a char entity: A</Item><--Fourteen chars in this element.--><Item>1234567890ABCD</Item></Items>  
```  
  
 <span data-ttu-id="12c41-122">Esaminando l'input riga per riga e usando l'output generato dal codice, è possibile usare la tabella seguente per analizzare quale verifica del nodo ha generato determinate righe di output e capire quindi quali dati XML sono stati convertiti in un determinato tipo di nodo.</span><span class="sxs-lookup"><span data-stu-id="12c41-122">Taking the input one line at a time and using the output generated from the code, you can use the following table to analyze what node test generated which lines of output, thereby understanding what XML data became what kind of node type.</span></span>  
  
|<span data-ttu-id="12c41-123">Input</span><span class="sxs-lookup"><span data-stu-id="12c41-123">Input</span></span>|<span data-ttu-id="12c41-124">Output</span><span class="sxs-lookup"><span data-stu-id="12c41-124">Output</span></span>|<span data-ttu-id="12c41-125">Verifica del tipo di nodo</span><span class="sxs-lookup"><span data-stu-id="12c41-125">Node Type Test</span></span>|  
|-----------|------------|--------------------|  
|<span data-ttu-id="12c41-126">\<?xml version="1.0"?></span><span class="sxs-lookup"><span data-stu-id="12c41-126">\<?xml version="1.0"?></span></span>|<span data-ttu-id="12c41-127">\<?xml version='1.0'?></span><span class="sxs-lookup"><span data-stu-id="12c41-127">\<?xml version='1.0'?></span></span>|<span data-ttu-id="12c41-128">XmlNodeType.XmlDeclaration</span><span class="sxs-lookup"><span data-stu-id="12c41-128">XmlNodeType.XmlDeclaration</span></span>|  
|<span data-ttu-id="12c41-129">\<!-- This is a sample XML document --></span><span class="sxs-lookup"><span data-stu-id="12c41-129">\<!-- This is a sample XML document --></span></span>|<span data-ttu-id="12c41-130">\<!--This is a sample XML document --></span><span class="sxs-lookup"><span data-stu-id="12c41-130">\<!--This is a sample XML document --></span></span>|<span data-ttu-id="12c41-131">XmlNodeType.Comment</span><span class="sxs-lookup"><span data-stu-id="12c41-131">XmlNodeType.Comment</span></span>|  
|<span data-ttu-id="12c41-132">\<!DOCTYPE Items [\<!ENTITY number "123">]></span><span class="sxs-lookup"><span data-stu-id="12c41-132">\<!DOCTYPE Items [\<!ENTITY number "123">]></span></span>|<span data-ttu-id="12c41-133">\<!DOCTYPE Items [\<!ENTITY number "123">]</span><span class="sxs-lookup"><span data-stu-id="12c41-133">\<!DOCTYPE Items [\<!ENTITY number "123">]</span></span>|<span data-ttu-id="12c41-134">XmlNodeType.DocumentType</span><span class="sxs-lookup"><span data-stu-id="12c41-134">XmlNodeType.DocumentType</span></span>|  
|<span data-ttu-id="12c41-135">\<Items></span><span class="sxs-lookup"><span data-stu-id="12c41-135">\<Items></span></span>|<span data-ttu-id="12c41-136">\<Items></span><span class="sxs-lookup"><span data-stu-id="12c41-136">\<Items></span></span>|<span data-ttu-id="12c41-137">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="12c41-137">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="12c41-138">\<Item></span><span class="sxs-lookup"><span data-stu-id="12c41-138">\<Item></span></span>|<span data-ttu-id="12c41-139">\<Item></span><span class="sxs-lookup"><span data-stu-id="12c41-139">\<Item></span></span>|<span data-ttu-id="12c41-140">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="12c41-140">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="12c41-141">Test with an entity: &number;</span><span class="sxs-lookup"><span data-stu-id="12c41-141">Test with an entity: &number;</span></span>|<span data-ttu-id="12c41-142">Test with an entity: 123</span><span class="sxs-lookup"><span data-stu-id="12c41-142">Test with an entity: 123</span></span>|<span data-ttu-id="12c41-143">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="12c41-143">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="12c41-144">\</Item></span><span class="sxs-lookup"><span data-stu-id="12c41-144">\</Item></span></span>|<span data-ttu-id="12c41-145">\</Item></span><span class="sxs-lookup"><span data-stu-id="12c41-145">\</Item></span></span>|<span data-ttu-id="12c41-146">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="12c41-146">XmlNodeType.EndElement</span></span>|  
|<span data-ttu-id="12c41-147">\<Item></span><span class="sxs-lookup"><span data-stu-id="12c41-147">\<Item></span></span>|<span data-ttu-id="12c41-148">\<Item></span><span class="sxs-lookup"><span data-stu-id="12c41-148">\<Item></span></span>|<span data-ttu-id="12c41-149">XmNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="12c41-149">XmNodeType.Element</span></span>|  
|<span data-ttu-id="12c41-150">test with a child element</span><span class="sxs-lookup"><span data-stu-id="12c41-150">test with a child element</span></span>|<span data-ttu-id="12c41-151">test with a child element</span><span class="sxs-lookup"><span data-stu-id="12c41-151">test with a child element</span></span>|<span data-ttu-id="12c41-152">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="12c41-152">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="12c41-153">\<more></span><span class="sxs-lookup"><span data-stu-id="12c41-153">\<more></span></span>|<span data-ttu-id="12c41-154">\<more></span><span class="sxs-lookup"><span data-stu-id="12c41-154">\<more></span></span>|<span data-ttu-id="12c41-155">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="12c41-155">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="12c41-156">stuff</span><span class="sxs-lookup"><span data-stu-id="12c41-156">stuff</span></span>|<span data-ttu-id="12c41-157">stuff</span><span class="sxs-lookup"><span data-stu-id="12c41-157">stuff</span></span>|<span data-ttu-id="12c41-158">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="12c41-158">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="12c41-159">\</Item></span><span class="sxs-lookup"><span data-stu-id="12c41-159">\</Item></span></span>|<span data-ttu-id="12c41-160">\</Item></span><span class="sxs-lookup"><span data-stu-id="12c41-160">\</Item></span></span>|<span data-ttu-id="12c41-161">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="12c41-161">XmlNodeType.EndElement</span></span>|  
|<span data-ttu-id="12c41-162">\<Item></span><span class="sxs-lookup"><span data-stu-id="12c41-162">\<Item></span></span>|<span data-ttu-id="12c41-163">\<Item></span><span class="sxs-lookup"><span data-stu-id="12c41-163">\<Item></span></span>|<span data-ttu-id="12c41-164">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="12c41-164">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="12c41-165">test with a CDATA section</span><span class="sxs-lookup"><span data-stu-id="12c41-165">test with a CDATA section</span></span>|<span data-ttu-id="12c41-166">test with a CDATA section</span><span class="sxs-lookup"><span data-stu-id="12c41-166">test with a CDATA section</span></span>|<span data-ttu-id="12c41-167">XmlTest.Text</span><span class="sxs-lookup"><span data-stu-id="12c41-167">XmlTest.Text</span></span>|  
|<span data-ttu-id="12c41-168"><![CDATA[\<456>]]\></span><span class="sxs-lookup"><span data-stu-id="12c41-168"><![CDATA[\<456>]]\></span></span>|<span data-ttu-id="12c41-169"><![CDATA[\<456>]]\></span><span class="sxs-lookup"><span data-stu-id="12c41-169"><![CDATA[\<456>]]\></span></span>|<span data-ttu-id="12c41-170">XmlTest.CDATA</span><span class="sxs-lookup"><span data-stu-id="12c41-170">XmlTest.CDATA</span></span>|  
|<span data-ttu-id="12c41-171">def</span><span class="sxs-lookup"><span data-stu-id="12c41-171">def</span></span>|<span data-ttu-id="12c41-172">def</span><span class="sxs-lookup"><span data-stu-id="12c41-172">def</span></span>|<span data-ttu-id="12c41-173">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="12c41-173">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="12c41-174">\</Item></span><span class="sxs-lookup"><span data-stu-id="12c41-174">\</Item></span></span>|<span data-ttu-id="12c41-175">\</Item></span><span class="sxs-lookup"><span data-stu-id="12c41-175">\</Item></span></span>|<span data-ttu-id="12c41-176">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="12c41-176">XmlNodeType.EndElement</span></span>|  
|<span data-ttu-id="12c41-177">\<Item></span><span class="sxs-lookup"><span data-stu-id="12c41-177">\<Item></span></span>|<span data-ttu-id="12c41-178">\<Item></span><span class="sxs-lookup"><span data-stu-id="12c41-178">\<Item></span></span>|<span data-ttu-id="12c41-179">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="12c41-179">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="12c41-180">Test with a char entity: &\#65;</span><span class="sxs-lookup"><span data-stu-id="12c41-180">Test with a char entity: &\#65;</span></span>|<span data-ttu-id="12c41-181">Test with a char entity: A</span><span class="sxs-lookup"><span data-stu-id="12c41-181">Test with a char entity: A</span></span>|<span data-ttu-id="12c41-182">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="12c41-182">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="12c41-183">\</Item></span><span class="sxs-lookup"><span data-stu-id="12c41-183">\</Item></span></span>|<span data-ttu-id="12c41-184">\</Item></span><span class="sxs-lookup"><span data-stu-id="12c41-184">\</Item></span></span>|<span data-ttu-id="12c41-185">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="12c41-185">XmlNodeType.EndElement</span></span>|  
|<span data-ttu-id="12c41-186">\<!-- Fourteen chars in this element.--></span><span class="sxs-lookup"><span data-stu-id="12c41-186">\<!-- Fourteen chars in this element.--></span></span>|<span data-ttu-id="12c41-187">\<--Fourteen chars in this element.--></span><span class="sxs-lookup"><span data-stu-id="12c41-187">\<--Fourteen chars in this element.--></span></span>|<span data-ttu-id="12c41-188">XmlNodeType.Comment</span><span class="sxs-lookup"><span data-stu-id="12c41-188">XmlNodeType.Comment</span></span>|  
|<span data-ttu-id="12c41-189">\<Item></span><span class="sxs-lookup"><span data-stu-id="12c41-189">\<Item></span></span>|<span data-ttu-id="12c41-190">\<Item></span><span class="sxs-lookup"><span data-stu-id="12c41-190">\<Item></span></span>|<span data-ttu-id="12c41-191">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="12c41-191">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="12c41-192">1234567890ABCD</span><span class="sxs-lookup"><span data-stu-id="12c41-192">1234567890ABCD</span></span>|<span data-ttu-id="12c41-193">1234567890ABCD</span><span class="sxs-lookup"><span data-stu-id="12c41-193">1234567890ABCD</span></span>|<span data-ttu-id="12c41-194">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="12c41-194">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="12c41-195">\</Item></span><span class="sxs-lookup"><span data-stu-id="12c41-195">\</Item></span></span>|<span data-ttu-id="12c41-196">\</Item></span><span class="sxs-lookup"><span data-stu-id="12c41-196">\</Item></span></span>|<span data-ttu-id="12c41-197">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="12c41-197">XmlNodeType.EndElement</span></span>|  
|<span data-ttu-id="12c41-198">\</Items></span><span class="sxs-lookup"><span data-stu-id="12c41-198">\</Items></span></span>|<span data-ttu-id="12c41-199">\</Items></span><span class="sxs-lookup"><span data-stu-id="12c41-199">\</Items></span></span>|<span data-ttu-id="12c41-200">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="12c41-200">XmlNodeType.EndElement</span></span>|  
  
 <span data-ttu-id="12c41-201">È necessario sapere quale tipo di nodo viene assegnato, poiché in base al tipo di nodo vengono determinate le operazioni valide e il tipo di proprietà che è possibile impostare e recuperare.</span><span class="sxs-lookup"><span data-stu-id="12c41-201">You must know what node type is assigned, as the node type controls what kinds of actions are valid and what kind of properties you can set and retrieve.</span></span>  
  
 <span data-ttu-id="12c41-202">La creazione di nodi per spazi vuoti viene controllata quando i dati sono caricati nel DOM dal flag **PreserveWhitespace**.</span><span class="sxs-lookup"><span data-stu-id="12c41-202">Node creation for white space is controlled when the data is loaded into the DOM by the **PreserveWhitespace** flag.</span></span> <span data-ttu-id="12c41-203">Per altre informazioni, vedere [Gestione degli spazi vuoti e degli spazi vuoti significativi durante il caricamento del DOM](../../../../docs/standard/data/xml/white-space-and-significant-white-space-handling-when-loading-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="12c41-203">For more information, see [White Space and Significant White Space Handling when Loading the DOM](../../../../docs/standard/data/xml/white-space-and-significant-white-space-handling-when-loading-the-dom.md).</span></span>  
  
 <span data-ttu-id="12c41-204">Per aggiungere nuovi nodi al DOM, vedere [Inserimento di nodi in un documento XML](../../../../docs/standard/data/xml/inserting-nodes-into-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="12c41-204">To add new nodes to the DOM, see [Inserting Nodes into an XML Document](../../../../docs/standard/data/xml/inserting-nodes-into-an-xml-document.md).</span></span> <span data-ttu-id="12c41-205">Per rimuovere nodi dal DOM, vedere [Rimozione di nodi, contenuto e valori da un documento XML](../../../../docs/standard/data/xml/removing-nodes-content-and-values-from-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="12c41-205">To remove nodes from the DOM, see [Removing Nodes, Content, and Values from an XML Document](../../../../docs/standard/data/xml/removing-nodes-content-and-values-from-an-xml-document.md).</span></span> <span data-ttu-id="12c41-206">Per modificare il contenuto dei nodi nel DOM, vedere [Modifica di nodi, contenuto e valori in un documento XML](../../../../docs/standard/data/xml/modifying-nodes-content-and-values-in-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="12c41-206">To modify the content of nodes in the DOM, see [Modifying Nodes, Content, and Values in an XML Document](../../../../docs/standard/data/xml/modifying-nodes-content-and-values-in-an-xml-document.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12c41-207">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="12c41-207">See also</span></span>

- [<span data-ttu-id="12c41-208">XML DOM (Document Object Model)</span><span class="sxs-lookup"><span data-stu-id="12c41-208">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
