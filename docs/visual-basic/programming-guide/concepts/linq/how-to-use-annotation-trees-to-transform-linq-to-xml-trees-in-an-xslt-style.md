---
title: 'Procedura: Usare le annotazioni per trasformare alberi LINQ to XML in uno stile XSLT (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 08e91fa2-dac2-4463-9ef1-87b1ac3fa890
ms.openlocfilehash: ed31e00b6d67a6707a98977c58e4e7afe35c8ad7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54746299"
---
# <a name="how-to-use-annotations-to-transform-linq-to-xml-trees-in-an-xslt-style-visual-basic"></a><span data-ttu-id="8c58b-102">Procedura: Usare le annotazioni per trasformare alberi LINQ to XML in uno stile XSLT (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8c58b-102">How to: Use Annotations to Transform LINQ to XML Trees in an XSLT Style (Visual Basic)</span></span>
<span data-ttu-id="8c58b-103">Le annotazioni possono essere usate per facilitare le trasformazioni di un albero XML.</span><span class="sxs-lookup"><span data-stu-id="8c58b-103">Annotations can be used to facilitate transforms of an XML tree.</span></span>  
  
 <span data-ttu-id="8c58b-104">Alcuni documenti XML sono "basati su documenti con contenuto misto".</span><span class="sxs-lookup"><span data-stu-id="8c58b-104">Some XML documents are "document centric with mixed content."</span></span> <span data-ttu-id="8c58b-105">Con tali documenti, la forma dei nodi figlio di un elemento non è necessariamente nota.</span><span class="sxs-lookup"><span data-stu-id="8c58b-105">With such documents, you don't necessarily know the shape of child nodes of an element.</span></span> <span data-ttu-id="8c58b-106">Ad esempio, un nodo che contiene testo può essere analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="8c58b-106">For instance, a node that contains text may look like this:</span></span>  
  
```xml  
<text>A phrase with <b>bold</b> and <i>italic</i> text.</text>  
```  
  
 <span data-ttu-id="8c58b-107">Per ogni nodo di testo potrebbe essere disponibile un numero qualsiasi di elementi `<b>` e `<i>` figlio.</span><span class="sxs-lookup"><span data-stu-id="8c58b-107">For any given text node, there may be any number of child `<b>` and `<i>` elements.</span></span> <span data-ttu-id="8c58b-108">Questo approccio è applicabile a diverse altre situazioni: ad esempio, le pagine che possono contenere una varietà di elementi figlio, ad esempio paragrafi normali, paragrafi puntati e bitmap.</span><span class="sxs-lookup"><span data-stu-id="8c58b-108">This approach extends to a number of other situations: such as, pages that can contain a variety of child elements, such as regular paragraphs, bulleted paragraphs, and bitmaps.</span></span> <span data-ttu-id="8c58b-109">Le celle di una tabella possono contenere testo, elenchi a discesa o bitmap.</span><span class="sxs-lookup"><span data-stu-id="8c58b-109">Cells in a table may contain text, drop down lists, or bitmaps.</span></span> <span data-ttu-id="8c58b-110">Una delle caratteristiche principali dell'XML basato su documento è che non è noto quale sarà l'elemento figlio di un determinato elemento.</span><span class="sxs-lookup"><span data-stu-id="8c58b-110">One of the primary characteristics of document centric XML is that you do not know which child element any particular element will have.</span></span>  
  
 <span data-ttu-id="8c58b-111">Se si desidera trasformare gli elementi di un albero e non si dispone necessariamente di molte informazioni sugli elementi figlio di tali elementi, questo approccio basato sull'utilizzo di annotazioni si rivela efficace.</span><span class="sxs-lookup"><span data-stu-id="8c58b-111">If you want to transform elements in a tree where you don't necessarily know much about the children of the elements that you want to transform, then this approach that uses annotations is an effective approach.</span></span>  
  
 <span data-ttu-id="8c58b-112">Il riepilogo dell'approccio è il seguente:</span><span class="sxs-lookup"><span data-stu-id="8c58b-112">The summary of the approach is:</span></span>  
  
-   <span data-ttu-id="8c58b-113">Annotare gli elementi dell'albero con un elemento sostitutivo.</span><span class="sxs-lookup"><span data-stu-id="8c58b-113">First, annotate elements in the tree with a replacement element.</span></span>  
  
-   <span data-ttu-id="8c58b-114">Scorrere l'intero albero, creando un nuovo albero in cui ogni elemento viene sostituito con la relativa annotazione.</span><span class="sxs-lookup"><span data-stu-id="8c58b-114">Second, iterate through the entire tree, creating a new tree where you replace each element with its annotation.</span></span> <span data-ttu-id="8c58b-115">In questo esempio vengono implementate l'iterazione e la creazione del nuovo albero in una funzione denominato `XForm`.</span><span class="sxs-lookup"><span data-stu-id="8c58b-115">This example implements the iteration and creation of the new tree in a function named `XForm`.</span></span>  
  
 <span data-ttu-id="8c58b-116">In dettaglio, l'approccio è costituito dai seguenti passaggi:</span><span class="sxs-lookup"><span data-stu-id="8c58b-116">In detail, the approach consists of:</span></span>  
  
-   <span data-ttu-id="8c58b-117">Eseguire una o più query LINQ to XML che restituiscono il set di elementi da trasformare da una forma a un'altra.</span><span class="sxs-lookup"><span data-stu-id="8c58b-117">Execute one or more LINQ to XML queries that return the set of elements that you want to transform from one shape to another.</span></span> <span data-ttu-id="8c58b-118">Per ogni elemento della query, aggiungere un nuovo oggetto <xref:System.Xml.Linq.XElement> come annotazione all'elemento.</span><span class="sxs-lookup"><span data-stu-id="8c58b-118">For each element in the query, add a new <xref:System.Xml.Linq.XElement> object as an annotation to the element.</span></span> <span data-ttu-id="8c58b-119">Questo nuovo elemento sostituirà l'elemento annotato nel nuovo albero trasformato.</span><span class="sxs-lookup"><span data-stu-id="8c58b-119">This new element will replace the annotated element in the new, transformed tree.</span></span> <span data-ttu-id="8c58b-120">Il codice da scrivere è semplice, come illustrato nell'esempio.</span><span class="sxs-lookup"><span data-stu-id="8c58b-120">This is simple code to write, as demonstrated by the example.</span></span>  
  
-   <span data-ttu-id="8c58b-121">Il nuovo elemento aggiunto come annotazione può contenere nuovi nodi figlio e può formare un sottoalbero con la forma desiderata.</span><span class="sxs-lookup"><span data-stu-id="8c58b-121">The new element that is added as an annotation can contain new child nodes; it can form a sub-tree with any desired shape.</span></span>  
  
-   <span data-ttu-id="8c58b-122">È disponibile una regola speciale: Se un nodo figlio del nuovo elemento è in uno spazio dei nomi diversi, uno spazio dei nomi è composto per questo scopo (in questo esempio, lo spazio dei nomi è `http://www.microsoft.com/LinqToXmlTransform/2007`), tale elemento figlio non viene copiato nel nuovo albero.</span><span class="sxs-lookup"><span data-stu-id="8c58b-122">There is a special rule: If a child node of the new element is in a different namespace, a namespace that is made up for this purpose (in this example, the namespace is `http://www.microsoft.com/LinqToXmlTransform/2007`), then that child element is not copied to the new tree.</span></span> <span data-ttu-id="8c58b-123">Se invece lo spazio dei nomi è quello speciale citato in precedenza e il nome locale dell'elemento è `ApplyTransforms`, i nodi figlio dell'elemento nell'albero di origine vengono scorsi e quindi copiati nel nuovo albero, con l'eccezione che gli elementi figlio annotati vengono trasformati anch'essi in base a queste regole.</span><span class="sxs-lookup"><span data-stu-id="8c58b-123">Instead, if the namespace is the above mentioned special namespace, and the local name of the element is `ApplyTransforms`, then the child nodes of the element in the source tree are iterated, and copied to the new tree (with the exception that annotated child elements are themselves transformed according to these rules).</span></span>  
  
-   <span data-ttu-id="8c58b-124">Questo comportamento è in una certa misura analogo alla specifica di trasformazioni in XSL.</span><span class="sxs-lookup"><span data-stu-id="8c58b-124">This is somewhat analogous to the specification of transforms in XSL.</span></span> <span data-ttu-id="8c58b-125">La query che seleziona un set di nodi è analoga all'espressione XPath per un modello.</span><span class="sxs-lookup"><span data-stu-id="8c58b-125">The query that selects a set of nodes is analogous to the XPath expression for a template.</span></span> <span data-ttu-id="8c58b-126">Il codice per creare il nuovo elemento <xref:System.Xml.Linq.XElement> salvato come annotazione è analogo al costruttore di sequenze in XSL e l'elemento `ApplyTransforms` ha una funzione analoga all'elemento `xsl:apply-templates` in XSL.</span><span class="sxs-lookup"><span data-stu-id="8c58b-126">The code to create the new <xref:System.Xml.Linq.XElement> that is saved as an annotation is analogous to the sequence constructor in XSL, and the `ApplyTransforms` element is analogous in function to the `xsl:apply-templates` element in XSL.</span></span>  
  
-   <span data-ttu-id="8c58b-127">Uno dei vantaggi di questo approccio è che le query formulate vengono sempre scritte sull'albero di origine non modificata.</span><span class="sxs-lookup"><span data-stu-id="8c58b-127">One advantage to taking this approach - as you formulate queries, you are always writing queries on the unmodified source tree.</span></span> <span data-ttu-id="8c58b-128">Non è necessario preoccuparsi degli effetti delle modifiche apportate all'albero sulle query che vengono scritte.</span><span class="sxs-lookup"><span data-stu-id="8c58b-128">You need not worry about how modifications to the tree affect the queries that you are writing.</span></span>  
  
## <a name="transforming-a-tree"></a><span data-ttu-id="8c58b-129">Trasformazione di un albero</span><span class="sxs-lookup"><span data-stu-id="8c58b-129">Transforming a Tree</span></span>  
 <span data-ttu-id="8c58b-130">Nel primo esempio tutti i nodi `Paragraph` vengono rinominati in `para`.</span><span class="sxs-lookup"><span data-stu-id="8c58b-130">This first example renames all `Paragraph` nodes to `para`.</span></span>  
  
```vb  
Imports <xmlns:xf="http://www.microsoft.com/LinqToXmlTransform/2007">  
  
Module Module1  
    Dim at As XName = GetXmlNamespace(xf) + "ApplyTransforms"  
  
    Sub Main()  
        Dim root As XElement = _  
            <Root>  
                <Paragraph>This is a sentence with <b>bold</b> and <i>italic</i> text.</Paragraph>  
                <Paragraph>More text.</Paragraph>  
            </Root>  
  
        ' Replace Paragraph with p.  
        For Each el In root...<Paragraph>  
            ' same idea as xsl:apply-templates  
            el.AddAnnotation( _  
                <para>  
                    <<%= at %>></>  
                </para>)  
        Next  
  
        ' The XForm function, shown later in this topic, accomplishes the transform  
        Dim newRoot As XElement = XForm(root)  
        Console.WriteLine(newRoot)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="8c58b-131">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="8c58b-131">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <para>This is a sentence with <b>bold</b> and <i>italic</i> text.</para>  
  <para>More text.</para>  
</Root>  
```  
  
## <a name="a-more-complicated-transform"></a><span data-ttu-id="8c58b-132">Trasformazioni più complicata</span><span class="sxs-lookup"><span data-stu-id="8c58b-132">A More Complicated Transform</span></span>  
 <span data-ttu-id="8c58b-133">Nell'esempio seguente viene eseguita una query sull'albero e vengono calcolate la media e la somma degli elementi `Data`, che vengono aggiunte come nuovi elementi nell'albero.</span><span class="sxs-lookup"><span data-stu-id="8c58b-133">The following example queries the tree and calculates the average and sum of the `Data` elements, and adds them as new elements to the tree.</span></span>  
  
```vb  
Imports <xmlns:xf="http://www.microsoft.com/LinqToXmlTransform/2007">  
  
Module Module1  
    Dim at As XName = GetXmlNamespace(xf) + "ApplyTransforms"  
  
    Sub Main()  
        Dim data As XElement = _  
            <Root>  
                <Data>20</Data>  
                <Data>10</Data>  
                <Data>3</Data>  
            </Root>  
  
        ' While adding annotations, you can query the source tree all you want,  
        ' as the tree is not mutated while annotating.  
        data.AddAnnotation( _  
            <Root>  
                <<%= at %>/>  
                <Average>  
                    <%= _  
                        String.Format("{0:F4}", _  
                        data.Elements("Data") _  
                        .Select(Function(z) CDec(z)).Average()) _  
                    %>  
                </Average>  
                <Sum>  
                    <%= _  
                        data.Elements("Data").Select(Function(z) CInt(z)).Sum() _  
                    %>  
                </Sum>  
            </Root> _  
        )  
  
        Console.WriteLine("Before Transform")  
        Console.WriteLine("----------------")  
        Console.WriteLine(data)  
        Console.WriteLine(vbNewLine)  
  
        ' The XForm function, shown later in this topic, accomplishes the transform  
        Dim newData As XElement = XForm(data)  
  
        Console.WriteLine("After Transform")  
        Console.WriteLine("----------------")  
        Console.WriteLine(newData)  
    End Sub  
End Module   
```  
  
 <span data-ttu-id="8c58b-134">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="8c58b-134">This example produces the following output:</span></span>  
  
```  
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
  
## <a name="effecting-the-transform"></a><span data-ttu-id="8c58b-135">Esecuzione della trasformazione</span><span class="sxs-lookup"><span data-stu-id="8c58b-135">Effecting the Transform</span></span>  
 <span data-ttu-id="8c58b-136">Una piccola funzione, `XForm`, crea un nuovo albero trasformato dall'albero originale annotato.</span><span class="sxs-lookup"><span data-stu-id="8c58b-136">A small function, `XForm`, creates a new transformed tree from the original, annotated tree.</span></span>  
  
-   <span data-ttu-id="8c58b-137">Lo pseudo-codice per la funzione è piuttosto semplice:</span><span class="sxs-lookup"><span data-stu-id="8c58b-137">The pseudo code for the function is quite simple:</span></span>  
  
```  
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
  
 <span data-ttu-id="8c58b-138">Di seguito è riportata l'implementazione di questa funzione:</span><span class="sxs-lookup"><span data-stu-id="8c58b-138">Following is the implementation of this function:</span></span>  
  
```vb  
' Build a transformed XML tree per the annotations.  
Function XForm(ByVal source As XElement) As XElement  
    If source.Annotation(Of XElement)() IsNot Nothing Then  
        Dim anno As XElement = source.Annotation(Of XElement)()  
        Return _  
            <<%= anno.Name.ToString() %>>  
                <%= anno.Attributes() %>  
                <%= anno.Nodes().Select(Function(n As XNode) _  
                    GetSubNodes(n, source)) %>  
            </>  
    Else  
        Return _  
            <<%= source.Name %>>  
                <%= source.Attributes() %>  
                <%= source.Nodes().Select(Function(n) GetExpandedNodes(n)) %>  
            </>  
    End If  
End Function  
  
Private Function GetSubNodes(ByVal n As XNode, ByVal s As XElement) As Object  
    Dim annoEl As XElement = TryCast(n, XElement)  
    If annoEl IsNot Nothing Then  
        If annoEl.Name = at Then  
            Return s.Nodes().Select(Function(n2 As XNode) GetExpandedNodes(n2))  
        End If  
    End If  
    Return n  
End Function  
  
Private Function GetExpandedNodes(ByVal n2 As XNode) As XNode  
    Dim e2 As XElement = TryCast(n2, XElement)  
    If e2 Is Nothing Then  
        Return n2  
    Else  
        Return XForm(e2)  
    End If  
End Function  
```  
  
## <a name="complete-example"></a><span data-ttu-id="8c58b-139">Esempio completo</span><span class="sxs-lookup"><span data-stu-id="8c58b-139">Complete Example</span></span>  
 <span data-ttu-id="8c58b-140">Il codice seguente è un esempio completo che include la funzione `XForm`</span><span class="sxs-lookup"><span data-stu-id="8c58b-140">The following code is a complete example that includes the `XForm` function.</span></span> <span data-ttu-id="8c58b-141">e alcuni dei tipici utilizzi di questo tipo di trasformazione:</span><span class="sxs-lookup"><span data-stu-id="8c58b-141">It includes a few of the typical uses of this type of transform:</span></span>  
  
```vb  
Imports System  
Imports System.Collections.Generic  
Imports System.Linq  
Imports System.Text  
Imports System.Xml  
Imports System.Xml.Linq  
  
Imports <xmlns:xf="http://www.microsoft.com/LinqToXmlTransform/2007">  
  
Module Module1  
    Dim at As XName = GetXmlNamespace(xf) + "ApplyTransforms"  
  
    ' Build a transformed XML tree per the annotations.  
    Function XForm(ByVal source As XElement) As XElement  
        If source.Annotation(Of XElement)() IsNot Nothing Then  
            Dim anno As XElement = source.Annotation(Of XElement)()  
            Return _  
                <<%= anno.Name.ToString() %>>  
                    <%= anno.Attributes() %>  
                    <%= anno.Nodes().Select(Function(n As XNode) _  
                        GetSubNodes(n, source)) %>  
                </>  
        Else  
            Return _  
                <<%= source.Name %>>  
                    <%= source.Attributes() %>  
                    <%= source.Nodes().Select(Function(n) GetExpandedNodes(n)) %>  
                </>  
        End If  
    End Function  
  
    Private Function GetSubNodes(ByVal n As XNode, ByVal s As XElement) As Object  
        Dim annoEl As XElement = TryCast(n, XElement)  
        If annoEl IsNot Nothing Then  
            If annoEl.Name = at Then  
                Return s.Nodes().Select(Function(n2 As XNode) GetExpandedNodes(n2))  
            End If  
        End If  
        Return n  
    End Function  
  
    Private Function GetExpandedNodes(ByVal n2 As XNode) As XNode  
        Dim e2 As XElement = TryCast(n2, XElement)  
        If e2 Is Nothing Then  
            Return n2  
        Else  
            Return XForm(e2)  
        End If  
    End Function  
  
    Sub Main()  
        Dim root As XElement = _  
<Root Att1='123'>  
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
  
        ' Each of the following serves the same semantic purpose as  
        ' XSLT templates and sequence constructors.  
  
        ' Replace Child with NewChild.  
        For Each el In root.<Child>  
            el.AddAnnotation(<NewChild><%= CStr(el) %></NewChild>)  
        Next  
  
        ' Replace first GC with GrandChild, add an attribute.  
        For Each el In root...<GC>.Take(1)  
            el.AddAnnotation(<GrandChild ANewAttribute='999'><%= CStr(el) %></GrandChild>)  
        Next  
  
        ' Replace Other with NewOther, add new child elements around original content.  
        For Each el In root.<Other>  
            el.AddAnnotation( _  
                <NewOther>  
                    <MyNewChild>1</MyNewChild>  
                    <<%= at %>></>  
                    <ChildThatComesAfter/>  
                </NewOther>)  
        Next  
  
        ' Change name of element that has mixed content.  
        root...<SomeMixedContent>(0).AddAnnotation( _  
                <MixedContent><<%= at %>></></MixedContent>)  
  
        ' Replace <b> with <Bold>.  
        For Each el In root...<b>  
            el.AddAnnotation(<Bold><<%= at %>></></Bold>)  
        Next  
  
        ' Replace <i> with <Italic>.  
        For Each el In root...<i>  
            el.AddAnnotation(<Italic><<%= at %>></></Italic>)  
        Next  
  
        Console.WriteLine("Before Transform")  
        Console.WriteLine("----------------")  
        Console.WriteLine(root)  
        Console.WriteLine(vbNewLine)  
        Dim newRoot As XElement = XForm(root)  
  
        Console.WriteLine("After Transform")  
        Console.WriteLine("----------------")  
        Console.WriteLine(newRoot)  
    End Sub  
End Module   
```  
  
 <span data-ttu-id="8c58b-142">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="8c58b-142">This example produces the following output:</span></span>  
  
```  
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
  
## <a name="see-also"></a><span data-ttu-id="8c58b-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c58b-143">See also</span></span>
- [<span data-ttu-id="8c58b-144">LINQ to XML (Visual Basic) di programmazione avanzata</span><span class="sxs-lookup"><span data-stu-id="8c58b-144">Advanced LINQ to XML Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
