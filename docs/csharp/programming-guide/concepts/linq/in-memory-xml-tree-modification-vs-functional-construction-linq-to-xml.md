---
title: Modifica dell'albero XML in memoria rispetto alla costruzione funzionale (LINQ to XML) (C#)
description: Questi esempi modificano la forma di un documento XML modificando il sistema e usando LINQ to XML costruzione funzionale in C#.
ms.date: 07/20/2015
ms.assetid: b5afc31d-a325-4ec6-bf17-0ff90a20ffca
ms.openlocfilehash: 7a2e3d2ddcd452cf6a58e9d5cc886f3e8b8dd325
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165778"
---
# <a name="in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml-c"></a><span data-ttu-id="ceb0f-103">Modifica dell'albero XML in memoria rispetto alla costruzione funzionale (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="ceb0f-103">In-Memory XML Tree Modification vs. Functional Construction (LINQ to XML) (C#)</span></span>
<span data-ttu-id="ceb0f-104">La modifica di un albero XML sul posto è un approccio tradizionale per cambiare la forma di un documento XML.</span><span class="sxs-lookup"><span data-stu-id="ceb0f-104">Modifying an XML tree in place is a traditional approach to changing the shape of an XML document.</span></span> <span data-ttu-id="ceb0f-105">In una tipica applicazione un documento viene caricato in un archivio dati quale DOM o [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], viene usata un'interfaccia di programmazione per inserire o eliminare nodi oppure per modificarne il contenuto, quindi il file XML viene salvato in un file o trasmesso tramite una rete.</span><span class="sxs-lookup"><span data-stu-id="ceb0f-105">A typical application loads a document into a data store such as DOM or [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]; uses a programming interface to insert nodes, delete nodes, or change the content of nodes; and then saves the XML to a file or transmits it over a network.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="ceb0f-106">consente di adottare un altro approccio che risulta utile in molti scenari: la *costruzione funzionale*.</span><span class="sxs-lookup"><span data-stu-id="ceb0f-106">enables another approach that is useful in many scenarios: *functional construction*.</span></span> <span data-ttu-id="ceb0f-107">Nella costruzione funzionale la modifica di dati viene considerata come un problema di trasformazione, anziché come una modifica dettagliata di un archivio dati.</span><span class="sxs-lookup"><span data-stu-id="ceb0f-107">Functional construction treats modifying data as a problem of transformation, rather than as detailed manipulation of a data store.</span></span> <span data-ttu-id="ceb0f-108">Se è possibile trasformare in modo efficiente una rappresentazione di dati da un formato a un altro, il risultato è identico a quello ottenuto modificando un archivio dati in modo da cambiarne la forma.</span><span class="sxs-lookup"><span data-stu-id="ceb0f-108">If you can take a representation of data and transform it efficiently from one form to another, the result is the same as if you took one data store and manipulated it in some way to take another shape.</span></span> <span data-ttu-id="ceb0f-109">Un aspetto importante dell'approccio della costruzione funzionale riguarda il passaggio dei risultati delle query ai costruttori <xref:System.Xml.Linq.XDocument> e <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="ceb0f-109">A key to the functional construction approach is to pass the results of queries to <xref:System.Xml.Linq.XDocument> and <xref:System.Xml.Linq.XElement> constructors.</span></span>  
  
 <span data-ttu-id="ceb0f-110">In molti casi, è possibile scrivere il codice di trasformazione in tempi ridotti rispetto a quelli richiesti per la modifica dell'archivio dati. Il codice è inoltre più affidabile e facile da gestire.</span><span class="sxs-lookup"><span data-stu-id="ceb0f-110">In many cases you can write the transformational code in a fraction of the time that it would take to manipulate the data store, and that code is more robust and easier to maintain.</span></span> <span data-ttu-id="ceb0f-111">In questi casi, anche se l'approccio della trasformazione può richiedere una maggiore potenza di elaborazione, si tratta di una soluzione più efficace per la modifica dei dati.</span><span class="sxs-lookup"><span data-stu-id="ceb0f-111">In these cases, even though the transformational approach can take more processing power, it is a more effective way to modify data.</span></span> <span data-ttu-id="ceb0f-112">Se gli sviluppatori hanno familiarità con l'approccio funzionale, il codice risultante è spesso più facile da comprendere.</span><span class="sxs-lookup"><span data-stu-id="ceb0f-112">If a developer is familiar with the functional approach, the resulting code in many cases is easier to understand.</span></span> <span data-ttu-id="ceb0f-113">Risulta facile trovare il codice che modifica ogni parte dell'albero.</span><span class="sxs-lookup"><span data-stu-id="ceb0f-113">It is easy to find the code that modifies each part of the tree.</span></span>  
  
 <span data-ttu-id="ceb0f-114">Molti programmatori DOM hanno una maggiore dimestichezza con l'approccio in cui un albero XML viene modificato sul posto, mentre il codice scritto con l'approccio funzionale potrebbe sembrare insolito agli sviluppatori che non hanno ancora compreso tale approccio.</span><span class="sxs-lookup"><span data-stu-id="ceb0f-114">The approach where you modify an XML tree in-place is more familiar to many DOM programmers, whereas code written using the functional approach might look unfamiliar to a developer who doesn't yet understand that approach.</span></span> <span data-ttu-id="ceb0f-115">Se è necessario apportare solo una piccola modifica a un albero XML di grandi dimensioni, l'approccio in cui un albero viene modificato sul posto richiederà in molti casi meno tempo CPU.</span><span class="sxs-lookup"><span data-stu-id="ceb0f-115">If you have to only make a small modification to a large XML tree, the approach where you modify a tree in place in many cases will take less CPU time.</span></span>  
  
 <span data-ttu-id="ceb0f-116">In questo argomento viene illustrato un esempio implementato con entrambi gli approcci.</span><span class="sxs-lookup"><span data-stu-id="ceb0f-116">This topic provides an example that is implemented with both approaches.</span></span>  
  
## <a name="transforming-attributes-into-elements"></a><span data-ttu-id="ceb0f-117">Trasformazione di attributi in elementi</span><span class="sxs-lookup"><span data-stu-id="ceb0f-117">Transforming Attributes into Elements</span></span>  
 <span data-ttu-id="ceb0f-118">Per questo esempio, si supponga di voler modificare il semplice documento XML seguente in modo che gli attributi diventino elementi.</span><span class="sxs-lookup"><span data-stu-id="ceb0f-118">For this example, suppose you want to modify the following simple XML document so that the attributes become elements.</span></span> <span data-ttu-id="ceb0f-119">In questo argomento viene presentato dapprima l'approccio tradizionale della modifica sul posto</span><span class="sxs-lookup"><span data-stu-id="ceb0f-119">This topic first presents the traditional in-place modification approach.</span></span> <span data-ttu-id="ceb0f-120">e quindi l'approccio della costruzione funzionale.</span><span class="sxs-lookup"><span data-stu-id="ceb0f-120">It then shows the functional construction approach.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<Root Data1="123" Data2="456">  
  <Child1>Content</Child1>  
</Root>  
```  
  
### <a name="modifying-the-xml-tree"></a><span data-ttu-id="ceb0f-121">Modifica dell'albero XML</span><span class="sxs-lookup"><span data-stu-id="ceb0f-121">Modifying the XML Tree</span></span>  
 <span data-ttu-id="ceb0f-122">È possibile scrivere codice procedurale per creare elementi dagli attributi e quindi eliminare gli attributi, come segue:</span><span class="sxs-lookup"><span data-stu-id="ceb0f-122">You can write some procedural code to create elements from the attributes, and then delete the attributes, as follows:</span></span>  
  
```csharp  
XElement root = XElement.Load("Data.xml");  
foreach (XAttribute att in root.Attributes()) {  
    root.Add(new XElement(att.Name, (string)att));  
}  
root.Attributes().Remove();  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="ceb0f-123">Questo codice genera l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="ceb0f-123">This code produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child1>Content</Child1>  
  <Data1>123</Data1>  
  <Data2>456</Data2>  
</Root>  
```  
  
### <a name="functional-construction-approach"></a><span data-ttu-id="ceb0f-124">Approccio della costruzione funzionale</span><span class="sxs-lookup"><span data-stu-id="ceb0f-124">Functional Construction Approach</span></span>  
 <span data-ttu-id="ceb0f-125">Al contrario, un approccio funzionale è costituito da codice per creare un nuovo albero, selezionando gli elementi e gli attributi dall'albero di origine e trasformandoli nel modo appropriato prima di aggiungerli nel nuovo albero.</span><span class="sxs-lookup"><span data-stu-id="ceb0f-125">By contrast, a functional approach consists of code to form a new tree, picking and choosing elements and attributes from the source tree, and transforming them as appropriate as they are added to the new tree.</span></span> <span data-ttu-id="ceb0f-126">Di seguito è illustrato il risultato dell'approccio funzionale:</span><span class="sxs-lookup"><span data-stu-id="ceb0f-126">The functional approach looks like the following:</span></span>  
  
```csharp  
XElement root = XElement.Load("Data.xml");  
XElement newTree = new XElement("Root",  
    root.Element("Child1"),  
    from att in root.Attributes()  
    select new XElement(att.Name, (string)att)  
);  
Console.WriteLine(newTree);  
```  
  
 <span data-ttu-id="ceb0f-127">In questo esempio viene restituito stesso lo stesso output XML del primo esempio.</span><span class="sxs-lookup"><span data-stu-id="ceb0f-127">This example outputs the same XML as the first example.</span></span> <span data-ttu-id="ceb0f-128">Si noti, tuttavia, che è possibile visualizzare la struttura risultante del nuovo codice XML nell'approccio funzionale.</span><span class="sxs-lookup"><span data-stu-id="ceb0f-128">However, notice that you can actually see the resulting structure of the new XML in the functional approach.</span></span> <span data-ttu-id="ceb0f-129">È quindi possibile vedere la creazione dell'elemento `Root`, il codice che effettua il pull dell'elemento `Child1` dall'albero di origine e il codice che trasforma gli attributi dell'albero di origine in elementi nel nuovo albero.</span><span class="sxs-lookup"><span data-stu-id="ceb0f-129">You can see the creation of the `Root` element, the code that pulls the `Child1` element from the source tree, and the code that transforms the attributes from the source tree to elements in the new tree.</span></span>  
  
 <span data-ttu-id="ceb0f-130">L'esempio funzionale in questo caso non è più breve del primo e in realtà non è neanche più semplice.</span><span class="sxs-lookup"><span data-stu-id="ceb0f-130">The functional example in this case is not any shorter than the first example, and it is not really any simpler.</span></span> <span data-ttu-id="ceb0f-131">Se tuttavia è necessario apportare molte modifiche a un albero XML, l'approccio non funzionale diventerà alquanto complesso e poco flessibile.</span><span class="sxs-lookup"><span data-stu-id="ceb0f-131">However, if you have many changes to make to an XML tree, the non functional approach will become quite complex and somewhat obtuse.</span></span> <span data-ttu-id="ceb0f-132">Al contrario, quando si usa l'approccio funzionale, viene comunque creato l'XML desiderato, incorporando query ed espressioni nel modo appropriato, per inserire il contenuto desiderato.</span><span class="sxs-lookup"><span data-stu-id="ceb0f-132">In contrast, when using the functional approach, you still just form the desired XML, embedding queries and expressions as appropriate, to pull in the desired content.</span></span> <span data-ttu-id="ceb0f-133">L'approccio funzionale restituisce codice più facile gestire.</span><span class="sxs-lookup"><span data-stu-id="ceb0f-133">The functional approach yields code that is easier to maintain.</span></span>  
  
 <span data-ttu-id="ceb0f-134">Si noti che in questo caso le prestazioni dell'approccio funzionale potrebbero non essere uguali a quelle dell'approccio della modifica dell'albero.</span><span class="sxs-lookup"><span data-stu-id="ceb0f-134">Notice that in this case the functional approach probably would not perform quite as well as the tree manipulation approach.</span></span> <span data-ttu-id="ceb0f-135">Il problema principale è che l'approccio funzionale crea più oggetti temporanei.</span><span class="sxs-lookup"><span data-stu-id="ceb0f-135">The main issue is that the functional approach creates more short lived objects.</span></span> <span data-ttu-id="ceb0f-136">Tuttavia, il problema è controbilanciato dalla maggiore produttività dei programmatori resa possibile da tale approccio.</span><span class="sxs-lookup"><span data-stu-id="ceb0f-136">However, the tradeoff is an effective one if using the functional approach allows for greater programmer productivity.</span></span>  
  
 <span data-ttu-id="ceb0f-137">Questo esempio è molto semplice, ma serve a illustrare le differenze concettuali tra i due approcci.</span><span class="sxs-lookup"><span data-stu-id="ceb0f-137">This is a very simple example, but it serves to show the difference in philosophy between the two approaches.</span></span> <span data-ttu-id="ceb0f-138">L'approccio funzionale offre un aumento della produttività per la trasformazione di documenti XML di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="ceb0f-138">The functional approach yields greater productivity gains for transforming larger XML documents.</span></span>  
  