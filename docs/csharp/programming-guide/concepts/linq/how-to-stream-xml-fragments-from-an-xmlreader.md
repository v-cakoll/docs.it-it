---
title: Come eseguire il flusso di frammenti XML da un XmlReader (C
ms.date: 07/20/2015
ms.assetid: 4a8f0e45-768a-42e2-bc5f-68bdf0e0a726
ms.openlocfilehash: f7914d33622518f983a685dd2e844a25fd3ca15f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75714646"
---
# <a name="how-to-stream-xml-fragments-from-an-xmlreader-c"></a><span data-ttu-id="13e3a-102">Come eseguire il flusso di frammenti XML da un XmlReader (C</span><span class="sxs-lookup"><span data-stu-id="13e3a-102">How to stream XML fragments from an XmlReader (C#)</span></span>

<span data-ttu-id="13e3a-103">Quando è necessario elaborare file XML di grandi dimensioni, potrebbe risultare impossibile caricare in memoria l'intero albero XML.</span><span class="sxs-lookup"><span data-stu-id="13e3a-103">When you have to process large XML files, it might not be feasible to load the whole XML tree into memory.</span></span> <span data-ttu-id="13e3a-104">In questo argomento viene illustrato come generare il flusso di frammenti tramite <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="13e3a-104">This topic shows how to stream fragments using an <xref:System.Xml.XmlReader>.</span></span>  
  
 <span data-ttu-id="13e3a-105">Uno dei modi più efficaci per usare un oggetto <xref:System.Xml.XmlReader> per leggere oggetti <xref:System.Xml.Linq.XElement> consiste nello scrivere un metodo dell'asse personalizzato.</span><span class="sxs-lookup"><span data-stu-id="13e3a-105">One of the most effective ways to use an <xref:System.Xml.XmlReader> to read <xref:System.Xml.Linq.XElement> objects is to write your own custom axis method.</span></span> <span data-ttu-id="13e3a-106">Un metodo dell'asse restituisce in genere una raccolta, ad esempio <xref:System.Collections.Generic.IEnumerable%601> di <xref:System.Xml.Linq.XElement>, come illustrato nell'esempio di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="13e3a-106">An axis method typically returns a collection such as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, as shown in the example in this topic.</span></span> <span data-ttu-id="13e3a-107">Nel metodo dell'asse personalizzato, dopo avere creato il frammento XML chiamando il metodo <xref:System.Xml.Linq.XNode.ReadFrom%2A>, restituire la raccolta usando `yield return`.</span><span class="sxs-lookup"><span data-stu-id="13e3a-107">In the custom axis method, after you create the XML fragment by calling the <xref:System.Xml.Linq.XNode.ReadFrom%2A> method, return the collection using `yield return`.</span></span> <span data-ttu-id="13e3a-108">In questo modo si fornisce la semantica di esecuzione posticipata al metodo dell'asse personalizzato.</span><span class="sxs-lookup"><span data-stu-id="13e3a-108">This provides deferred execution semantics to your custom axis method.</span></span>  
  
 <span data-ttu-id="13e3a-109">Quando si crea un albero XML da un oggetto <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlReader> deve essere posizionato su un elemento.</span><span class="sxs-lookup"><span data-stu-id="13e3a-109">When you create an XML tree from an <xref:System.Xml.XmlReader> object, the <xref:System.Xml.XmlReader> must be positioned on an element.</span></span> <span data-ttu-id="13e3a-110">Il metodo <xref:System.Xml.Linq.XNode.ReadFrom%2A> restituisce risultati solo dopo aver letto il tag di chiusura dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="13e3a-110">The <xref:System.Xml.Linq.XNode.ReadFrom%2A> method does not return until it has read the close tag of the element.</span></span>  
  
 <span data-ttu-id="13e3a-111">Se si desidera creare un albero parziale, è possibile creare un'istanza di <xref:System.Xml.XmlReader>, posizionare il lettore sul nodo da convertire in un albero <xref:System.Xml.Linq.XElement> e quindi creare l'oggetto <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="13e3a-111">If you want to create a partial tree, you can instantiate an <xref:System.Xml.XmlReader>, position the reader on the node that you want to convert to an <xref:System.Xml.Linq.XElement> tree, and then create the <xref:System.Xml.Linq.XElement> object.</span></span>  
  
<span data-ttu-id="13e3a-112">L'argomento [Come trasmettere frammenti XML con accesso alle informazioni di intestazione (C )](./how-to-stream-xml-fragments-with-access-to-header-information.md) contiene informazioni e un esempio su come trasmettere un documento più complesso.</span><span class="sxs-lookup"><span data-stu-id="13e3a-112">The topic [How to stream XML fragments with access to header information (C#)](./how-to-stream-xml-fragments-with-access-to-header-information.md) contains information and an example on how to stream a more complex document.</span></span>
  
 <span data-ttu-id="13e3a-113">L'argomento Come eseguire la [trasformazione di flusso di documenti XML di grandi dimensioni (C )](./how-to-perform-streaming-transform-of-large-xml-documents.md) contiene un esempio di utilizzo di LINQ to XMLLINQ to XML per trasformare documenti XML di grandi dimensioni mantenendo un footprint di memoria ridotto.</span><span class="sxs-lookup"><span data-stu-id="13e3a-113">The topic [How to perform streaming transform of large XML documents (C#)](./how-to-perform-streaming-transform-of-large-xml-documents.md) contains an example of using LINQ to XML to transform extremely large XML documents while maintaining a small memory footprint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13e3a-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="13e3a-114">Example</span></span>  
 <span data-ttu-id="13e3a-115">In questo esempio viene creato un metodo dell'asse personalizzato.</span><span class="sxs-lookup"><span data-stu-id="13e3a-115">This example creates a custom axis method.</span></span> <span data-ttu-id="13e3a-116">È possibile eseguire una query utilizzando una query LINQ.</span><span class="sxs-lookup"><span data-stu-id="13e3a-116">You can query it by using a LINQ query.</span></span> <span data-ttu-id="13e3a-117">Il metodo dell'asse personalizzato `StreamRootChildDoc` è progettato specificamente per leggere un documento contenente un elemento `Child` ripetuto.</span><span class="sxs-lookup"><span data-stu-id="13e3a-117">The custom axis method, `StreamRootChildDoc`, is a method that is designed specifically to read a document that has a repeating `Child` element.</span></span>  
  
```csharp  
static IEnumerable<XElement> StreamRootChildDoc(StringReader stringReader)  
{  
    using (XmlReader reader = XmlReader.Create(stringReader))  
    {  
        reader.MoveToContent();  
        // Parse the file and display each of the nodes.  
        while (reader.Read())  
        {  
            switch (reader.NodeType)  
            {  
                case XmlNodeType.Element:  
                    if (reader.Name == "Child") {  
                        XElement el = XElement.ReadFrom(reader) as XElement;  
                        if (el != null)  
                            yield return el;  
                    }  
                    break;  
            }  
        }  
    }  
}  
  
static void Main(string[] args)  
{  
    string markup = @"<Root>  
      <Child Key=""01"">  
        <GrandChild>aaa</GrandChild>  
      </Child>  
      <Child Key=""02"">  
        <GrandChild>bbb</GrandChild>  
      </Child>  
      <Child Key=""03"">  
        <GrandChild>ccc</GrandChild>  
      </Child>  
    </Root>";  
  
    IEnumerable<string> grandChildData =  
        from el in StreamRootChildDoc(new StringReader(markup))  
        where (int)el.Attribute("Key") > 1  
        select (string)el.Element("GrandChild");  
  
    foreach (string str in grandChildData) {  
        Console.WriteLine(str);  
    }  
}  
```  
  
 <span data-ttu-id="13e3a-118">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="13e3a-118">This example produces the following output:</span></span>  
  
```output  
bbb  
ccc  
```  
  
 <span data-ttu-id="13e3a-119">In questo esempio il documento di origine è molto piccolo.</span><span class="sxs-lookup"><span data-stu-id="13e3a-119">In this example, the source document is very small.</span></span> <span data-ttu-id="13e3a-120">Tuttavia, anche contenesse milioni di elementi `Child`, il footprint di memoria di questo esempio sarebbe comunque ridotto.</span><span class="sxs-lookup"><span data-stu-id="13e3a-120">However, even if there were millions of `Child` elements, this example would still have a small memory footprint.</span></span>  
