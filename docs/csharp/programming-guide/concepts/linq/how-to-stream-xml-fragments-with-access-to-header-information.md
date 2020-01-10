---
title: Come eseguire lo streaming di frammenti XML con accesso a informazioni diC#intestazione ()
ms.date: 07/20/2015
ms.assetid: 7f242770-b0c7-418d-894b-643215e1f8aa
ms.openlocfilehash: 5bc10bcadae0e33ee63f953608ca841d44dd6527
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712390"
---
# <a name="how-to-stream-xml-fragments-with-access-to-header-information-c"></a><span data-ttu-id="f68ca-102">Come eseguire lo streaming di frammenti XML con accesso a informazioni diC#intestazione ()</span><span class="sxs-lookup"><span data-stu-id="f68ca-102">How to stream XML fragments with access to header information (C#)</span></span>
<span data-ttu-id="f68ca-103">A volte è necessario leggere file XML arbitrariamente grandi e scrivere l'applicazione in modo tale che il footprint di memoria dell'applicazione sia prevedibile.</span><span class="sxs-lookup"><span data-stu-id="f68ca-103">Sometimes you have to read arbitrarily large XML files, and write your application so that the memory footprint of the application is predictable.</span></span> <span data-ttu-id="f68ca-104">Se si tenta di popolare un albero XML con un file XML di grandi dimensioni, l'uso della memoria sarà proporzionale alla dimensione del file (ovvero, eccessivo).</span><span class="sxs-lookup"><span data-stu-id="f68ca-104">If you attempt to populate an XML tree with a large XML file, your memory usage will be proportional to the size of the file—that is, excessive.</span></span> <span data-ttu-id="f68ca-105">Pertanto, è necessario usare una tecnica di flusso in sostituzione.</span><span class="sxs-lookup"><span data-stu-id="f68ca-105">Therefore, you should use a streaming technique instead.</span></span>  
  
<span data-ttu-id="f68ca-106">Una delle opzioni disponibili consiste nello scrivere l'applicazione usando <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="f68ca-106">One option is to write your application using <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="f68ca-107">Tuttavia, potrebbe essere necessario usare LINQ per eseguire una query sull'albero XML.</span><span class="sxs-lookup"><span data-stu-id="f68ca-107">However, you might want to use LINQ to query the XML tree.</span></span> <span data-ttu-id="f68ca-108">In questo caso, è possibile scrivere un metodo dell'asse personalizzato.</span><span class="sxs-lookup"><span data-stu-id="f68ca-108">If this is the case, you can write your own custom axis method.</span></span> <span data-ttu-id="f68ca-109">Per ulteriori informazioni, vedere [come scrivere un metodo dell'asse LINQ to XML (C#)](./how-to-write-a-linq-to-xml-axis-method.md).</span><span class="sxs-lookup"><span data-stu-id="f68ca-109">For more information, see [How to write a LINQ to XML axis method (C#)](./how-to-write-a-linq-to-xml-axis-method.md).</span></span>
  
 <span data-ttu-id="f68ca-110">Per scrivere metodo dell'asse, scrivere un piccolo metodo che usa <xref:System.Xml.XmlReader> per leggere i nodi fino a raggiungere uno dei nodi di interesse.</span><span class="sxs-lookup"><span data-stu-id="f68ca-110">To write your own axis method, you write a small method that uses the <xref:System.Xml.XmlReader> to read nodes until it reaches one of the nodes in which you are interested.</span></span> <span data-ttu-id="f68ca-111">Il metodo chiama quindi <xref:System.Xml.Linq.XNode.ReadFrom%2A>, che legge da <xref:System.Xml.XmlReader> e crea un'istanza di un frammento XML.</span><span class="sxs-lookup"><span data-stu-id="f68ca-111">The method then calls <xref:System.Xml.Linq.XNode.ReadFrom%2A>, which reads from the <xref:System.Xml.XmlReader> and instantiates an XML fragment.</span></span> <span data-ttu-id="f68ca-112">Restituisce quindi ogni frammento tramite `yield return` al metodo che sta enumerando il metodo dell'asse personalizzato.</span><span class="sxs-lookup"><span data-stu-id="f68ca-112">It then yields each fragment through `yield return` to the method that is enumerating your custom axis method.</span></span> <span data-ttu-id="f68ca-113">È quindi possibile scrivere query LINQ sul metodo dell'asse personalizzato.</span><span class="sxs-lookup"><span data-stu-id="f68ca-113">You can then write LINQ queries on your custom axis method.</span></span>  
  
 <span data-ttu-id="f68ca-114">Le tecniche di flusso sono maggiormente indicate nelle situazioni in cui è necessario elaborare solo una volta il documento di origine ed è possibile elaborare gli elementi in base all'ordine in cui sono riportati nel documento.</span><span class="sxs-lookup"><span data-stu-id="f68ca-114">Streaming techniques are best applied in situations where you need to process the source document only once, and you can process the elements in document order.</span></span> <span data-ttu-id="f68ca-115">Determinati operatori di query standard, ad esempio <xref:System.Linq.Enumerable.OrderBy%2A>, scorrono l'origine, raccolgono tutti i dati, li ordinano e infine restituiscono il primo elemento nella sequenza.</span><span class="sxs-lookup"><span data-stu-id="f68ca-115">Certain standard query operators, such as <xref:System.Linq.Enumerable.OrderBy%2A>, iterate their source, collect all of the data, sort it, and then finally yield the first item in the sequence.</span></span> <span data-ttu-id="f68ca-116">Se si usa un operatore di query che materializza l'origine prima di restituire il primo elemento, non si manterrà un footprint di memoria ridotto.</span><span class="sxs-lookup"><span data-stu-id="f68ca-116">If you use a query operator that materializes its source before yielding the first item, you will not retain a small memory footprint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f68ca-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="f68ca-117">Example</span></span>  

<span data-ttu-id="f68ca-118">A volte il problema diventa più interessante.</span><span class="sxs-lookup"><span data-stu-id="f68ca-118">Sometimes the problem gets just a little more interesting.</span></span> <span data-ttu-id="f68ca-119">Nel documento XML seguente, il consumer del metodo dell'asse personalizzato deve conoscere anche il nome del cliente cui appartiene ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="f68ca-119">In the following XML document, the consumer of your custom axis method also has to know the name of the customer that each item belongs to.</span></span>  
  
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
  
 <span data-ttu-id="f68ca-120">L'approccio adottato in questo esempio prevede anche di cercare queste informazioni di intestazione, salvarle e quindi compilare un piccolo albero XML che contiene sia le informazioni di intestazione che i dettagli enumerati.</span><span class="sxs-lookup"><span data-stu-id="f68ca-120">The approach that this example takes is to also watch for this header information, save the header information, and then build a small XML tree that contains both the header information and the detail that you are enumerating.</span></span> <span data-ttu-id="f68ca-121">Il metodo dell'asse restituisce questo nuovo, piccolo albero XML.</span><span class="sxs-lookup"><span data-stu-id="f68ca-121">The axis method then yields this new, small XML tree.</span></span> <span data-ttu-id="f68ca-122">La query ha quindi accesso alle informazioni di intestazione oltre a quelle sui dettagli.</span><span class="sxs-lookup"><span data-stu-id="f68ca-122">The query then has access to the header information as well as the detail information.</span></span>  
  
 <span data-ttu-id="f68ca-123">Questo approccio prevede un footprint di memoria ridotto.</span><span class="sxs-lookup"><span data-stu-id="f68ca-123">This approach has a small memory footprint.</span></span> <span data-ttu-id="f68ca-124">Quando viene restituito un frammento XML, non viene mantenuto alcun riferimento al frammento precedente, che diventa disponibile per Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="f68ca-124">As each detail XML fragment is yielded, no references are kept to the previous fragment, and it is available for garbage collection.</span></span> <span data-ttu-id="f68ca-125">Questa tecnica crea molti oggetti di breve durata nell'heap.</span><span class="sxs-lookup"><span data-stu-id="f68ca-125">This technique creates many short lived objects on the heap.</span></span>  
  
 <span data-ttu-id="f68ca-126">Nell'esempio seguente viene illustrato come implementare e usare un metodo dell'asse personalizzato che genera un flusso di frammenti XML dal file specificato dall'URI.</span><span class="sxs-lookup"><span data-stu-id="f68ca-126">The following example shows how to implement and use a custom axis method that streams XML fragments from the file specified by the URI.</span></span> <span data-ttu-id="f68ca-127">Questo asse personalizzato viene scritto in modo che preveda un documento con elementi `Customer`, `Name`e `Item` e che tali elementi verranno disposti come nel documento di `Source.xml` precedente.</span><span class="sxs-lookup"><span data-stu-id="f68ca-127">This custom axis is written such that it expects a document that has `Customer`, `Name`, and `Item` elements, and that those elements will be arranged as in the above `Source.xml` document.</span></span> <span data-ttu-id="f68ca-128">Si tratta di un'implementazione semplicistica.</span><span class="sxs-lookup"><span data-stu-id="f68ca-128">It is a simplistic implementation.</span></span> <span data-ttu-id="f68ca-129">Un'implementazione più solida sarebbe in grado di analizzare un documento non valido.</span><span class="sxs-lookup"><span data-stu-id="f68ca-129">A more robust implementation would be prepared to parse an invalid document.</span></span>  
  
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
    XElement xmlTree = new XElement("Root",  
        from el in StreamCustomerItem("Source.xml")  
        where (int)el.Element("Key") >= 3 && (int)el.Element("Key") <= 7  
        select new XElement("Item",  
            new XElement("Customer", (string)el.Parent.Element("Name")),  
            new XElement(el.Element("Key"))  
        )  
    );  
    Console.WriteLine(xmlTree);  
}  
```  
  
 <span data-ttu-id="f68ca-130">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="f68ca-130">This code produces the following output:</span></span>  
  
```xml  
<Root>  
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
</Root>  
```  
