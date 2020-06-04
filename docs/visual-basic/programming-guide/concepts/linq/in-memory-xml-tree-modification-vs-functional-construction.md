---
title: Differenze tra la modifica dell'albero XML in memoria e la Costruzione funzionale (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: d91c4ebf-6549-43cc-9961-26d4a82f722b
ms.openlocfilehash: efdbf51efa0f502ac9991d520defe45bb95678b7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397609"
---
# <a name="in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml-visual-basic"></a><span data-ttu-id="8f34b-102">Modifica dell'albero XML in memoria rispetto alla costruzione funzionale (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f34b-102">In-Memory XML Tree Modification vs. Functional Construction (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="8f34b-103">La modifica di un albero XML sul posto è un approccio tradizionale per cambiare la forma di un documento XML.</span><span class="sxs-lookup"><span data-stu-id="8f34b-103">Modifying an XML tree in place is a traditional approach to changing the shape of an XML document.</span></span> <span data-ttu-id="8f34b-104">In una tipica applicazione un documento viene caricato in un archivio dati quale DOM o [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], viene usata un'interfaccia di programmazione per inserire o eliminare nodi oppure per modificarne il contenuto, quindi il file XML viene salvato in un file o trasmesso tramite una rete.</span><span class="sxs-lookup"><span data-stu-id="8f34b-104">A typical application loads a document into a data store such as DOM or [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]; uses a programming interface to insert nodes, delete nodes, or change the content of nodes; and then saves the XML to a file or transmits it over a network.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="8f34b-105">consente un altro approccio utile in molti scenari *: costruzione funzionale*.</span><span class="sxs-lookup"><span data-stu-id="8f34b-105">enables another approach that is useful in many scenarios *: functional construction*.</span></span> <span data-ttu-id="8f34b-106">Nella costruzione funzionale la modifica di dati viene considerata come un problema di trasformazione, anziché come una modifica dettagliata di un archivio dati.</span><span class="sxs-lookup"><span data-stu-id="8f34b-106">Functional construction treats modifying data as a problem of transformation, rather than as detailed manipulation of a data store.</span></span> <span data-ttu-id="8f34b-107">Se è possibile trasformare in modo efficiente una rappresentazione di dati da un formato a un altro, il risultato è identico a quello ottenuto modificando un archivio dati in modo da cambiarne la forma.</span><span class="sxs-lookup"><span data-stu-id="8f34b-107">If you can take a representation of data and transform it efficiently from one form to another, the result is the same as if you took one data store and manipulated it in some way to take another shape.</span></span> <span data-ttu-id="8f34b-108">Un aspetto importante dell'approccio della costruzione funzionale riguarda il passaggio dei risultati delle query ai costruttori <xref:System.Xml.Linq.XDocument> e <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="8f34b-108">A key to the functional construction approach is to pass the results of queries to <xref:System.Xml.Linq.XDocument> and <xref:System.Xml.Linq.XElement> constructors.</span></span>  
  
 <span data-ttu-id="8f34b-109">In molti casi, è possibile scrivere il codice di trasformazione in tempi ridotti rispetto a quelli richiesti per la modifica dell'archivio dati. Il codice è inoltre più affidabile e facile da gestire.</span><span class="sxs-lookup"><span data-stu-id="8f34b-109">In many cases you can write the transformational code in a fraction of the time that it would take to manipulate the data store, and that code is more robust and easier to maintain.</span></span> <span data-ttu-id="8f34b-110">In questi casi, anche se l'approccio della trasformazione può richiedere una maggiore potenza di elaborazione, si tratta di una soluzione più efficace per la modifica dei dati.</span><span class="sxs-lookup"><span data-stu-id="8f34b-110">In these cases, even though the transformational approach can take more processing power, it is a more effective way to modify data.</span></span> <span data-ttu-id="8f34b-111">Se gli sviluppatori hanno familiarità con l'approccio funzionale, il codice risultante è spesso più facile da comprendere.</span><span class="sxs-lookup"><span data-stu-id="8f34b-111">If a developer is familiar with the functional approach, the resulting code in many cases is easier to understand.</span></span> <span data-ttu-id="8f34b-112">Risulta facile trovare il codice che modifica ogni parte dell'albero.</span><span class="sxs-lookup"><span data-stu-id="8f34b-112">It is easy to find the code that modifies each part of the tree.</span></span>  
  
 <span data-ttu-id="8f34b-113">Molti programmatori DOM hanno una maggiore dimestichezza con l'approccio in cui un albero XML viene modificato sul posto, mentre il codice scritto con l'approccio funzionale potrebbe sembrare insolito agli sviluppatori che non hanno ancora compreso tale approccio.</span><span class="sxs-lookup"><span data-stu-id="8f34b-113">The approach where you modify an XML tree in-place is more familiar to many DOM programmers, whereas code written using the functional approach might look unfamiliar to a developer who doesn't yet understand that approach.</span></span> <span data-ttu-id="8f34b-114">Se è necessario apportare solo una piccola modifica a un albero XML di grandi dimensioni, l'approccio in cui un albero viene modificato sul posto richiederà in molti casi meno tempo CPU.</span><span class="sxs-lookup"><span data-stu-id="8f34b-114">If you have to only make a small modification to a large XML tree, the approach where you modify a tree in place in many cases will take less CPU time.</span></span>  
  
 <span data-ttu-id="8f34b-115">In questo argomento viene illustrato un esempio implementato con entrambi gli approcci.</span><span class="sxs-lookup"><span data-stu-id="8f34b-115">This topic provides an example that is implemented with both approaches.</span></span>  
  
## <a name="transforming-attributes-into-elements"></a><span data-ttu-id="8f34b-116">Trasformazione di attributi in elementi</span><span class="sxs-lookup"><span data-stu-id="8f34b-116">Transforming Attributes into Elements</span></span>  
 <span data-ttu-id="8f34b-117">Per questo esempio, si supponga di voler modificare il semplice documento XML seguente in modo che gli attributi diventino elementi.</span><span class="sxs-lookup"><span data-stu-id="8f34b-117">For this example, suppose you want to modify the following simple XML document so that the attributes become elements.</span></span> <span data-ttu-id="8f34b-118">In questo argomento viene presentato dapprima l'approccio tradizionale della modifica sul posto</span><span class="sxs-lookup"><span data-stu-id="8f34b-118">This topic first presents the traditional in-place modification approach.</span></span> <span data-ttu-id="8f34b-119">e quindi l'approccio della costruzione funzionale.</span><span class="sxs-lookup"><span data-stu-id="8f34b-119">It then shows the functional construction approach.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<Root Data1="123" Data2="456">  
  <Child1>Content</Child1>  
</Root>  
```  
  
### <a name="modifying-the-xml-tree"></a><span data-ttu-id="8f34b-120">Modifica dell'albero XML</span><span class="sxs-lookup"><span data-stu-id="8f34b-120">Modifying the XML Tree</span></span>  
 <span data-ttu-id="8f34b-121">È possibile scrivere codice procedurale per creare elementi dagli attributi e quindi eliminare gli attributi, come segue:</span><span class="sxs-lookup"><span data-stu-id="8f34b-121">You can write some procedural code to create elements from the attributes, and then delete the attributes, as follows:</span></span>  
  
```vb  
Dim root As XElement = XElement.Load("Data.xml")  
For Each att As XAttribute In root.Attributes()  
    root.Add(New XElement(att.Name, att.Value))  
Next  
root.Attributes().Remove()  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="8f34b-122">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="8f34b-122">This code produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child1>Content</Child1>  
  <Data1>123</Data1>  
  <Data2>456</Data2>  
</Root>  
```  
  
### <a name="functional-construction-approach"></a><span data-ttu-id="8f34b-123">Approccio della costruzione funzionale</span><span class="sxs-lookup"><span data-stu-id="8f34b-123">Functional Construction Approach</span></span>  
 <span data-ttu-id="8f34b-124">Al contrario, un approccio funzionale è costituito da codice per creare un nuovo albero, selezionando gli elementi e gli attributi dall'albero di origine e trasformandoli nel modo appropriato prima di aggiungerli nel nuovo albero.</span><span class="sxs-lookup"><span data-stu-id="8f34b-124">By contrast, a functional approach consists of code to form a new tree, picking and choosing elements and attributes from the source tree, and transforming them as appropriate as they are added to the new tree.</span></span> <span data-ttu-id="8f34b-125">Di seguito è illustrato il risultato dell'approccio funzionale:</span><span class="sxs-lookup"><span data-stu-id="8f34b-125">The functional approach looks like the following:</span></span>  
  
```vb  
Dim root As XElement = XElement.Load("Data.xml")  
Dim newTree As XElement = _  
    <Root>  
        <%= root.<Child1> %>  
        <%= From att In root.Attributes() _  
            Select New XElement(att.Name, att.Value) %>  
    </Root>  
Console.WriteLine(newTree)  
```  
  
 <span data-ttu-id="8f34b-126">In questo esempio viene restituito stesso lo stesso output XML del primo esempio.</span><span class="sxs-lookup"><span data-stu-id="8f34b-126">This example outputs the same XML as the first example.</span></span> <span data-ttu-id="8f34b-127">Si noti, tuttavia, che è possibile visualizzare la struttura risultante del nuovo codice XML nell'approccio funzionale.</span><span class="sxs-lookup"><span data-stu-id="8f34b-127">However, notice that you can actually see the resulting structure of the new XML in the functional approach.</span></span> <span data-ttu-id="8f34b-128">È quindi possibile vedere la creazione dell'elemento `Root`, il codice che effettua il pull dell'elemento `Child1` dall'albero di origine e il codice che trasforma gli attributi dell'albero di origine in elementi nel nuovo albero.</span><span class="sxs-lookup"><span data-stu-id="8f34b-128">You can see the creation of the `Root` element, the code that pulls the `Child1` element from the source tree, and the code that transforms the attributes from the source tree to elements in the new tree.</span></span>  
  
 <span data-ttu-id="8f34b-129">L'esempio funzionale in questo caso non è più breve del primo e in realtà non è neanche più semplice.</span><span class="sxs-lookup"><span data-stu-id="8f34b-129">The functional example in this case is not any shorter than the first example, and it is not really any simpler.</span></span> <span data-ttu-id="8f34b-130">Se tuttavia è necessario apportare molte modifiche a un albero XML, l'approccio non funzionale diventerà alquanto complesso e poco flessibile.</span><span class="sxs-lookup"><span data-stu-id="8f34b-130">However, if you have many changes to make to an XML tree, the non functional approach will become quite complex and somewhat obtuse.</span></span> <span data-ttu-id="8f34b-131">Al contrario, quando si usa l'approccio funzionale, viene comunque creato l'XML desiderato, incorporando query ed espressioni nel modo appropriato, per inserire il contenuto desiderato.</span><span class="sxs-lookup"><span data-stu-id="8f34b-131">In contrast, when using the functional approach, you still just form the desired XML, embedding queries and expressions as appropriate, to pull in the desired content.</span></span> <span data-ttu-id="8f34b-132">L'approccio funzionale restituisce codice più facile gestire.</span><span class="sxs-lookup"><span data-stu-id="8f34b-132">The functional approach yields code that is easier to maintain.</span></span>  
  
 <span data-ttu-id="8f34b-133">Si noti che in questo caso le prestazioni dell'approccio funzionale potrebbero non essere uguali a quelle dell'approccio della modifica dell'albero.</span><span class="sxs-lookup"><span data-stu-id="8f34b-133">Notice that in this case the functional approach probably would not perform quite as well as the tree manipulation approach.</span></span> <span data-ttu-id="8f34b-134">Il problema principale è che l'approccio funzionale crea più oggetti temporanei.</span><span class="sxs-lookup"><span data-stu-id="8f34b-134">The main issue is that the functional approach creates more short lived objects.</span></span> <span data-ttu-id="8f34b-135">Tuttavia, il problema è controbilanciato dalla maggiore produttività dei programmatori resa possibile da tale approccio.</span><span class="sxs-lookup"><span data-stu-id="8f34b-135">However, the tradeoff is an effective one if using the functional approach allows for greater programmer productivity.</span></span>  
  
 <span data-ttu-id="8f34b-136">Questo esempio è molto semplice, ma serve a illustrare le differenze concettuali tra i due approcci.</span><span class="sxs-lookup"><span data-stu-id="8f34b-136">This is a very simple example, but it serves to show the difference in philosophy between the two approaches.</span></span> <span data-ttu-id="8f34b-137">L'approccio funzionale offre un aumento della produttività per la trasformazione di documenti XML di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="8f34b-137">The functional approach yields greater productivity gains for transforming larger XML documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f34b-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f34b-138">See also</span></span>

- [<span data-ttu-id="8f34b-139">Modifica di strutture ad albero XML (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f34b-139">Modifying XML Trees (LINQ to XML) (Visual Basic)</span></span>](modifying-xml-trees-linq-to-xml.md)
