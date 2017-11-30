---
title: Mapping della gerarchia di oggetti in dati XML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 450e350b-6a68-4634-a2a5-33f4dc33baf0
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1bf43922fb702988e9057f541833cd58d33c820a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="mapping-the-object-hierarchy-to-xml-data"></a><span data-ttu-id="2769c-102">Mapping della gerarchia di oggetti in dati XML</span><span class="sxs-lookup"><span data-stu-id="2769c-102">Mapping the Object Hierarchy to XML Data</span></span>
<span data-ttu-id="2769c-103">Quando un documento XML è in memoria, la rappresentazione concettuale è un albero.</span><span class="sxs-lookup"><span data-stu-id="2769c-103">When an XML document is in memory, the conceptual representation is a tree.</span></span> <span data-ttu-id="2769c-104">Nella programmazione, è possibile accedere ai nodi dell'albero mediante una gerarchia di oggetti.</span><span class="sxs-lookup"><span data-stu-id="2769c-104">For programming, you have an object hierarchy to access the nodes of the tree.</span></span> <span data-ttu-id="2769c-105">Nell'esempio seguente viene illustrato come il contenuto XML viene convertito in nodi.</span><span class="sxs-lookup"><span data-stu-id="2769c-105">The following example shows you how the XML content becomes nodes.</span></span>  
  
 <span data-ttu-id="2769c-106">Mentre il codice XML viene letto nel DOM (Document Object Model) XML, i dati sono convertiti in nodi in cui vengono conservati metadati aggiuntivi, quali il tipo di nodo e i relativi valori.</span><span class="sxs-lookup"><span data-stu-id="2769c-106">As the XML is read into the XML Document Object Model (DOM), the pieces are translated into nodes, and these nodes retain additional metadata about themselves, such as their node type and values.</span></span> <span data-ttu-id="2769c-107">Il tipo di nodo corrisponde al relativo oggetto e determina le operazioni che possono essere eseguite e le proprietà che possono essere impostate o recuperate.</span><span class="sxs-lookup"><span data-stu-id="2769c-107">The node type is its object and is what determines what actions can be performed and what properties can be set or retrieved.</span></span>  
  
 <span data-ttu-id="2769c-108">Si consideri ad esempio il seguente codice XML:</span><span class="sxs-lookup"><span data-stu-id="2769c-108">If you have the following simple XML:</span></span>  
  
 <span data-ttu-id="2769c-109">**Input**</span><span class="sxs-lookup"><span data-stu-id="2769c-109">**Input**</span></span>  
  
```xml  
<book>  
    <title>The Handmaid's Tale</title>  
</book>  
```  
  
 <span data-ttu-id="2769c-110">L'input è rappresentato in memoria come il seguente albero di nodi con la proprietà del tipo di nodo associata:</span><span class="sxs-lookup"><span data-stu-id="2769c-110">The input is represented in memory as the following node tree with the assigned node type property:</span></span>  
  
 <span data-ttu-id="2769c-111">![albero nodo esempio](../../../../docs/standard/data/xml/media/simple-xml.gif "Simple_XML")</span><span class="sxs-lookup"><span data-stu-id="2769c-111">![example node tree](../../../../docs/standard/data/xml/media/simple-xml.gif "Simple_XML")</span></span>  
<span data-ttu-id="2769c-112">Rappresentazione dell'albero dei nodi Book e Title</span><span class="sxs-lookup"><span data-stu-id="2769c-112">Book and title node tree representation</span></span>  
  
 <span data-ttu-id="2769c-113">Il `book` elemento diventa un **XmlElement** oggetto, l'elemento successivo, `title`, diventa un **XmlElement**, mentre il contenuto dell'elemento diventa un **XmlText** oggetto.</span><span class="sxs-lookup"><span data-stu-id="2769c-113">The `book` element becomes an **XmlElement** object, the next element, `title`, also becomes an **XmlElement**, while the element content becomes an **XmlText** object.</span></span> <span data-ttu-id="2769c-114">Osservando il **XmlElement** metodi e proprietà, metodi e proprietà sono diverse dai metodi e le proprietà disponibili in un **XmlText** oggetto.</span><span class="sxs-lookup"><span data-stu-id="2769c-114">In looking at the **XmlElement** methods and properties, the methods and properties are different than the methods and properties available on an **XmlText** object.</span></span> <span data-ttu-id="2769c-115">È quindi fondamentale sapere quale tipo di nodo diventerà il markup XML, perché in base a questo vengono determinate le operazioni che possono essere eseguite.</span><span class="sxs-lookup"><span data-stu-id="2769c-115">So knowing what node type the XML markup becomes is vital, as its node type determines the actions that can be performed.</span></span>  
  
 <span data-ttu-id="2769c-116">Nell'esempio seguente vengono letti i dati XML e viene scritto un testo diverso a seconda del tipo di nodo,</span><span class="sxs-lookup"><span data-stu-id="2769c-116">The following example reads in XML data and writes out different text, depending on the node type.</span></span> <span data-ttu-id="2769c-117">Utilizzando il seguente file di dati XML come input, **items.xml**:</span><span class="sxs-lookup"><span data-stu-id="2769c-117">Using the following XML data file as input, **items.xml**:</span></span>  
  
 <span data-ttu-id="2769c-118">**Input**</span><span class="sxs-lookup"><span data-stu-id="2769c-118">**Input**</span></span>  
  
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
  
 <span data-ttu-id="2769c-119">Letture di esempio di codice seguente il **items.xml** file e visualizza le informazioni per ogni tipo di nodo.</span><span class="sxs-lookup"><span data-stu-id="2769c-119">The following code example reads the **items.xml** file and displays information for each node type.</span></span>  
  
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
  
 <span data-ttu-id="2769c-120">L'output dell'esempio consente di visualizzare il mapping dei dati nei tipi di nodo.</span><span class="sxs-lookup"><span data-stu-id="2769c-120">The output from the example reveals the mapping of the data to the node types.</span></span>  
  
 <span data-ttu-id="2769c-121">**Output**</span><span class="sxs-lookup"><span data-stu-id="2769c-121">**Output**</span></span>  
  
```xml  
<?xml version='1.0'?><!--This is a sample XML document --><!DOCTYPE Items [<!ENTITY number "123">]<Items><Item>Test with an entity: 123</Item><Item>test with a child element <more> stuff</Item><Item>test with a CDATA section <![CDATA[<456>]]> def</Item><Item>Test with a char entity: A</Item><--Fourteen chars in this element.--><Item>1234567890ABCD</Item></Items>  
```  
  
 <span data-ttu-id="2769c-122">Esaminando l'input riga per riga e usando l'output generato dal codice, è possibile usare la tabella seguente per analizzare quale verifica del nodo ha generato determinate righe di output e capire quindi quali dati XML sono stati convertiti in un determinato tipo di nodo.</span><span class="sxs-lookup"><span data-stu-id="2769c-122">Taking the input one line at a time and using the output generated from the code, you can use the following table to analyze what node test generated which lines of output, thereby understanding what XML data became what kind of node type.</span></span>  
  
|<span data-ttu-id="2769c-123">Input</span><span class="sxs-lookup"><span data-stu-id="2769c-123">Input</span></span>|<span data-ttu-id="2769c-124">Output</span><span class="sxs-lookup"><span data-stu-id="2769c-124">Output</span></span>|<span data-ttu-id="2769c-125">Verifica del tipo di nodo</span><span class="sxs-lookup"><span data-stu-id="2769c-125">Node Type Test</span></span>|  
|-----------|------------|--------------------|  
|<span data-ttu-id="2769c-126">\<? versione xml = "1.0"? ></span><span class="sxs-lookup"><span data-stu-id="2769c-126">\<?xml version="1.0"?></span></span>|<span data-ttu-id="2769c-127">\<? versione xml ='1.0 '? ></span><span class="sxs-lookup"><span data-stu-id="2769c-127">\<?xml version='1.0'?></span></span>|<span data-ttu-id="2769c-128">XmlNodeType.XmlDeclaration</span><span class="sxs-lookup"><span data-stu-id="2769c-128">XmlNodeType.XmlDeclaration</span></span>|  
|<span data-ttu-id="2769c-129">\<!-Si tratta di un documento XML di esempio--></span><span class="sxs-lookup"><span data-stu-id="2769c-129">\<!-- This is a sample XML document --></span></span>|<span data-ttu-id="2769c-130">\<!-Si tratta di un documento XML di esempio--></span><span class="sxs-lookup"><span data-stu-id="2769c-130">\<!--This is a sample XML document --></span></span>|<span data-ttu-id="2769c-131">XmlNodeType.Comment</span><span class="sxs-lookup"><span data-stu-id="2769c-131">XmlNodeType.Comment</span></span>|  
|<span data-ttu-id="2769c-132">\<! Gli elementi di tipo di documento [\<! Numero di entità "123" >] ></span><span class="sxs-lookup"><span data-stu-id="2769c-132">\<!DOCTYPE Items [\<!ENTITY number "123">]></span></span>|<span data-ttu-id="2769c-133">\<! Gli elementi di tipo di documento [\<! Numero di entità "123" >]</span><span class="sxs-lookup"><span data-stu-id="2769c-133">\<!DOCTYPE Items [\<!ENTITY number "123">]</span></span>|<span data-ttu-id="2769c-134">XmlNodeType.DocumentType</span><span class="sxs-lookup"><span data-stu-id="2769c-134">XmlNodeType.DocumentType</span></span>|  
|<span data-ttu-id="2769c-135">\<Gli elementi ></span><span class="sxs-lookup"><span data-stu-id="2769c-135">\<Items></span></span>|<span data-ttu-id="2769c-136">\<Gli elementi ></span><span class="sxs-lookup"><span data-stu-id="2769c-136">\<Items></span></span>|<span data-ttu-id="2769c-137">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="2769c-137">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="2769c-138">\<Item></span><span class="sxs-lookup"><span data-stu-id="2769c-138">\<Item></span></span>|<span data-ttu-id="2769c-139">\<Item></span><span class="sxs-lookup"><span data-stu-id="2769c-139">\<Item></span></span>|<span data-ttu-id="2769c-140">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="2769c-140">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="2769c-141">Test con un'entità:&number;</span><span class="sxs-lookup"><span data-stu-id="2769c-141">Test with an entity: &number;</span></span>|<span data-ttu-id="2769c-142">Test with an entity: 123</span><span class="sxs-lookup"><span data-stu-id="2769c-142">Test with an entity: 123</span></span>|<span data-ttu-id="2769c-143">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="2769c-143">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="2769c-144">\</ Item ></span><span class="sxs-lookup"><span data-stu-id="2769c-144">\</Item></span></span>|<span data-ttu-id="2769c-145">\</ Item ></span><span class="sxs-lookup"><span data-stu-id="2769c-145">\</Item></span></span>|<span data-ttu-id="2769c-146">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="2769c-146">XmlNodeType.EndElement</span></span>|  
|<span data-ttu-id="2769c-147">\<Item></span><span class="sxs-lookup"><span data-stu-id="2769c-147">\<Item></span></span>|<span data-ttu-id="2769c-148">\<Item></span><span class="sxs-lookup"><span data-stu-id="2769c-148">\<Item></span></span>|<span data-ttu-id="2769c-149">XmNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="2769c-149">XmNodeType.Element</span></span>|  
|<span data-ttu-id="2769c-150">test with a child element</span><span class="sxs-lookup"><span data-stu-id="2769c-150">test with a child element</span></span>|<span data-ttu-id="2769c-151">test with a child element</span><span class="sxs-lookup"><span data-stu-id="2769c-151">test with a child element</span></span>|<span data-ttu-id="2769c-152">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="2769c-152">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="2769c-153">\<più ></span><span class="sxs-lookup"><span data-stu-id="2769c-153">\<more></span></span>|<span data-ttu-id="2769c-154">\<più ></span><span class="sxs-lookup"><span data-stu-id="2769c-154">\<more></span></span>|<span data-ttu-id="2769c-155">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="2769c-155">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="2769c-156">stuff</span><span class="sxs-lookup"><span data-stu-id="2769c-156">stuff</span></span>|<span data-ttu-id="2769c-157">stuff</span><span class="sxs-lookup"><span data-stu-id="2769c-157">stuff</span></span>|<span data-ttu-id="2769c-158">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="2769c-158">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="2769c-159">\</ Item ></span><span class="sxs-lookup"><span data-stu-id="2769c-159">\</Item></span></span>|<span data-ttu-id="2769c-160">\</ Item ></span><span class="sxs-lookup"><span data-stu-id="2769c-160">\</Item></span></span>|<span data-ttu-id="2769c-161">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="2769c-161">XmlNodeType.EndElement</span></span>|  
|<span data-ttu-id="2769c-162">\<Item></span><span class="sxs-lookup"><span data-stu-id="2769c-162">\<Item></span></span>|<span data-ttu-id="2769c-163">\<Item></span><span class="sxs-lookup"><span data-stu-id="2769c-163">\<Item></span></span>|<span data-ttu-id="2769c-164">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="2769c-164">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="2769c-165">test with a CDATA section</span><span class="sxs-lookup"><span data-stu-id="2769c-165">test with a CDATA section</span></span>|<span data-ttu-id="2769c-166">test with a CDATA section</span><span class="sxs-lookup"><span data-stu-id="2769c-166">test with a CDATA section</span></span>|<span data-ttu-id="2769c-167">XmlTest.Text</span><span class="sxs-lookup"><span data-stu-id="2769c-167">XmlTest.Text</span></span>|  
|<span data-ttu-id="2769c-168"><! [CDATA [\<456 >]]\></span><span class="sxs-lookup"><span data-stu-id="2769c-168"><![CDATA[\<456>]]\></span></span>|<span data-ttu-id="2769c-169"><! [CDATA [\<456 >]]\></span><span class="sxs-lookup"><span data-stu-id="2769c-169"><![CDATA[\<456>]]\></span></span>|<span data-ttu-id="2769c-170">XmlTest.CDATA</span><span class="sxs-lookup"><span data-stu-id="2769c-170">XmlTest.CDATA</span></span>|  
|<span data-ttu-id="2769c-171">def</span><span class="sxs-lookup"><span data-stu-id="2769c-171">def</span></span>|<span data-ttu-id="2769c-172">def</span><span class="sxs-lookup"><span data-stu-id="2769c-172">def</span></span>|<span data-ttu-id="2769c-173">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="2769c-173">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="2769c-174">\</ Item ></span><span class="sxs-lookup"><span data-stu-id="2769c-174">\</Item></span></span>|<span data-ttu-id="2769c-175">\</ Item ></span><span class="sxs-lookup"><span data-stu-id="2769c-175">\</Item></span></span>|<span data-ttu-id="2769c-176">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="2769c-176">XmlNodeType.EndElement</span></span>|  
|<span data-ttu-id="2769c-177">\<Item></span><span class="sxs-lookup"><span data-stu-id="2769c-177">\<Item></span></span>|<span data-ttu-id="2769c-178">\<Item></span><span class="sxs-lookup"><span data-stu-id="2769c-178">\<Item></span></span>|<span data-ttu-id="2769c-179">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="2769c-179">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="2769c-180">Test con un'entità di tipo char: &\#65;</span><span class="sxs-lookup"><span data-stu-id="2769c-180">Test with a char entity: &\#65;</span></span>|<span data-ttu-id="2769c-181">Test with a char entity: A</span><span class="sxs-lookup"><span data-stu-id="2769c-181">Test with a char entity: A</span></span>|<span data-ttu-id="2769c-182">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="2769c-182">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="2769c-183">\</ Item ></span><span class="sxs-lookup"><span data-stu-id="2769c-183">\</Item></span></span>|<span data-ttu-id="2769c-184">\</ Item ></span><span class="sxs-lookup"><span data-stu-id="2769c-184">\</Item></span></span>|<span data-ttu-id="2769c-185">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="2769c-185">XmlNodeType.EndElement</span></span>|  
|<span data-ttu-id="2769c-186">\<!---> Quattordici caratteri in questo elemento.</span><span class="sxs-lookup"><span data-stu-id="2769c-186">\<!-- Fourteen chars in this element.--></span></span>|<span data-ttu-id="2769c-187">\<---> Quattordici caratteri in questo elemento.</span><span class="sxs-lookup"><span data-stu-id="2769c-187">\<--Fourteen chars in this element.--></span></span>|<span data-ttu-id="2769c-188">XmlNodeType.Comment</span><span class="sxs-lookup"><span data-stu-id="2769c-188">XmlNodeType.Comment</span></span>|  
|<span data-ttu-id="2769c-189">\<Item></span><span class="sxs-lookup"><span data-stu-id="2769c-189">\<Item></span></span>|<span data-ttu-id="2769c-190">\<Item></span><span class="sxs-lookup"><span data-stu-id="2769c-190">\<Item></span></span>|<span data-ttu-id="2769c-191">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="2769c-191">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="2769c-192">1234567890ABCD</span><span class="sxs-lookup"><span data-stu-id="2769c-192">1234567890ABCD</span></span>|<span data-ttu-id="2769c-193">1234567890ABCD</span><span class="sxs-lookup"><span data-stu-id="2769c-193">1234567890ABCD</span></span>|<span data-ttu-id="2769c-194">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="2769c-194">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="2769c-195">\</ Item ></span><span class="sxs-lookup"><span data-stu-id="2769c-195">\</Item></span></span>|<span data-ttu-id="2769c-196">\</ Item ></span><span class="sxs-lookup"><span data-stu-id="2769c-196">\</Item></span></span>|<span data-ttu-id="2769c-197">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="2769c-197">XmlNodeType.EndElement</span></span>|  
|<span data-ttu-id="2769c-198">\</ Elementi ></span><span class="sxs-lookup"><span data-stu-id="2769c-198">\</Items></span></span>|<span data-ttu-id="2769c-199">\</ Elementi ></span><span class="sxs-lookup"><span data-stu-id="2769c-199">\</Items></span></span>|<span data-ttu-id="2769c-200">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="2769c-200">XmlNodeType.EndElement</span></span>|  
  
 <span data-ttu-id="2769c-201">È necessario sapere quale tipo di nodo viene assegnato, poiché in base al tipo di nodo vengono determinate le operazioni valide e il tipo di proprietà che è possibile impostare e recuperare.</span><span class="sxs-lookup"><span data-stu-id="2769c-201">You must know what node type is assigned, as the node type controls what kinds of actions are valid and what kind of properties you can set and retrieve.</span></span>  
  
 <span data-ttu-id="2769c-202">Creazione di nodi per spazi vuoti viene controllata quando i dati vengono caricati nel DOM dal **PreserveWhitespace** flag.</span><span class="sxs-lookup"><span data-stu-id="2769c-202">Node creation for white space is controlled when the data is loaded into the DOM by the **PreserveWhitespace** flag.</span></span> <span data-ttu-id="2769c-203">Per ulteriori informazioni, vedere [spazi vuoti e significativa la gestione di spazi vuoti durante il caricamento del DOM](../../../../docs/standard/data/xml/white-space-and-significant-white-space-handling-when-loading-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="2769c-203">For more information, see [White Space and Significant White Space Handling when Loading the DOM](../../../../docs/standard/data/xml/white-space-and-significant-white-space-handling-when-loading-the-dom.md).</span></span>  
  
 <span data-ttu-id="2769c-204">Per aggiungere nuovi nodi al DOM, vedere [inserimento di nodi in un documento XML](../../../../docs/standard/data/xml/inserting-nodes-into-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="2769c-204">To add new nodes to the DOM, see [Inserting Nodes into an XML Document](../../../../docs/standard/data/xml/inserting-nodes-into-an-xml-document.md).</span></span> <span data-ttu-id="2769c-205">Per rimuovere nodi dal DOM, vedere [rimozione di nodi, contenuto e valori da un documento XML](../../../../docs/standard/data/xml/removing-nodes-content-and-values-from-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="2769c-205">To remove nodes from the DOM, see [Removing Nodes, Content, and Values from an XML Document](../../../../docs/standard/data/xml/removing-nodes-content-and-values-from-an-xml-document.md).</span></span> <span data-ttu-id="2769c-206">Per modificare il contenuto dei nodi nel DOM, vedere [modifica dei nodi, contenuto e valori in un documento XML](../../../../docs/standard/data/xml/modifying-nodes-content-and-values-in-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="2769c-206">To modify the content of nodes in the DOM, see [Modifying Nodes, Content, and Values in an XML Document](../../../../docs/standard/data/xml/modifying-nodes-content-and-values-in-an-xml-document.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2769c-207">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2769c-207">See Also</span></span>  
 [<span data-ttu-id="2769c-208">XML Document Object Model (DOM)</span><span class="sxs-lookup"><span data-stu-id="2769c-208">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
