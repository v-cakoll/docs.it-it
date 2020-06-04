---
title: Bug nel codice dichiarativo/imperativo misto (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: f12b1ab4-bb92-4b92-a648-0525e45b3ce7
ms.openlocfilehash: e5526a64805b19ea293d3ef28636738923d03662
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84361073"
---
# <a name="mixed-declarative-codeimperative-code-bugs-linq-to-xml-visual-basic"></a><span data-ttu-id="cca65-102">Bug nel codice dichiarativo/imperativo misto (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cca65-102">Mixed Declarative Code/Imperative Code Bugs (LINQ to XML) (Visual Basic)</span></span>
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="cca65-103">contiene i vari metodi che consentono di modificare direttamente un albero XML.</span><span class="sxs-lookup"><span data-stu-id="cca65-103">contains various methods that allow you to modify an XML tree directly.</span></span> <span data-ttu-id="cca65-104">È possibile aggiungere elementi, eliminare elementi, modificare il contenuto di un elemento, aggiungere attributi e così via.</span><span class="sxs-lookup"><span data-stu-id="cca65-104">You can add elements, delete elements, change the contents of an element, add attributes, and so on.</span></span> <span data-ttu-id="cca65-105">Questa interfaccia di programmazione è descritta in [modifica di alberi XML (LINQ to XML) (Visual Basic)](modifying-xml-trees-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="cca65-105">This programming interface is described in [Modifying XML Trees (LINQ to XML) (Visual Basic)](modifying-xml-trees-linq-to-xml.md).</span></span> <span data-ttu-id="cca65-106">Se si scorre uno degli assi, ad esempio <xref:System.Xml.Linq.XContainer.Elements%2A>, e si modifica l'albero XML durante lo scorrimento dell'asse, è possibile che vengano individuati alcuni bug strani.</span><span class="sxs-lookup"><span data-stu-id="cca65-106">If you are iterating through one of the axes, such as <xref:System.Xml.Linq.XContainer.Elements%2A>, and you are modifying the XML tree as you iterate through the axis, you can end up with some strange bugs.</span></span>  
  
 <span data-ttu-id="cca65-107">Questo problema viene talvolta definito come "problema di Halloween".</span><span class="sxs-lookup"><span data-stu-id="cca65-107">This problem is sometimes known as "The Halloween Problem".</span></span>  
  
## <a name="definition-of-the-problem"></a><span data-ttu-id="cca65-108">Definizione del problema</span><span class="sxs-lookup"><span data-stu-id="cca65-108">Definition of the Problem</span></span>  
 <span data-ttu-id="cca65-109">Quando si scrive codice usando LINQ che scorre in una raccolta, si usa uno stile dichiarativo.</span><span class="sxs-lookup"><span data-stu-id="cca65-109">When you write some code using LINQ that iterates through a collection, you are writing code in a declarative style.</span></span> <span data-ttu-id="cca65-110">Si tratta in pratica più di descrivere *cosa* si vuole eseguire, anziché *come* si vuole che venga eseguito.</span><span class="sxs-lookup"><span data-stu-id="cca65-110">It is more akin to describing *what* you want, rather that *how* you want to get it done.</span></span> <span data-ttu-id="cca65-111">Se invece si scrive codice che 1) ottiene il primo elemento, 2) lo verifica in base ad alcune condizioni, 3) lo modifica e 4) lo reinserisce nell'elenco, si usa lo stile del codice imperativo.</span><span class="sxs-lookup"><span data-stu-id="cca65-111">If you write code that 1) gets the first element, 2) tests it for some condition, 3) modifies it, and 4) puts it back into the list, then this would be imperative code.</span></span> <span data-ttu-id="cca65-112">In pratica si indica al computer *come* eseguire le operazioni desiderate.</span><span class="sxs-lookup"><span data-stu-id="cca65-112">You are telling the computer *how* to do what you want done.</span></span>  
  
 <span data-ttu-id="cca65-113">È proprio la combinazione di questi stili di codice nella stessa operazione a comportare problemi.</span><span class="sxs-lookup"><span data-stu-id="cca65-113">Mixing these styles of code in the same operation is what leads to problems.</span></span> <span data-ttu-id="cca65-114">Considerare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="cca65-114">Consider the following:</span></span>  
  
 <span data-ttu-id="cca65-115">Si supponga di disporre di un elenco collegato contenente tre elementi (a, b e c):</span><span class="sxs-lookup"><span data-stu-id="cca65-115">Suppose you have a linked list with three items in it (a, b, and c):</span></span>  
  
 `a -> b -> c`  
  
 <span data-ttu-id="cca65-116">Si supponga ora di volersi spostare nell'elenco collegato, aggiungendo tre nuovi elementi (a', b' e c').</span><span class="sxs-lookup"><span data-stu-id="cca65-116">Now, suppose that you want to move through the linked list, adding three new items (a', b', and c').</span></span> <span data-ttu-id="cca65-117">Si desidera che l'elenco collegato risultante sia simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="cca65-117">You want the resulting linked list to look like this:</span></span>  
  
 `a -> a' -> b -> b' -> c -> c'`  
  
 <span data-ttu-id="cca65-118">Si scrive pertanto codice che scorre l'elenco e aggiunge un nuovo elemento subito dopo ogni elemento già esistente.</span><span class="sxs-lookup"><span data-stu-id="cca65-118">So you write code that iterates through the list, and for every item, adds a new item right after it.</span></span> <span data-ttu-id="cca65-119">Il codice rileverà quindi per primo l'elemento `a` e inserirà `a'` dopo di esso.</span><span class="sxs-lookup"><span data-stu-id="cca65-119">What happens is that your code will first see the `a` element, and insert `a'` after it.</span></span> <span data-ttu-id="cca65-120">A questo punto il codice si sposterà al nodo successivo dell'elenco, che però corrisponde ora a `a'`,</span><span class="sxs-lookup"><span data-stu-id="cca65-120">Now, your code will move to the next node in the list, which is now `a'`!</span></span> <span data-ttu-id="cca65-121">aggiungendo tranquillamente un nuovo elemento all'elenco, `a''`.</span><span class="sxs-lookup"><span data-stu-id="cca65-121">It happily adds a new item to the list, `a''`.</span></span>  
  
 <span data-ttu-id="cca65-122">Per risolvere questo problema nel mondo reale,</span><span class="sxs-lookup"><span data-stu-id="cca65-122">How would you solve this in the real world?</span></span> <span data-ttu-id="cca65-123">sarebbe possibile fare una copia dell'elenco collegato originale e creare un elenco completamente nuovo.</span><span class="sxs-lookup"><span data-stu-id="cca65-123">Well, you might make a copy of the original linked list, and create a completely new list.</span></span> <span data-ttu-id="cca65-124">In alternativa, se si scrive codice esclusivamente imperativo, è possibile individuare il primo elemento, aggiungere il nuovo elemento e quindi avanzare di due posizioni nell'elenco collegato oppure ignorare l'elemento appena aggiunto.</span><span class="sxs-lookup"><span data-stu-id="cca65-124">Or if you are writing purely imperative code, you might find the first item, add the new item, and then advance twice in the linked list, advancing over the element that you just added.</span></span>  
  
## <a name="adding-while-iterating"></a><span data-ttu-id="cca65-125">Aggiunta durante lo scorrimento</span><span class="sxs-lookup"><span data-stu-id="cca65-125">Adding While Iterating</span></span>  
 <span data-ttu-id="cca65-126">Ad esempio, si supponga di voler scrivere codice che crea un elemento duplicato per ogni elemento di un albero:</span><span class="sxs-lookup"><span data-stu-id="cca65-126">For example, suppose you want to write some code that for every element in a tree, you want to create a duplicate element:</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <A>1</A>  
        <B>2</B>  
        <C>3</C>  
    </Root>  
For Each e As XElement In root.Elements()  
    root.Add(New XElement(e.Name, e.Value))  
Next  
```  
  
 <span data-ttu-id="cca65-127">Questo codice entra in un ciclo infinito.</span><span class="sxs-lookup"><span data-stu-id="cca65-127">This code goes into an infinite loop.</span></span> <span data-ttu-id="cca65-128">L'istruzione `foreach` scorre l'asse `Elements()`, aggiungendo nuovi elementi all'elemento `doc`,</span><span class="sxs-lookup"><span data-stu-id="cca65-128">The `foreach` statement iterates through the `Elements()` axis, adding new elements to the `doc` element.</span></span> <span data-ttu-id="cca65-129">ma finisce per scorrere anche gli elementi appena aggiunti.</span><span class="sxs-lookup"><span data-stu-id="cca65-129">It ends up iterating also through the elements it just added.</span></span> <span data-ttu-id="cca65-130">Poiché inoltre alloca oggetti nuovi a ogni iterazione del ciclo, finisce con il consumare tutta la memoria disponibile.</span><span class="sxs-lookup"><span data-stu-id="cca65-130">And because it allocates new objects with every iteration of the loop, it will eventually consume all available memory.</span></span>  
  
 <span data-ttu-id="cca65-131">Per risolvere questo problema, è possibile effettuare il pull della raccolta in memoria usando l'operatore di query standard <xref:System.Linq.Enumerable.ToList%2A>, come descritto di seguito:</span><span class="sxs-lookup"><span data-stu-id="cca65-131">You can fix this problem by pulling the collection into memory using the <xref:System.Linq.Enumerable.ToList%2A> standard query operator, as follows:</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <A>1</A>  
        <B>2</B>  
        <C>3</C>  
    </Root>  
For Each e As XElement In root.Elements().ToList()  
    root.Add(New XElement(e.Name, e.Value))  
Next  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="cca65-132">A questo punto il codice viene eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="cca65-132">Now the code works.</span></span> <span data-ttu-id="cca65-133">l'albero XML risultante è la seguente:</span><span class="sxs-lookup"><span data-stu-id="cca65-133">The resulting XML tree is the following:</span></span>  
  
```xml  
<Root>  
  <A>1</A>  
  <B>2</B>  
  <C>3</C>  
  <A>1</A>  
  <B>2</B>  
  <C>3</C>  
</Root>  
```  
  
## <a name="deleting-while-iterating"></a><span data-ttu-id="cca65-134">Eliminazione durante lo scorrimento</span><span class="sxs-lookup"><span data-stu-id="cca65-134">Deleting While Iterating</span></span>  
 <span data-ttu-id="cca65-135">Se si desidera eliminare tutti i nodi a un determinato livello, si può essere tentati di scrivere codice simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="cca65-135">If you want to delete all nodes at a certain level, you might be tempted to write code like the following:</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <A>1</A>  
        <B>2</B>  
        <C>3</C>  
    </Root>  
For Each e As XElement In root.Elements()  
    e.Remove()  
Next  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="cca65-136">Tuttavia, questo codice non consente di eseguire l'operazione desiderata.</span><span class="sxs-lookup"><span data-stu-id="cca65-136">However, this does not do what you want.</span></span> <span data-ttu-id="cca65-137">In questa situazione, dopo aver rimosso il primo elemento, A, l'elemento viene rimosso dall'albero XML contenuto nella radice e il codice del metodo Elements usato per eseguire lo scorrimento non riesce a individuare l'elemento successivo.</span><span class="sxs-lookup"><span data-stu-id="cca65-137">In this situation, after you have removed the first element, A, it is removed from the XML tree contained in root, and the code in the Elements method that is doing the iterating cannot find the next element.</span></span>  
  
 <span data-ttu-id="cca65-138">L'output del codice precedente è il seguente:</span><span class="sxs-lookup"><span data-stu-id="cca65-138">The preceding code produces the following output:</span></span>  
  
```xml  
<Root>  
  <B>2</B>  
  <C>3</C>  
</Root>  
```  
  
 <span data-ttu-id="cca65-139">Anche in questo caso la soluzione consiste nel chiamare <xref:System.Linq.Enumerable.ToList%2A> per materializzare la raccolta, come segue:</span><span class="sxs-lookup"><span data-stu-id="cca65-139">The solution again is to call <xref:System.Linq.Enumerable.ToList%2A> to materialize the collection, as follows:</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <A>1</A>  
        <B>2</B>  
        <C>3</C>  
    </Root>  
For Each e As XElement In root.Elements().ToList()  
    e.Remove()  
Next  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="cca65-140">Viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="cca65-140">This produces the following output:</span></span>  
  
```xml  
<Root />  
```  
  
 <span data-ttu-id="cca65-141">In alternativa, è possibile eliminare del tutto l'iterazione chiamando <xref:System.Xml.Linq.XElement.RemoveAll%2A> sull'elemento padre:</span><span class="sxs-lookup"><span data-stu-id="cca65-141">Alternatively, you can eliminate the iteration altogether by calling <xref:System.Xml.Linq.XElement.RemoveAll%2A> on the parent element:</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <A>1</A>  
        <B>2</B>  
        <C>3</C>  
    </Root>  
root.RemoveAll()  
Console.WriteLine(root)  
```  
  
## <a name="why-cant-linq-automatically-handle-this"></a><span data-ttu-id="cca65-142">Motivi per i quali LINQ non è in grado di gestire automaticamente questi problemi</span><span class="sxs-lookup"><span data-stu-id="cca65-142">Why Can't LINQ Automatically Handle This?</span></span>  
 <span data-ttu-id="cca65-143">Un approccio potrebbe essere inserire sempre tutto in memoria anziché ricorrere alla valutazione lazy.</span><span class="sxs-lookup"><span data-stu-id="cca65-143">One approach would be to always bring everything into memory instead of doing lazy evaluation.</span></span> <span data-ttu-id="cca65-144">Tuttavia, un tale approccio sarebbe molto oneroso in termini di prestazioni e utilizzo della memoria.</span><span class="sxs-lookup"><span data-stu-id="cca65-144">However, it would be very expensive in terms of performance and memory use.</span></span> <span data-ttu-id="cca65-145">Di fatto se pure questo approccio venisse usato con LINQ e LINQ to XML, non consentirebbe di ottenere risultati validi in situazioni realistiche.</span><span class="sxs-lookup"><span data-stu-id="cca65-145">In fact, if LINQ and (LINQ to XML) were to take this approach, it would fail in real-world situations.</span></span>  
  
 <span data-ttu-id="cca65-146">Un altro possibile approccio potrebbe essere inserire in LINQ una qualche forma di sintassi delle transazione e fare in modo che il compilatore analizzi il codice per determinare se è necessario materializzare un'eventuale raccolta specifica.</span><span class="sxs-lookup"><span data-stu-id="cca65-146">Another possible approach would be to put in some sort of transaction syntax into LINQ, and have the compiler attempt to analyze the code and determine if any particular collection needed to be materialized.</span></span> <span data-ttu-id="cca65-147">Tuttavia, il tentativo di determinare tutto il codice con effetti collaterali è incredibilmente complesso.</span><span class="sxs-lookup"><span data-stu-id="cca65-147">However, attempting to determine all code that has side-effects is incredibly complex.</span></span> <span data-ttu-id="cca65-148">Esaminare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="cca65-148">Consider the following code:</span></span>  
  
```vb  
Dim z = _  
    From e In root.Elements() _  
    Where (TestSomeCondition(e)) _  
    Select DoMyProjection(e)  
```  
  
 <span data-ttu-id="cca65-149">Tale codice di analisi dovrebbe analizzare i metodi TestSomeCondition e DoMyProjection, nonché tutti i metodi da questi chiamati, per determinare se il codice presenta effetti collaterali.</span><span class="sxs-lookup"><span data-stu-id="cca65-149">Such analysis code would need to analyze the methods TestSomeCondition and DoMyProjection, and all methods that those methods called, to determine if any code had side-effects.</span></span> <span data-ttu-id="cca65-150">Tuttavia il codice di analisi potrebbe non cercare solo il codice con effetti collaterali</span><span class="sxs-lookup"><span data-stu-id="cca65-150">But the analysis code could not just look for any code that had side-effects.</span></span> <span data-ttu-id="cca65-151">e dovrebbe selezionare solo quello che ha effetti collaterali sugli elementi figlio di `root` in questa situazione.</span><span class="sxs-lookup"><span data-stu-id="cca65-151">It would need to select for just the code that had side-effects on the child elements of `root` in this situation.</span></span>  
  
 <span data-ttu-id="cca65-152">LINQ to XML non tenta di eseguire un tale tipo di analisi.</span><span class="sxs-lookup"><span data-stu-id="cca65-152">LINQ to XML does not attempt to do any such analysis.</span></span>  
  
 <span data-ttu-id="cca65-153">È responsabilità dell'utente evitare questi problemi.</span><span class="sxs-lookup"><span data-stu-id="cca65-153">It is up to you to avoid these problems.</span></span>  
  
## <a name="guidance"></a><span data-ttu-id="cca65-154">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="cca65-154">Guidance</span></span>  
 <span data-ttu-id="cca65-155">In primo luogo, non combinare codice dichiarativo e codice imperativo.</span><span class="sxs-lookup"><span data-stu-id="cca65-155">First, do not mix declarative and imperative code.</span></span>  
  
 <span data-ttu-id="cca65-156">Anche se si conosce esattamente la semantica delle raccolte e la semantica dei metodi che modificano l'albero XML, eventuale codice scritto appositamente per evitare queste categorie di problemi dovrà essere gestito da altri sviluppatori in futuro che potrebbero non avere ugualmente chiara la situazione.</span><span class="sxs-lookup"><span data-stu-id="cca65-156">Even if you know exactly the semantics of your collections and the semantics of the methods that modify the XML tree, if you write some clever code that avoids these categories of problems, your code will need to be maintained by other developers in the future, and they may not be as clear on the issues.</span></span> <span data-ttu-id="cca65-157">Se si combinano stili di codifica dichiarativa e imperativa, il codice sarà più fragile.</span><span class="sxs-lookup"><span data-stu-id="cca65-157">If you mix declarative and imperative coding styles, your code will be more brittle.</span></span>  
  
 <span data-ttu-id="cca65-158">Se si scrive codice che materializza una raccolta allo scopo di evitare questi problemi, annotarlo in appositi commenti nel codice, per consentire ai programmatori che effettuano interventi di manutenzione di comprendere il problema.</span><span class="sxs-lookup"><span data-stu-id="cca65-158">If you write code that materializes a collection so that these problems are avoided, note it with comments as appropriate in your code, so that maintenance programmers will understand the issue.</span></span>  
  
 <span data-ttu-id="cca65-159">In secondo luogo, usare solo codice dichiarativo, se consentito dalle prestazioni e da altre considerazioni.</span><span class="sxs-lookup"><span data-stu-id="cca65-159">Second, if performance and other considerations allow, use only declarative code.</span></span> <span data-ttu-id="cca65-160">Non modificare l'albero XML esistente,</span><span class="sxs-lookup"><span data-stu-id="cca65-160">Don't modify your existing XML tree.</span></span> <span data-ttu-id="cca65-161">ma generarne una nuova.</span><span class="sxs-lookup"><span data-stu-id="cca65-161">Generate a new one.</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <A>1</A>  
        <B>2</B>  
        <C>3</C>  
    </Root>  
Dim newRoot As XElement = New XElement("Root", _  
    root.Elements(), root.Elements())  
Console.WriteLine(newRoot)  
```  
  
## <a name="see-also"></a><span data-ttu-id="cca65-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cca65-162">See also</span></span>

- [<span data-ttu-id="cca65-163">Programmazione LINQ to XML avanzata (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cca65-163">Advanced LINQ to XML Programming (Visual Basic)</span></span>](advanced-linq-to-xml-programming.md)
