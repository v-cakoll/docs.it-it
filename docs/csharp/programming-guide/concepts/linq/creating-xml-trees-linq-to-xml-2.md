---
title: Creazione di alberi in C# (LINQ to XML)
description: Informazioni sulla creazione di alberi XML in C#, inclusa la costruzione di elementi e l'uso di costruttori XElement.
ms.date: 08/31/2018
ms.assetid: cc74234a-0bac-4327-9c8c-5a2ead15b595
ms.openlocfilehash: 3991f461c4c870a64320853ccd1d45026a8a6bf6
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105472"
---
# <a name="creating-xml-trees-in-c-linq-to-xml"></a><span data-ttu-id="961f0-103">Creazione di alberi in C# (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="961f0-103">Creating XML trees in C# (LINQ to XML)</span></span>
<span data-ttu-id="961f0-104">In questa sezione vengono fornite informazioni sulla creazione di alberi XML in C#.</span><span class="sxs-lookup"><span data-stu-id="961f0-104">This section provides information about creating XML trees in C#.</span></span>  
  
 <span data-ttu-id="961f0-105">Per informazioni sull'uso dei risultati delle query LINQ come contenuto per un oggetto <xref:System.Xml.Linq.XElement>, vedere [Costruzione funzionale (LINQ to XML) (C#)](./functional-construction-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="961f0-105">For information about using the results of LINQ queries as the content for an <xref:System.Xml.Linq.XElement>, see [Functional Construction (LINQ to XML) (C#)](./functional-construction-linq-to-xml.md).</span></span>  
  
## <a name="constructing-elements"></a><span data-ttu-id="961f0-106">Costruzione di elementi</span><span class="sxs-lookup"><span data-stu-id="961f0-106">Constructing elements</span></span>
 <span data-ttu-id="961f0-107">Le firme dei costruttori <xref:System.Xml.Linq.XElement> e <xref:System.Xml.Linq.XAttribute> consentono di passare come argomenti del costruttore il contenuto dell'elemento o dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="961f0-107">The signatures of the <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XAttribute> constructors let you pass the contents of the element or attribute as arguments to the constructor.</span></span> <span data-ttu-id="961f0-108">Poiché uno dei costruttori accetta un numero variabile di argomenti, è possibile passare un qualsiasi numero di elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="961f0-108">Because one of the constructors takes a variable number of arguments, you can pass any number of child elements.</span></span> <span data-ttu-id="961f0-109">Ognuno degli elementi figlio può naturalmente contenere elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="961f0-109">Of course, each of those child elements can contain their own child elements.</span></span> <span data-ttu-id="961f0-110">Per qualsiasi elemento è possibile aggiungere un qualsiasi numero di attributi.</span><span class="sxs-lookup"><span data-stu-id="961f0-110">For any element, you can add any number of attributes.</span></span>  
  
 <span data-ttu-id="961f0-111">Se quando si aggiungono oggetti <xref:System.Xml.Linq.XNode> (incluso <xref:System.Xml.Linq.XElement>) o <xref:System.Xml.Linq.XAttribute>, il nuovo contenuto non ha elementi padre, gli oggetti vengono semplicemente collegati all'albero XML.</span><span class="sxs-lookup"><span data-stu-id="961f0-111">When adding <xref:System.Xml.Linq.XNode> (including <xref:System.Xml.Linq.XElement>) or <xref:System.Xml.Linq.XAttribute> objects, if the new content has no parent, the objects are simply attached to the XML tree.</span></span> <span data-ttu-id="961f0-112">Se invece il nuovo contenuto include già elementi padre e fa parte di un altro albero XML, viene duplicato e quindi collegato all'albero XML.</span><span class="sxs-lookup"><span data-stu-id="961f0-112">If the new content already is parented, and is part of another XML tree, the new content is cloned, and the newly cloned content is attached to the XML tree.</span></span> <span data-ttu-id="961f0-113">Tale comportamento è illustrato nell'ultimo esempio di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="961f0-113">The last example in this topic demonstrates this.</span></span>  
  
 <span data-ttu-id="961f0-114">Per creare un oggetto `contacts`<xref:System.Xml.Linq.XElement>, è possibile usare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="961f0-114">To create a `contacts`<xref:System.Xml.Linq.XElement>, you could use the following code:</span></span>  
  
```csharp  
XElement contacts =  
    new XElement("Contacts",  
        new XElement("Contact",  
            new XElement("Name", "Patrick Hines"),
            new XElement("Phone", "206-555-0144"),  
            new XElement("Address",  
                new XElement("Street1", "123 Main St"),  
                new XElement("City", "Mercer Island"),  
                new XElement("State", "WA"),  
                new XElement("Postal", "68042")  
            )  
        )  
    );  
```  
  
 <span data-ttu-id="961f0-115">Se i rientri sono stati impostati correttamente, il codice per costruire oggetti <xref:System.Xml.Linq.XElement> è molto simile alla struttura del codice XML sottostante.</span><span class="sxs-lookup"><span data-stu-id="961f0-115">If indented properly, the code to construct <xref:System.Xml.Linq.XElement> objects closely resembles the structure of the underlying XML.</span></span>  
  
## <a name="xelement-constructors"></a><span data-ttu-id="961f0-116">Costruttori XElement</span><span class="sxs-lookup"><span data-stu-id="961f0-116">XElement constructors</span></span>  
 <span data-ttu-id="961f0-117">La classe <xref:System.Xml.Linq.XElement> usa i costruttori seguenti per la costruzione funzionale.</span><span class="sxs-lookup"><span data-stu-id="961f0-117">The <xref:System.Xml.Linq.XElement> class uses the following constructors for functional construction.</span></span> <span data-ttu-id="961f0-118">Notare che esistono altri costruttori per <xref:System.Xml.Linq.XElement>, che tuttavia non vengono elencati in questa sede perché non usati per la costruzione funzionale.</span><span class="sxs-lookup"><span data-stu-id="961f0-118">Note that there are some other constructors for <xref:System.Xml.Linq.XElement>, but because they are not used for functional construction they are not listed here.</span></span>  
  
|<span data-ttu-id="961f0-119">Costruttore</span><span class="sxs-lookup"><span data-stu-id="961f0-119">Constructor</span></span>|<span data-ttu-id="961f0-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="961f0-120">Description</span></span>|  
|-----------------|-----------------|  
|`XElement(XName name, object content)`|<span data-ttu-id="961f0-121">Crea un oggetto <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="961f0-121">Creates an <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="961f0-122">Il parametro `name` specifica il nome dell'elemento, mentre il parametro `content` ne specifica il contenuto.</span><span class="sxs-lookup"><span data-stu-id="961f0-122">The `name` parameter specifies the name of the element; `content` specifies the content of the element.</span></span>|  
|`XElement(XName name)`|<span data-ttu-id="961f0-123">Crea un oggetto <xref:System.Xml.Linq.XElement> il cui <xref:System.Xml.Linq.XName> viene inizializzato in base al nome specificato.</span><span class="sxs-lookup"><span data-stu-id="961f0-123">Creates an <xref:System.Xml.Linq.XElement> with its <xref:System.Xml.Linq.XName> initialized to the specified name.</span></span>|  
|`XElement(XName name, params object[] content)`|<span data-ttu-id="961f0-124">Crea un oggetto <xref:System.Xml.Linq.XElement> il cui <xref:System.Xml.Linq.XName> viene inizializzato in base al nome specificato.</span><span class="sxs-lookup"><span data-stu-id="961f0-124">Creates an <xref:System.Xml.Linq.XElement> with its <xref:System.Xml.Linq.XName> initialized to the specified name.</span></span> <span data-ttu-id="961f0-125">Gli attributi e/o elementi figlio vengono creati dal contenuto dell'elenco di parametri.</span><span class="sxs-lookup"><span data-stu-id="961f0-125">The attributes and/or child elements are created from the contents of the parameter list.</span></span>|  
  
 <span data-ttu-id="961f0-126">Il parametro `content` è estremamente flessibile.</span><span class="sxs-lookup"><span data-stu-id="961f0-126">The `content` parameter is extremely flexible.</span></span> <span data-ttu-id="961f0-127">Supporta qualsiasi tipo di oggetto che corrisponde a un elemento figlio valido di un oggetto <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="961f0-127">It supports any type of object that is a valid child of an <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="961f0-128">Ai tipi diversi di oggetti passati in questo parametro si applicano le regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="961f0-128">The following rules apply to different types of objects passed in this parameter:</span></span>  
  
- <span data-ttu-id="961f0-129">Una stringa viene aggiunta come contenuto di tipo testo.</span><span class="sxs-lookup"><span data-stu-id="961f0-129">A string is added as text content.</span></span>  
  
- <span data-ttu-id="961f0-130">Un oggetto <xref:System.Xml.Linq.XElement> viene aggiunto come elemento figlio.</span><span class="sxs-lookup"><span data-stu-id="961f0-130">An <xref:System.Xml.Linq.XElement> is added as a child element.</span></span>  
  
- <span data-ttu-id="961f0-131">Un oggetto <xref:System.Xml.Linq.XAttribute> viene aggiunto come attributo.</span><span class="sxs-lookup"><span data-stu-id="961f0-131">An <xref:System.Xml.Linq.XAttribute> is added as an attribute.</span></span>  
  
- <span data-ttu-id="961f0-132">Un oggetto <xref:System.Xml.Linq.XProcessingInstruction>, <xref:System.Xml.Linq.XComment> o <xref:System.Xml.Linq.XText> viene aggiunto come contenuto di elemento figlio.</span><span class="sxs-lookup"><span data-stu-id="961f0-132">An <xref:System.Xml.Linq.XProcessingInstruction>, <xref:System.Xml.Linq.XComment>, or <xref:System.Xml.Linq.XText> is added as child content.</span></span>  
  
- <span data-ttu-id="961f0-133">Viene enumerato un oggetto <xref:System.Collections.IEnumerable> e queste regole vengono applicate in modo ricorsivo ai risultati.</span><span class="sxs-lookup"><span data-stu-id="961f0-133">An <xref:System.Collections.IEnumerable> is enumerated, and these rules are applied recursively to the results.</span></span>  
  
- <span data-ttu-id="961f0-134">Per qualsiasi altro tipo viene chiamato il metodo `ToString` e il risultato viene aggiunto come contenuto di tipo testo.</span><span class="sxs-lookup"><span data-stu-id="961f0-134">For any other type, its `ToString` method is called and the result is added as text content.</span></span>  
  
### <a name="creating-an-xelement-with-content"></a><span data-ttu-id="961f0-135">Creazione di un XElement con contenuto</span><span class="sxs-lookup"><span data-stu-id="961f0-135">Creating an XElement with content</span></span>  
 <span data-ttu-id="961f0-136">È possibile creare un oggetto <xref:System.Xml.Linq.XElement> con contenuto semplice usando una sola chiamata di metodo.</span><span class="sxs-lookup"><span data-stu-id="961f0-136">You can create an <xref:System.Xml.Linq.XElement> that contains simple content with a single method call.</span></span> <span data-ttu-id="961f0-137">A tale scopo, specificare il contenuto come secondo parametro, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="961f0-137">To do this, specify the content as the second parameter, as follows:</span></span>  
  
```csharp  
XElement n = new XElement("Customer", "Adventure Works");  
Console.WriteLine(n);  
```  
  
 <span data-ttu-id="961f0-138">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="961f0-138">This example produces the following output:</span></span>  
  
```xml  
<Customer>Adventure Works</Customer>  
```  
  
 <span data-ttu-id="961f0-139">È possibile passare come contenuto qualsiasi tipo di oggetto.</span><span class="sxs-lookup"><span data-stu-id="961f0-139">You can pass any type of object as the content.</span></span> <span data-ttu-id="961f0-140">Ad esempio, nel codice seguente viene creato un elemento il cui contenuto è un numero a virgola mobile:</span><span class="sxs-lookup"><span data-stu-id="961f0-140">For example, the following code creates an element that contains a floating point number as content:</span></span>  
  
```csharp  
XElement n = new XElement("Cost", 324.50);  
Console.WriteLine(n);  
```  
  
 <span data-ttu-id="961f0-141">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="961f0-141">This example produces the following output:</span></span>  
  
```xml  
<Cost>324.5</Cost>  
```  
  
 <span data-ttu-id="961f0-142">Il numero a virgola mobile viene sottoposto a boxing e quindi passato al costruttore.</span><span class="sxs-lookup"><span data-stu-id="961f0-142">The floating point number is boxed and passed in to the constructor.</span></span> <span data-ttu-id="961f0-143">Il numero boxed viene convertito in una stringa e usato come contenuto dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="961f0-143">The boxed number is converted to a string and used as the content of the element.</span></span>  
  
### <a name="creating-an-xelement-with-a-child-element"></a><span data-ttu-id="961f0-144">Creazione di un XElement con un elemento figlio</span><span class="sxs-lookup"><span data-stu-id="961f0-144">Creating an XElement with a child element</span></span>  
 <span data-ttu-id="961f0-145">Se si passa un'istanza della classe <xref:System.Xml.Linq.XElement> come argomento del contenuto, il costruttore crea un elemento con un elemento figlio:</span><span class="sxs-lookup"><span data-stu-id="961f0-145">If you pass an instance of the <xref:System.Xml.Linq.XElement> class for the content argument, the constructor creates an element with a child element:</span></span>  
  
```csharp  
XElement shippingUnit = new XElement("ShippingUnit",  
    new XElement("Cost", 324.50)  
);  
Console.WriteLine(shippingUnit);  
```  
  
 <span data-ttu-id="961f0-146">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="961f0-146">This example produces the following output:</span></span>  
  
```xml  
<ShippingUnit>  
  <Cost>324.5</Cost>  
</ShippingUnit>  
```  
  
### <a name="creating-an-xelement-with-multiple-child-elements"></a><span data-ttu-id="961f0-147">Creazione di un XElement con più elementi figlio</span><span class="sxs-lookup"><span data-stu-id="961f0-147">Creating an XElement with multiple child elements</span></span>  
 <span data-ttu-id="961f0-148">È possibile passare più oggetti <xref:System.Xml.Linq.XElement> per il contenuto.</span><span class="sxs-lookup"><span data-stu-id="961f0-148">You can pass in a number of <xref:System.Xml.Linq.XElement> objects for the content.</span></span> <span data-ttu-id="961f0-149">Ognuno degli oggetti <xref:System.Xml.Linq.XElement> viene incluso come elemento figlio.</span><span class="sxs-lookup"><span data-stu-id="961f0-149">Each of the <xref:System.Xml.Linq.XElement> objects is included as a child element.</span></span>  
  
```csharp  
XElement address = new XElement("Address",  
    new XElement("Street1", "123 Main St"),  
    new XElement("City", "Mercer Island"),  
    new XElement("State", "WA"),  
    new XElement("Postal", "68042")  
);  
Console.WriteLine(address);  
```  
  
 <span data-ttu-id="961f0-150">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="961f0-150">This example produces the following output:</span></span>  
  
```xml  
<Address>  
  <Street1>123 Main St</Street1>  
  <City>Mercer Island</City>  
  <State>WA</State>  
  <Postal>68042</Postal>  
</Address>  
```  
  
 <span data-ttu-id="961f0-151">Estendendo l'esempio precedente, è possibile creare un intero albero XML, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="961f0-151">By extending the above example, you can create an entire XML tree, as follows:</span></span>  
  
```csharp  
XElement contacts =  
    new XElement("Contacts",  
        new XElement("Contact",  
            new XElement("Name", "Patrick Hines"),
            new XElement("Phone", "206-555-0144"),  
            new XElement("Address",  
                new XElement("Street1", "123 Main St"),  
                new XElement("City", "Mercer Island"),  
                new XElement("State", "WA"),  
                new XElement("Postal", "68042")  
            )  
        )  
    );  
Console.WriteLine(contacts);  
```  
  
 <span data-ttu-id="961f0-152">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="961f0-152">This example produces the following output:</span></span>  
  
```xml  
<Contacts>  
  <Contact>  
    <Name>Patrick Hines</Name>  
    <Phone>206-555-0144</Phone>  
    <Address>  
      <Street1>123 Main St</Street1>  
      <City>Mercer Island</City>  
      <State>WA</State>  
      <Postal>68042</Postal>  
    </Address>  
  </Contact>  
</Contacts>  
```  

### <a name="creating-an-xelement-with-an-xattribute"></a><span data-ttu-id="961f0-153">Creazione di un XElement con XAttribute</span><span class="sxs-lookup"><span data-stu-id="961f0-153">Creating an XElement with an XAttribute</span></span>
 <span data-ttu-id="961f0-154">Se si passa un'istanza della classe <xref:System.Xml.Linq.XAttribute> come argomento del contenuto, il costruttore crea un elemento con un attributo:</span><span class="sxs-lookup"><span data-stu-id="961f0-154">If you pass an instance of the <xref:System.Xml.Linq.XAttribute> class for the content argument, the constructor creates an element with an attribute:</span></span>

```csharp  
XElement phone = new XElement("Phone",  
    new XAttribute("Type", "Home"),  
    "555-555-5555");  
Console.WriteLine(phone);  
```  
  
 <span data-ttu-id="961f0-155">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="961f0-155">This example produces the following output:</span></span>  
  
```xml  
<Phone Type="Home">555-555-5555</Phone>
```

### <a name="creating-an-empty-element"></a><span data-ttu-id="961f0-156">Creazione di un elemento vuoto</span><span class="sxs-lookup"><span data-stu-id="961f0-156">Creating an empty element</span></span>  
 <span data-ttu-id="961f0-157">Per creare un oggetto <xref:System.Xml.Linq.XElement> vuoto, non viene passato nessun contenuto al costruttore.</span><span class="sxs-lookup"><span data-stu-id="961f0-157">To create an empty <xref:System.Xml.Linq.XElement>, you do not pass any content to the constructor.</span></span> <span data-ttu-id="961f0-158">Nell'esempio seguente creato un elemento vuoto.</span><span class="sxs-lookup"><span data-stu-id="961f0-158">The following example creates an empty element:</span></span>  
  
```csharp  
XElement n = new XElement("Customer");  
Console.WriteLine(n);  
```  
  
 <span data-ttu-id="961f0-159">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="961f0-159">This example produces the following output:</span></span>  
  
```xml  
<Customer />  
```  
  
### <a name="attaching-vs-cloning"></a><span data-ttu-id="961f0-160">Collegamento e duplicazione</span><span class="sxs-lookup"><span data-stu-id="961f0-160">Attaching vs. cloning</span></span>  
 <span data-ttu-id="961f0-161">Come accennato in precedenza, se quando si aggiungono oggetti <xref:System.Xml.Linq.XNode> (incluso <xref:System.Xml.Linq.XElement>) o <xref:System.Xml.Linq.XAttribute>, il nuovo contenuto non ha elementi padre, gli oggetti vengono semplicemente collegati all'albero XML.</span><span class="sxs-lookup"><span data-stu-id="961f0-161">As mentioned previously, when adding <xref:System.Xml.Linq.XNode> (including <xref:System.Xml.Linq.XElement>) or <xref:System.Xml.Linq.XAttribute> objects, if the new content has no parent, the objects are simply attached to the XML tree.</span></span> <span data-ttu-id="961f0-162">Se invece il nuovo contenuto include già elementi padre e fa parte di un altro albero XML, viene duplicato e quindi collegato all'albero XML.</span><span class="sxs-lookup"><span data-stu-id="961f0-162">If the new content already is parented and is part of another XML tree, the new content is cloned, and the newly cloned content is attached to the XML tree.</span></span>  

<span data-ttu-id="961f0-163">Nell'esempio seguente viene illustrato il diverso comportamento relativo all'aggiunta di un elemento con o senza elemento padre a una struttura ad albero.</span><span class="sxs-lookup"><span data-stu-id="961f0-163">The following example demonstrates the behavior when you add a parented element to a tree, and when you add an element with no parent to a tree.</span></span>

```csharp  
// Create a tree with a child element.  
XElement xmlTree1 = new XElement("Root",  
    new XElement("Child1", 1)  
);  
  
// Create an element that is not parented.  
XElement child2 = new XElement("Child2", 2);  
  
// Create a tree and add Child1 and Child2 to it.  
XElement xmlTree2 = new XElement("Root",  
    xmlTree1.Element("Child1"),  
    child2  
);  
  
// Compare Child1 identity.  
Console.WriteLine("Child1 was {0}",  
    xmlTree1.Element("Child1") == xmlTree2.Element("Child1") ?  
    "attached" : "cloned");  
  
// Compare Child2 identity.  
Console.WriteLine("Child2 was {0}",  
    child2 == xmlTree2.Element("Child2") ?  
    "attached" : "cloned");  

// The example displays the following output:  
//    Child1 was cloned  
//    Child2 was attached  
```

## <a name="see-also"></a><span data-ttu-id="961f0-164">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="961f0-164">See also</span></span>

- [<span data-ttu-id="961f0-165">Creazione di alberi XML (C#)</span><span class="sxs-lookup"><span data-stu-id="961f0-165">Creating XML Trees (C#)</span></span>](./linq-to-xml-overview.md)
