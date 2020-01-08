---
title: Come usare le annotazioni per trasformare alberi LINQ to XML in uno stile XSLTC#()
ms.date: 07/20/2015
ms.assetid: 12a95902-a6b7-4a1e-ad52-04a518db226f
ms.openlocfilehash: 109e1a49530f34e7197f8c975de8c04245b11734
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347288"
---
# <a name="how-to-use-annotations-to-transform-linq-to-xml-trees-in-an-xslt-style-c"></a><span data-ttu-id="b0960-102">Come usare le annotazioni per trasformare alberi LINQ to XML in uno stile XSLTC#()</span><span class="sxs-lookup"><span data-stu-id="b0960-102">How to use annotations to transform LINQ to XML trees in an XSLT style (C#)</span></span>
<span data-ttu-id="b0960-103">Le annotazioni possono essere usate per facilitare le trasformazioni di un albero XML.</span><span class="sxs-lookup"><span data-stu-id="b0960-103">Annotations can be used to facilitate transforms of an XML tree.</span></span>  
  
 <span data-ttu-id="b0960-104">Alcuni documenti XML sono "basati su documenti con contenuto misto".</span><span class="sxs-lookup"><span data-stu-id="b0960-104">Some XML documents are "document centric with mixed content."</span></span> <span data-ttu-id="b0960-105">Con tali documenti, la forma dei nodi figlio di un elemento non è necessariamente nota.</span><span class="sxs-lookup"><span data-stu-id="b0960-105">With such documents, you don't necessarily know the shape of child nodes of an element.</span></span> <span data-ttu-id="b0960-106">Ad esempio, un nodo che contiene testo può essere analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="b0960-106">For instance, a node that contains text may look like this:</span></span>  
  
```xml  
<text>A phrase with <b>bold</b> and <i>italic</i> text.</text>  
```  
  
 <span data-ttu-id="b0960-107">Per ogni nodo di testo potrebbe essere disponibile un numero qualsiasi di elementi `<b>` e `<i>` figlio.</span><span class="sxs-lookup"><span data-stu-id="b0960-107">For any given text node, there may be any number of child `<b>` and `<i>` elements.</span></span> <span data-ttu-id="b0960-108">Questo approccio è applicabile a diverse altre situazioni, ad esempio pagine che possono contenere un'ampia varietà di elementi figlio, come paragrafi normali, paragrafi sotto forma di elenchi puntati e bitmap.</span><span class="sxs-lookup"><span data-stu-id="b0960-108">This approach extends to a number of other situations, such as pages that can contain a variety of child elements, such as regular paragraphs, bulleted paragraphs, and bitmaps.</span></span> <span data-ttu-id="b0960-109">Le celle di una tabella possono contenere testo, elenchi a discesa o bitmap.</span><span class="sxs-lookup"><span data-stu-id="b0960-109">Cells in a table may contain text, drop down lists, or bitmaps.</span></span> <span data-ttu-id="b0960-110">Una delle caratteristiche principali dell'XML basato su documento è che non è noto quale sarà l'elemento figlio di un determinato elemento.</span><span class="sxs-lookup"><span data-stu-id="b0960-110">One of the primary characteristics of document centric XML is that you do not know which child element any particular element will have.</span></span>  
  
 <span data-ttu-id="b0960-111">Se si desidera trasformare gli elementi di un albero e non si dispone necessariamente di molte informazioni sugli elementi figlio di tali elementi, questo approccio basato sull'utilizzo di annotazioni si rivela efficace.</span><span class="sxs-lookup"><span data-stu-id="b0960-111">If you want to transform elements in a tree where you don't necessarily know much about the children of the elements that you want to transform, then this approach that uses annotations is an effective approach.</span></span>  
  
 <span data-ttu-id="b0960-112">Il riepilogo dell'approccio è il seguente:</span><span class="sxs-lookup"><span data-stu-id="b0960-112">The summary of the approach is:</span></span>  
  
- <span data-ttu-id="b0960-113">Annotare gli elementi dell'albero con un elemento sostitutivo.</span><span class="sxs-lookup"><span data-stu-id="b0960-113">First, annotate elements in the tree with a replacement element.</span></span>  
  
- <span data-ttu-id="b0960-114">Scorrere l'intero albero, creando un nuovo albero in cui ogni elemento viene sostituito con la relativa annotazione.</span><span class="sxs-lookup"><span data-stu-id="b0960-114">Second, iterate through the entire tree, creating a new tree where you replace each element with its annotation.</span></span> <span data-ttu-id="b0960-115">In questo esempio vengono implementate l'iterazione e la creazione del nuovo albero in una funzione denominato `XForm`.</span><span class="sxs-lookup"><span data-stu-id="b0960-115">This example implements the iteration and creation of the new tree in a function named `XForm`.</span></span>  
  
 <span data-ttu-id="b0960-116">In dettaglio, l'approccio è costituito dai seguenti passaggi:</span><span class="sxs-lookup"><span data-stu-id="b0960-116">In detail, the approach consists of:</span></span>  
  
- <span data-ttu-id="b0960-117">Eseguire una o più query LINQ to XML che restituiscono il set di elementi da trasformare da una forma a un'altra.</span><span class="sxs-lookup"><span data-stu-id="b0960-117">Execute one or more LINQ to XML queries that return the set of elements that you want to transform from one shape to another.</span></span> <span data-ttu-id="b0960-118">Per ogni elemento della query, aggiungere un nuovo oggetto <xref:System.Xml.Linq.XElement> come annotazione all'elemento.</span><span class="sxs-lookup"><span data-stu-id="b0960-118">For each element in the query, add a new <xref:System.Xml.Linq.XElement> object as an annotation to the element.</span></span> <span data-ttu-id="b0960-119">Questo nuovo elemento sostituirà l'elemento annotato nel nuovo albero trasformato.</span><span class="sxs-lookup"><span data-stu-id="b0960-119">This new element will replace the annotated element in the new, transformed tree.</span></span> <span data-ttu-id="b0960-120">Il codice da scrivere è semplice, come illustrato nell'esempio.</span><span class="sxs-lookup"><span data-stu-id="b0960-120">This is simple code to write, as demonstrated by the example.</span></span>  
  
- <span data-ttu-id="b0960-121">Il nuovo elemento aggiunto come annotazione può contenere nuovi nodi figlio e può formare un sottoalbero con la forma desiderata.</span><span class="sxs-lookup"><span data-stu-id="b0960-121">The new element that is added as an annotation can contain new child nodes; it can form a sub-tree with any desired shape.</span></span>  
  
- <span data-ttu-id="b0960-122">È necessario seguire una regola speciale: se un nodo figlio del nuovo elemento è incluso in uno spazio dei nomi diverso, ovvero uno spazio dei nomi creato appositamente (in questo esempio lo spazio dei nomi è `http://www.microsoft.com/LinqToXmlTransform/2007`), tale elemento figlio non viene copiato nel nuovo albero.</span><span class="sxs-lookup"><span data-stu-id="b0960-122">There is a special rule: If a child node of the new element is in a different namespace, a namespace that is made up for this purpose (in this example, the namespace is `http://www.microsoft.com/LinqToXmlTransform/2007`), then that child element is not copied to the new tree.</span></span> <span data-ttu-id="b0960-123">Se invece lo spazio dei nomi è quello speciale citato in precedenza e il nome locale dell'elemento è `ApplyTransforms`, i nodi figlio dell'elemento nell'albero di origine vengono scorsi e quindi copiati nel nuovo albero, con l'eccezione che gli elementi figlio annotati vengono trasformati anch'essi in base a queste regole.</span><span class="sxs-lookup"><span data-stu-id="b0960-123">Instead, if the namespace is the above mentioned special namespace, and the local name of the element is `ApplyTransforms`, then the child nodes of the element in the source tree are iterated, and copied to the new tree (with the exception that annotated child elements are themselves transformed according to these rules).</span></span>  
  
- <span data-ttu-id="b0960-124">Questo comportamento è in una certa misura analogo alla specifica di trasformazioni in XSL.</span><span class="sxs-lookup"><span data-stu-id="b0960-124">This is somewhat analogous to the specification of transforms in XSL.</span></span> <span data-ttu-id="b0960-125">La query che seleziona un set di nodi è analoga all'espressione XPath per un modello.</span><span class="sxs-lookup"><span data-stu-id="b0960-125">The query that selects a set of nodes is analogous to the XPath expression for a template.</span></span> <span data-ttu-id="b0960-126">Il codice per creare il nuovo elemento <xref:System.Xml.Linq.XElement> salvato come annotazione è analogo al costruttore di sequenze in XSL e l'elemento `ApplyTransforms` ha una funzione analoga all'elemento `xsl:apply-templates` in XSL.</span><span class="sxs-lookup"><span data-stu-id="b0960-126">The code to create the new <xref:System.Xml.Linq.XElement> that is saved as an annotation is analogous to the sequence constructor in XSL, and the `ApplyTransforms` element is analogous in function to the `xsl:apply-templates` element in XSL.</span></span>  
  
- <span data-ttu-id="b0960-127">Uno dei vantaggi di questo approccio è che le query formulate vengono sempre scritte sull'albero di origine non modificata.</span><span class="sxs-lookup"><span data-stu-id="b0960-127">One advantage to taking this approach - as you formulate queries, you are always writing queries on the unmodified source tree.</span></span> <span data-ttu-id="b0960-128">Non è necessario preoccuparsi degli effetti delle modifiche apportate all'albero sulle query che vengono scritte.</span><span class="sxs-lookup"><span data-stu-id="b0960-128">You need not worry about how modifications to the tree affect the queries that you are writing.</span></span>  
  
## <a name="transforming-a-tree"></a><span data-ttu-id="b0960-129">Trasformazione di un albero</span><span class="sxs-lookup"><span data-stu-id="b0960-129">Transforming a Tree</span></span>  
 <span data-ttu-id="b0960-130">Nel primo esempio tutti i nodi `Paragraph` vengono rinominati in `para`.</span><span class="sxs-lookup"><span data-stu-id="b0960-130">This first example renames all `Paragraph` nodes to `para`.</span></span>  
  
```csharp  
XNamespace xf = "http://www.microsoft.com/LinqToXmlTransform/2007";  
XName at = xf + "ApplyTransforms";  
  
XElement root = XElement.Parse(@"  
<Root>  
    <Paragraph>This is a sentence with <b>bold</b> and <i>italic</i> text.</Paragraph>  
    <Paragraph>More text.</Paragraph>  
</Root>");  
  
// replace Paragraph with para  
foreach (var el in root.Descendants("Paragraph"))  
    el.AddAnnotation(  
        new XElement("para",  
            // same idea as xsl:apply-templates  
            new XElement(xf + "ApplyTransforms")  
        )  
    );  
  
// The XForm method, shown later in this topic, accomplishes the transform  
XElement newRoot = XForm(root);  
  
Console.WriteLine(newRoot);  
```  
  
 <span data-ttu-id="b0960-131">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="b0960-131">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <para>This is a sentence with <b>bold</b> and <i>italic</i> text.</para>  
  <para>More text.</para>  
</Root>  
```  
  
## <a name="a-more-complicated-transform"></a><span data-ttu-id="b0960-132">Trasformazioni più complicata</span><span class="sxs-lookup"><span data-stu-id="b0960-132">A More Complicated Transform</span></span>  
 <span data-ttu-id="b0960-133">Nell'esempio seguente viene eseguita una query sull'albero e vengono calcolate la media e la somma degli elementi `Data`, che vengono aggiunte come nuovi elementi nell'albero.</span><span class="sxs-lookup"><span data-stu-id="b0960-133">The following example queries the tree and calculates the average and sum of the `Data` elements, and adds them as new elements to the tree.</span></span>  
  
```csharp  
XNamespace xf = "http://www.microsoft.com/LinqToXmlTransform/2007";  
XName at = xf + "ApplyTransforms";  
  
XElement data = new XElement("Root",  
    new XElement("Data", 20),  
    new XElement("Data", 10),  
    new XElement("Data", 3)  
);  
  
// while adding annotations, you can query the source tree all you want,  
// as the tree is not mutated while annotating.
var avg = data.Elements("Data").Select(z => (Decimal)z).Average();
data.AddAnnotation(  
    new XElement("Root",  
        new XElement(xf + "ApplyTransforms"),  
        new XElement("Average", $"{avg:F4}"),
        new XElement("Sum",  
            data  
            .Elements("Data")  
            .Select(z => (int)z)  
            .Sum()  
        )  
    )  
);  
  
Console.WriteLine("Before Transform");  
Console.WriteLine("----------------");  
Console.WriteLine(data);  
Console.WriteLine();  
Console.WriteLine();  
  
// The XForm method, shown later in this topic, accomplishes the transform  
XElement newData = XForm(data);  
  
Console.WriteLine("After Transform");  
Console.WriteLine("----------------");  
Console.WriteLine(newData);  
```  
  
 <span data-ttu-id="b0960-134">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="b0960-134">This example produces the following output:</span></span>  
  
```output  
Before Transform  
----------------  
<Root>  
  <Data>20</Data>  
  <Data>10</Data>  
  <Data>3</Data>  
</Root>  
  
After Transform  
----------------  
<Root>  
  <Data>20</Data>  
  <Data>10</Data>  
  <Data>3</Data>  
  <Average>11.0000</Average>  
  <Sum>33</Sum>  
</Root>  
```  
  
## <a name="effecting-the-transform"></a><span data-ttu-id="b0960-135">Esecuzione della trasformazione</span><span class="sxs-lookup"><span data-stu-id="b0960-135">Effecting the Transform</span></span>  
 <span data-ttu-id="b0960-136">Una piccola funzione, `XForm`, crea un nuovo albero trasformato dall'albero originale annotato.</span><span class="sxs-lookup"><span data-stu-id="b0960-136">A small function, `XForm`, creates a new transformed tree from the original, annotated tree.</span></span>  
  
- <span data-ttu-id="b0960-137">Lo pseudo-codice per la funzione è piuttosto semplice:</span><span class="sxs-lookup"><span data-stu-id="b0960-137">The pseudo code for the function is quite simple:</span></span>  
  
```text  
The function takes an XElement as an argument and returns an XElement.   
If an element has an XElement annotation, then  
    Return a new XElement  
        The name of the new XElement is the annotation element's name.  
        All attributes are copied from the annotation to the new node.  
        All child nodes are copied from the annotation, with the  
            exception that the special node xf:ApplyTransforms is  
            recognized, and the source element's child nodes are  
            iterated. If the source child node is not an XElement, it  
            is copied to the new tree. If the source child is an  
            XElement, then it is transformed by calling this function  
            recursively.  
If an element is not annotated  
    Return a new XElement  
        The name of the new XElement is the source element's name  
        All attributes are copied from the source element to the  
            destination's element.  
        All child nodes are copied from the source element.  
        If the source child node is not an XElement, it is copied to  
            the new tree. If the source child is an XElement, then it  
            is transformed by calling this function recursively.  
```  
  
 <span data-ttu-id="b0960-138">Di seguito è riportata l'implementazione di questa funzione:</span><span class="sxs-lookup"><span data-stu-id="b0960-138">Following is the implementation of this function:</span></span>  
  
```csharp  
// Build a transformed XML tree per the annotations  
static XElement XForm(XElement source)  
{  
    XNamespace xf = "http://www.microsoft.com/LinqToXmlTransform/2007";  
    XName at = xf + "ApplyTransforms";  
  
    if (source.Annotation<XElement>() != null)  
    {  
        XElement anno = source.Annotation<XElement>();  
        return new XElement(anno.Name,  
            anno.Attributes(),  
            anno  
            .Nodes()  
            .Select(  
                (XNode n) =>  
                {  
                    XElement annoEl = n as XElement;  
                    if (annoEl != null)  
                    {  
                        if (annoEl.Name == at)  
                            return (object)(  
                                source.Nodes()  
                                .Select(  
                                    (XNode n2) =>  
                                    {  
                                        XElement e2 = n2 as XElement;  
                                        if (e2 == null)  
                                            return n2;  
                                        else  
                                            return XForm(e2);  
                                    }  
                                )  
                            );  
                        else  
                            return n;  
                    }  
                    else  
                        return n;  
                }  
            )  
        );  
    }  
    else  
    {  
        return new XElement(source.Name,  
            source.Attributes(),  
            source  
                .Nodes()  
                .Select(n =>  
                {  
                    XElement el = n as XElement;  
                    if (el == null)  
                        return n;  
                    else  
                        return XForm(el);  
                }  
                )  
        );  
    }  
}   
```  
  
## <a name="complete-example"></a><span data-ttu-id="b0960-139">Esempio completo</span><span class="sxs-lookup"><span data-stu-id="b0960-139">Complete Example</span></span>  
 <span data-ttu-id="b0960-140">Il codice seguente è un esempio completo che include la funzione `XForm`</span><span class="sxs-lookup"><span data-stu-id="b0960-140">The following code is a complete example that includes the `XForm` function.</span></span> <span data-ttu-id="b0960-141">e alcuni dei tipici utilizzi di questo tipo di trasformazione:</span><span class="sxs-lookup"><span data-stu-id="b0960-141">It includes a few of the typical uses of this type of transform:</span></span>  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.Xml;  
using System.Xml.Linq;  
  
class Program  
{  
    static XNamespace xf = "http://www.microsoft.com/LinqToXmlTransform/2007";  
    static XName at = xf + "ApplyTransforms";  
  
    // Build a transformed XML tree per the annotations  
    static XElement XForm(XElement source)  
    {  
        if (source.Annotation<XElement>() != null)  
        {  
            XElement anno = source.Annotation<XElement>();  
            return new XElement(anno.Name,  
                anno.Attributes(),  
                anno  
                .Nodes()  
                .Select(  
                    (XNode n) =>  
                    {  
                        XElement annoEl = n as XElement;  
                        if (annoEl != null)  
                        {  
                            if (annoEl.Name == at)  
                                return (object)(  
                                    source.Nodes()  
                                    .Select(  
                                        (XNode n2) =>  
                                        {  
                                            XElement e2 = n2 as XElement;  
                                            if (e2 == null)  
                                                return n2;  
                                            else  
                                                return XForm(e2);  
                                        }  
                                    )  
                                );  
                            else  
                                return n;  
                        }  
                        else  
                            return n;  
                    }  
                )  
            );  
        }  
        else  
        {  
            return new XElement(source.Name,  
                source.Attributes(),  
                source  
                    .Nodes()  
                    .Select(n =>  
                    {  
                        XElement el = n as XElement;  
                        if (el == null)  
                            return n;  
                        else  
                            return XForm(el);  
                    }  
                    )  
            );  
        }  
    }  
  
    static void Main(string[] args)  
    {  
        XElement root = new XElement("Root",  
            new XComment("A comment"),  
            new XAttribute("Att1", 123),  
            new XElement("Child", 1),  
            new XElement("Child", 2),  
            new XElement("Other",  
                new XElement("GC", 3),  
                new XElement("GC", 4)  
            ),  
            XElement.Parse(  
              "<SomeMixedContent>This is <i>an</i> element that " +  
              "<b>has</b> some mixed content</SomeMixedContent>"),  
            new XElement("AnUnchangedElement", 42)  
        );  
  
        // each of the following serves the same semantic purpose as  
        // XSLT templates and sequence constructors  
  
        // replace Child with NewChild  
        foreach (var el in root.Elements("Child"))  
            el.AddAnnotation(new XElement("NewChild", (string)el));  
  
        // replace first GC with GrandChild, add an attribute  
        foreach (var el in root.Descendants("GC").Take(1))  
            el.AddAnnotation(  
                new XElement("GrandChild",  
                    new XAttribute("ANewAttribute", 999),  
                    (string)el  
                )  
            );  
  
        // replace Other with NewOther, add new child elements around original content  
        foreach (var el in root.Elements("Other"))  
            el.AddAnnotation(  
                new XElement("NewOther",  
                    new XElement("MyNewChild", 1),  
                    // same idea as xsl:apply-templates  
                    new XElement(xf + "ApplyTransforms"),  
                    new XElement("ChildThatComesAfter")  
                )  
            );  
  
        // change name of element that has mixed content  
        root.Descendants("SomeMixedContent").First().AddAnnotation(  
            new XElement("MixedContent",  
                new XElement(xf + "ApplyTransforms")  
            )  
        );  
  
        // replace <b> with <Bold>  
        foreach (var el in root.Descendants("b"))  
            el.AddAnnotation(  
                new XElement("Bold",  
                    new XElement(xf + "ApplyTransforms")  
                )  
            );  
  
        // replace <i> with <Italic>  
        foreach (var el in root.Descendants("i"))  
            el.AddAnnotation(  
                new XElement("Italic",  
                    new XElement(xf + "ApplyTransforms")  
                )  
            );  
  
        Console.WriteLine("Before Transform");  
        Console.WriteLine("----------------");  
        Console.WriteLine(root);  
        Console.WriteLine();  
        Console.WriteLine();  
        XElement newRoot = XForm(root);  
  
        Console.WriteLine("After Transform");  
        Console.WriteLine("----------------");  
        Console.WriteLine(newRoot);  
    }  
}  
```  
  
 <span data-ttu-id="b0960-142">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="b0960-142">This example produces the following output:</span></span>  
  
```output  
Before Transform  
----------------  
<Root Att1="123">  
  <!--A comment-->  
  <Child>1</Child>  
  <Child>2</Child>  
  <Other>  
    <GC>3</GC>  
    <GC>4</GC>  
  </Other>  
  <SomeMixedContent>This is <i>an</i> element that <b>has</b> some mixed content</SomeMixedContent>  
  <AnUnchangedElement>42</AnUnchangedElement>  
</Root>  
  
After Transform  
----------------  
<Root Att1="123">  
  <!--A comment-->  
  <NewChild>1</NewChild>  
  <NewChild>2</NewChild>  
  <NewOther>  
    <MyNewChild>1</MyNewChild>  
    <GrandChild ANewAttribute="999">3</GrandChild>  
    <GC>4</GC>  
    <ChildThatComesAfter />  
  </NewOther>  
  <MixedContent>This is <Italic>an</Italic> element that <Bold>has</Bold> some mixed content</MixedContent>  
  <AnUnchangedElement>42</AnUnchangedElement>  
</Root>  
```  
  