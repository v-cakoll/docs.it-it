---
title: Come eseguire la trasformazione del flusso di documenti XML diC#grandi dimensioni ()
ms.date: 07/20/2015
ms.assetid: 5f16d1f8-5370-4b55-b0c8-e497df163037
ms.openlocfilehash: 86b74534635dcca7e8c7f94873abcb50ea7c4d2b
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345820"
---
# <a name="how-to-perform-streaming-transform-of-large-xml-documents-c"></a><span data-ttu-id="85432-102">Come eseguire la trasformazione del flusso di documenti XML diC#grandi dimensioni ()</span><span class="sxs-lookup"><span data-stu-id="85432-102">How to perform streaming transform of large XML documents (C#)</span></span>
<span data-ttu-id="85432-103">A volte è necessario trasformare file XML di grandi dimensioni e scrivere l'applicazione in modo tale che il footprint di memoria dell'applicazione sia prevedibile.</span><span class="sxs-lookup"><span data-stu-id="85432-103">Sometimes you have to transform large XML files, and write your application so that the memory footprint of the application is predictable.</span></span> <span data-ttu-id="85432-104">Se si tenta di popolare un albero XML con un file XML molto grande, l'uso della memoria sarà proporzionale alla dimensione del file (ovvero, eccessivo).</span><span class="sxs-lookup"><span data-stu-id="85432-104">If you try to populate an XML tree with a very large XML file, your memory usage will be proportional to the size of the file (that is, excessive).</span></span> <span data-ttu-id="85432-105">Pertanto, è necessario usare una tecnica di flusso in sostituzione.</span><span class="sxs-lookup"><span data-stu-id="85432-105">Therefore, you should use a streaming technique instead.</span></span>  
  
 <span data-ttu-id="85432-106">Le tecniche di flusso sono maggiormente indicate nelle situazioni in cui è necessario elaborare solo una volta il documento di origine ed è possibile elaborare gli elementi in base all'ordine in cui sono riportati nel documento.</span><span class="sxs-lookup"><span data-stu-id="85432-106">Streaming techniques are best applied in situations where you need to process the source document only once, and you can process the elements in document order.</span></span> <span data-ttu-id="85432-107">Determinati operatori di query standard, ad esempio <xref:System.Linq.Enumerable.OrderBy%2A>, scorrono l'origine, raccolgono tutti i dati, li ordinano e infine restituiscono il primo elemento nella sequenza.</span><span class="sxs-lookup"><span data-stu-id="85432-107">Certain standard query operators, such as <xref:System.Linq.Enumerable.OrderBy%2A>, iterate their source, collect all of the data, sort it, and then finally yield the first item in the sequence.</span></span> <span data-ttu-id="85432-108">Si noti che se si usa un operatore di query che materializza l'origine prima di restituire il primo elemento, non verrà mantenuto un footprint di memoria ridotto per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="85432-108">Note that if you use a query operator that materializes its source before yielding the first item, you will not retain a small memory footprint for your application.</span></span>  
  
<span data-ttu-id="85432-109">Anche se si usa la tecnica descritta in [come eseguire lo streaming di frammenti XML con accesso a informazioni diC#intestazione ()](./how-to-stream-xml-fragments-with-access-to-header-information.md), se si tenta di assemblare un albero XML che contiene il documento trasformato, l'utilizzo della memoria sarà troppo elevato.</span><span class="sxs-lookup"><span data-stu-id="85432-109">Even if you use the technique described in [How to stream XML fragments with access to header information (C#)](./how-to-stream-xml-fragments-with-access-to-header-information.md), if you try to assemble an XML tree that contains the transformed document, memory usage will be too great.</span></span>
  
 <span data-ttu-id="85432-110">Sono disponibili due approcci principali:</span><span class="sxs-lookup"><span data-stu-id="85432-110">There are two main approaches.</span></span> <span data-ttu-id="85432-111">il primo consiste nell'usare le caratteristiche di elaborazione posticipata di <xref:System.Xml.Linq.XStreamingElement>.</span><span class="sxs-lookup"><span data-stu-id="85432-111">One approach is to use the deferred processing characteristics of <xref:System.Xml.Linq.XStreamingElement>.</span></span> <span data-ttu-id="85432-112">L'altro prevede la creazione di un oggetto <xref:System.Xml.XmlWriter> e l'uso delle funzionalità di [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] per scrivere elementi in un oggetto <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="85432-112">Another approach is to create an <xref:System.Xml.XmlWriter>, and use the capabilities of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] to write elements to an <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="85432-113">In questo argomento vengono descritti entrambi gli approcci.</span><span class="sxs-lookup"><span data-stu-id="85432-113">This topic demonstrates both approaches.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85432-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="85432-114">Example</span></span>  
 <span data-ttu-id="85432-115">Nell'esempio seguente si basa sull'esempio di [come eseguire il flusso di frammenti XML con accesso a informazioni diC#intestazione ()](./how-to-stream-xml-fragments-with-access-to-header-information.md).</span><span class="sxs-lookup"><span data-stu-id="85432-115">The following example builds on the example in [How to stream XML fragments with access to header information (C#)](./how-to-stream-xml-fragments-with-access-to-header-information.md).</span></span>
  
 <span data-ttu-id="85432-116">In questo esempio vengono usate le funzionalità di esecuzione posticipata di <xref:System.Xml.Linq.XStreamingElement> per generare il flusso di output.</span><span class="sxs-lookup"><span data-stu-id="85432-116">This example uses the deferred execution capabilities of <xref:System.Xml.Linq.XStreamingElement> to stream the output.</span></span> <span data-ttu-id="85432-117">È possibile trasformare un documento di dimensioni molto grandi mantenendo un footprint di memoria ridotto.</span><span class="sxs-lookup"><span data-stu-id="85432-117">This example can transform a very large document while maintaining a small memory footprint.</span></span>  
  
 <span data-ttu-id="85432-118">Si noti che il metodo dell'asse personalizzato (`StreamCustomerItem`) è stato scritto in modo tale da prevedere un documento contenente elementi `Customer`, `Name` e `Item`, disposti come nel documento Source.xml seguente.</span><span class="sxs-lookup"><span data-stu-id="85432-118">Note that the custom axis (`StreamCustomerItem`) is specifically written so that it expects a document that has `Customer`, `Name`, and `Item` elements, and that those elements will be arranged as in the following Source.xml document.</span></span> <span data-ttu-id="85432-119">Tuttavia, un'implementazione più solida sarebbe in grado di analizzare un documento non valido.</span><span class="sxs-lookup"><span data-stu-id="85432-119">A more robust implementation, however, would be prepared to parse an invalid document.</span></span>  
  
 <span data-ttu-id="85432-120">Il documento seguente, Source.xml, è il documento di origine:</span><span class="sxs-lookup"><span data-stu-id="85432-120">The following is the source document, Source.xml:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>   
<Root>  
  <Customer>  
    <Name>A. Datum Corporation</Name>  
    <Item>  
      <Key>0001</Key>  
    </Item>  
    <Item>  
      <Key>0002</Key>  
    </Item>  
    <Item>  
      <Key>0003</Key>  
    </Item>  
    <Item>  
      <Key>0004</Key>  
    </Item>  
  </Customer>  
  <Customer>  
    <Name>Fabrikam, Inc.</Name>  
    <Item>  
      <Key>0005</Key>  
    </Item>  
    <Item>  
      <Key>0006</Key>  
    </Item>  
    <Item>  
      <Key>0007</Key>  
    </Item>  
    <Item>  
      <Key>0008</Key>  
    </Item>  
  </Customer>  
  <Customer>  
    <Name>Southridge Video</Name>  
    <Item>  
      <Key>0009</Key>  
    </Item>  
    <Item>  
      <Key>0010</Key>  
    </Item>  
  </Customer>  
</Root>  
```  
  
```csharp  
static IEnumerable<XElement> StreamCustomerItem(string uri)  
{  
    using (XmlReader reader = XmlReader.Create(uri))  
    {  
        XElement name = null;  
        XElement item = null;  
  
        reader.MoveToContent();  
  
        // Parse the file, save header information when encountered, and yield the  
        // Item XElement objects as they are created.  
  
        // loop through Customer elements  
        while (reader.Read())  
        {  
            if (reader.NodeType == XmlNodeType.Element  
                && reader.Name == "Customer")  
            {  
                // move to Name element  
                while (reader.Read())  
                {  
                    if (reader.NodeType == XmlNodeType.Element &&  
                        reader.Name == "Name")  
                    {  
                        name = XElement.ReadFrom(reader) as XElement;  
                        break;  
                    }  
                }  
  
                // loop through Item elements  
                while (reader.Read())  
                {  
                    if (reader.NodeType == XmlNodeType.EndElement)  
                        break;  
                    if (reader.NodeType == XmlNodeType.Element  
                        && reader.Name == "Item")  
                    {  
                        item = XElement.ReadFrom(reader) as XElement;  
                        if (item != null)  
                        {  
                            XElement tempRoot = new XElement("Root",  
                                new XElement(name)  
                            );  
                            tempRoot.Add(item);  
                            yield return item;  
                        }  
                    }  
                }  
            }  
        }  
    }  
}  
  
static void Main(string[] args)  
{  
    XStreamingElement root = new XStreamingElement("Root",  
        from el in StreamCustomerItem("Source.xml")  
        select new XElement("Item",  
            new XElement("Customer", (string)el.Parent.Element("Name")),  
            new XElement(el.Element("Key"))  
        )  
    );  
    root.Save("Test.xml");  
    Console.WriteLine(File.ReadAllText("Test.xml"));  
}  
```  
  
 <span data-ttu-id="85432-121">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="85432-121">This code produces the following output:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Root>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0001</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0002</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0003</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0004</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0005</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0006</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0007</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0008</Key>  
  </Item>  
  <Item>  
    <Customer>Southridge Video</Customer>  
    <Key>0009</Key>  
  </Item>  
  <Item>  
    <Customer>Southridge Video</Customer>  
    <Key>0010</Key>  
  </Item>  
</Root>  
```  
  
## <a name="example"></a><span data-ttu-id="85432-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="85432-122">Example</span></span>  
<span data-ttu-id="85432-123">Nell'esempio seguente viene inoltre compilato l'esempio in [come eseguire il flusso di frammenti XML con accesso a informazioni diC#intestazione ()](./how-to-stream-xml-fragments-with-access-to-header-information.md).</span><span class="sxs-lookup"><span data-stu-id="85432-123">The following example also builds on the example in [How to stream XML fragments with access to header information (C#)](./how-to-stream-xml-fragments-with-access-to-header-information.md).</span></span>
  
 <span data-ttu-id="85432-124">In questo esempio viene usata la funzionalità di [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] per scrivere elementi in <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="85432-124">This example uses the capability of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] to write elements to an <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="85432-125">È possibile trasformare un documento di dimensioni molto grandi mantenendo un footprint di memoria ridotto.</span><span class="sxs-lookup"><span data-stu-id="85432-125">This example can transform a very large document while maintaining a small memory footprint.</span></span>  
  
 <span data-ttu-id="85432-126">Si noti che il metodo dell'asse personalizzato (`StreamCustomerItem`) è stato scritto in modo tale da prevedere un documento contenente elementi `Customer`, `Name` e `Item`, disposti come nel documento Source.xml seguente.</span><span class="sxs-lookup"><span data-stu-id="85432-126">Note that the custom axis (`StreamCustomerItem`) is specifically written so that it expects a document that has `Customer`, `Name`, and `Item` elements, and that those elements will be arranged as in the following Source.xml document.</span></span> <span data-ttu-id="85432-127">Tuttavia, un'implementazione più affidabile convaliderebbe il documento di origine con uno schema XSD oppure verrebbe preparata per analizzare un documento non valido.</span><span class="sxs-lookup"><span data-stu-id="85432-127">A more robust implementation, however, would either validate the source document with an XSD, or would be prepared to parse an invalid document.</span></span>  
  
 <span data-ttu-id="85432-128">In questo esempio viene usato lo stesso documento di origine, Source.xml, dell'esempio precedente in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="85432-128">This example uses the same source document, Source.xml, as the previous example in this topic.</span></span> <span data-ttu-id="85432-129">Viene inoltre prodotto esattamente lo stesso output.</span><span class="sxs-lookup"><span data-stu-id="85432-129">It also produces exactly the same output.</span></span>  
  
 <span data-ttu-id="85432-130">Per generare il flusso di output XML, è preferibile usare <xref:System.Xml.Linq.XStreamingElement> anziché scrivere in <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="85432-130">Using <xref:System.Xml.Linq.XStreamingElement> for streaming the output XML is preferred over writing to an <xref:System.Xml.XmlWriter>.</span></span>  
  
```csharp  
static IEnumerable<XElement> StreamCustomerItem(string uri)  
{  
    using (XmlReader reader = XmlReader.Create(uri))  
    {  
        XElement name = null;  
        XElement item = null;  
  
        reader.MoveToContent();  
  
        // Parse the file, save header information when encountered, and yield the  
        // Item XElement objects as they are created.  
  
        // loop through Customer elements  
        while (reader.Read())  
        {  
            if (reader.NodeType == XmlNodeType.Element  
                && reader.Name == "Customer")  
            {  
                // move to Name element  
                while (reader.Read())  
                {  
                    if (reader.NodeType == XmlNodeType.Element &&  
                        reader.Name == "Name")  
                    {  
                        name = XElement.ReadFrom(reader) as XElement;  
                        break;  
                    }  
                }  
  
                // loop through Item elements  
                while (reader.Read())  
                {  
                    if (reader.NodeType == XmlNodeType.EndElement)  
                        break;  
                    if (reader.NodeType == XmlNodeType.Element  
                        && reader.Name == "Item")  
                    {  
                        item = XElement.ReadFrom(reader) as XElement;  
                        if (item != null) {  
                            XElement tempRoot = new XElement("Root",  
                                new XElement(name)  
                            );  
                            tempRoot.Add(item);  
                            yield return item;  
                        }  
                    }  
                }  
            }  
        }  
    }  
}  
  
static void Main(string[] args)  
{  
    IEnumerable<XElement> srcTree =  
        from el in StreamCustomerItem("Source.xml")  
        select new XElement("Item",  
            new XElement("Customer", (string)el.Parent.Element("Name")),  
            new XElement(el.Element("Key"))  
        );  
    XmlWriterSettings xws = new XmlWriterSettings();  
    xws.OmitXmlDeclaration = true;  
    xws.Indent = true;  
    using (XmlWriter xw = XmlWriter.Create("Output.xml", xws)) {  
        xw.WriteStartElement("Root");  
        foreach (XElement el in srcTree)  
            el.WriteTo(xw);  
        xw.WriteEndElement();  
    }  
  
    string str = File.ReadAllText("Output.xml");  
    Console.WriteLine(str);  
}  
```  
  
 <span data-ttu-id="85432-131">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="85432-131">This code produces the following output:</span></span>  
  
```xml  
<Root>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0001</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0002</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0003</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0004</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0005</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0006</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0007</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0008</Key>  
  </Item>  
  <Item>  
    <Customer>Southridge Video</Customer>  
    <Key>0009</Key>  
  </Item>  
  <Item>  
    <Customer>Southridge Video</Customer>  
    <Key>0010</Key>  
  </Item>  
</Root>  
```  
  