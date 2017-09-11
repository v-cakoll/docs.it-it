---
title: Raccolte (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: get-started-article
dev_langs:
- VB
ms.assetid: 5f7749f3-aaf2-4319-b63c-bfa72e1e2b7a
caps.latest.revision: 6
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b3c8de3e22075d576f86bcd4eb599946740ebe16
ms.contentlocale: it-it
ms.lasthandoff: 03/13/2017

---
# <a name="collections-visual-basic"></a><span data-ttu-id="d528d-102">Raccolte (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d528d-102">Collections (Visual Basic)</span></span>
<span data-ttu-id="d528d-103">Per molte applicazioni è utile creare e gestire gruppi di oggetti correlati.</span><span class="sxs-lookup"><span data-stu-id="d528d-103">For many applications, you want to create and manage groups of related objects.</span></span> <span data-ttu-id="d528d-104">È possibile raggruppare gli oggetti in due modi: creando matrici di oggetti e creando raccolte di oggetti.</span><span class="sxs-lookup"><span data-stu-id="d528d-104">There are two ways to group objects: by creating arrays of objects, and by creating collections of objects.</span></span>  
  
 <span data-ttu-id="d528d-105">Le matrici sono estremamente utili per la creazione e l'uso di un numero fisso di oggetti fortemente tipizzati.</span><span class="sxs-lookup"><span data-stu-id="d528d-105">Arrays are most useful for creating and working with a fixed number of strongly-typed objects.</span></span> <span data-ttu-id="d528d-106">Per informazioni sulle matrici, vedere [matrici](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="d528d-106">For information about arrays, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
 <span data-ttu-id="d528d-107">Le raccolte consentono di lavorare in modo più flessibile con gruppi di oggetti.</span><span class="sxs-lookup"><span data-stu-id="d528d-107">Collections provide a more flexible way to work with groups of objects.</span></span> <span data-ttu-id="d528d-108">A differenza delle matrici, il gruppo di oggetti con cui si lavora può aumentare e diminuire in modo dinamico in base alle esigenze dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d528d-108">Unlike arrays, the group of objects you work with can grow and shrink dynamically as the needs of the application change.</span></span> <span data-ttu-id="d528d-109">Per alcune raccolte è possibile assegnare una chiave a qualsiasi oggetto inserito nella raccolta in modo da recuperare rapidamente l'oggetto usando la chiave.</span><span class="sxs-lookup"><span data-stu-id="d528d-109">For some collections, you can assign a key to any object that you put into the collection so that you can quickly retrieve the object by using the key.</span></span>  
  
 <span data-ttu-id="d528d-110">Una Collection è una classe. Di conseguenza, prima di poter aggiungere elementi a una nuova raccolta è necessario dichiarare la Collection.</span><span class="sxs-lookup"><span data-stu-id="d528d-110">A collection is a class, so you must declare an instance of the class before you can add elements to that collection.</span></span>  
  
 <span data-ttu-id="d528d-111">Se la raccolta contiene elementi di un solo tipo di dati, è possibile utilizzare una delle classi di <xref:System.Collections.Generic?displayProperty=fullName>dello spazio dei nomi.</xref:System.Collections.Generic?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d528d-111">If your collection contains elements of only one data type, you can use one of the classes in the <xref:System.Collections.Generic?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="d528d-112">In una raccolta generica viene imposta l'indipendenza dai tipi, in modo da impedire che vengano aggiunti altri tipi di dati alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="d528d-112">A generic collection enforces type safety so that no other data type can be added to it.</span></span> <span data-ttu-id="d528d-113">Quando si recupera un elemento da una raccolta generica, non è necessario determinarne il tipo di dati né convertirlo.</span><span class="sxs-lookup"><span data-stu-id="d528d-113">When you retrieve an element from a generic collection, you do not have to determine its data type or convert it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d528d-114">Per gli esempi in questo argomento, includere [importazioni](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) le istruzioni per la `System.Collections.Generic` e `System.Linq` gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="d528d-114">For the examples in this topic, include [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) statements for the `System.Collections.Generic` and `System.Linq` namespaces.</span></span>  
  
 <span data-ttu-id="d528d-115">**Contenuto dell'argomento**</span><span class="sxs-lookup"><span data-stu-id="d528d-115">**In this topic**</span></span>  
  
-   [<span data-ttu-id="d528d-116">Utilizzando una semplice raccolta</span><span class="sxs-lookup"><span data-stu-id="d528d-116">Using a Simple Collection</span></span>](#BKMK_SimpleCollection)  
  
-   [<span data-ttu-id="d528d-117">Tipi di raccolte</span><span class="sxs-lookup"><span data-stu-id="d528d-117">Kinds of Collections</span></span>](#BKMK_KindsOfCollections)  
  
    -   [<span data-ttu-id="d528d-118">Classi System.Collections.Generic</span><span class="sxs-lookup"><span data-stu-id="d528d-118">System.Collections.Generic Classes</span></span>](#BKMK_Generic)  
  
    -   [<span data-ttu-id="d528d-119">Classi System.Collections.Concurrent</span><span class="sxs-lookup"><span data-stu-id="d528d-119">System.Collections.Concurrent Classes</span></span>](#BKMK_Concurrent)  
  
    -   [<span data-ttu-id="d528d-120">Classi System. Collections</span><span class="sxs-lookup"><span data-stu-id="d528d-120">System.Collections Classes</span></span>](#BKMK_Collections)  
  
    -   [<span data-ttu-id="d528d-121">Classe di raccolta di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d528d-121">Visual Basic Collection Class</span></span>](#BKMK_VisualBasic)  
  
-   [<span data-ttu-id="d528d-122">Implementazione di una raccolta di coppie chiave/valore</span><span class="sxs-lookup"><span data-stu-id="d528d-122">Implementing a Collection of Key/Value Pairs</span></span>](#BKMK_KeyValuePairs)  
  
-   [<span data-ttu-id="d528d-123">Utilizzo di LINQ per accedere a una raccolta</span><span class="sxs-lookup"><span data-stu-id="d528d-123">Using LINQ to Access a Collection</span></span>](#BKMK_LINQ)  
  
-   [<span data-ttu-id="d528d-124">Ordinamento di una raccolta</span><span class="sxs-lookup"><span data-stu-id="d528d-124">Sorting a Collection</span></span>](#BKMK_Sorting)  
  
-   [<span data-ttu-id="d528d-125">Definizione di una raccolta personalizzata</span><span class="sxs-lookup"><span data-stu-id="d528d-125">Defining a Custom Collection</span></span>](#BKMK_CustomCollection)  
  
-   [<span data-ttu-id="d528d-126">Iteratori</span><span class="sxs-lookup"><span data-stu-id="d528d-126">Iterators</span></span>](#BKMK_Iterators)  
  
<a name="BKMK_SimpleCollection"></a>
## <a name="using-a-simple-collection"></a><span data-ttu-id="d528d-127">Uso di una raccolta semplice</span><span class="sxs-lookup"><span data-stu-id="d528d-127">Using a Simple Collection</span></span>  
 <span data-ttu-id="d528d-128">Negli esempi inclusi in questa sezione utilizzano gli elementi generici <xref:System.Collections.Generic.List%601>classe, che consente di lavorare con un elenco di oggetti fortemente tipizzato.</xref:System.Collections.Generic.List%601></span><span class="sxs-lookup"><span data-stu-id="d528d-128">The examples in this section use the generic <xref:System.Collections.Generic.List%601> class, which enables you to work with a strongly typed list of objects.</span></span>  
  
 <span data-ttu-id="d528d-129">Nell'esempio seguente viene creato un elenco di stringhe e quindi scorre le stringhe mediante un [For Each... Avanti](../../../visual-basic/language-reference/statements/for-each-next-statement.md) istruzione.</span><span class="sxs-lookup"><span data-stu-id="d528d-129">The following example creates a list of strings and then iterates through the strings by using a [For Each…Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement.</span></span>  
  
```vb  
' Create a list of strings.  
Dim salmons As New List(Of String)  
salmons.Add("chinook")  
salmons.Add("coho")  
salmons.Add("pink")  
salmons.Add("sockeye")  
  
' Iterate through the list.  
For Each salmon As String In salmons  
    Console.Write(salmon & " ")  
Next  
'Output: chinook coho pink sockeye  
```  
  
 <span data-ttu-id="d528d-130">Se il contenuto di una raccolta è noti in anticipo, è possibile utilizzare un *inizializzatore di raccolta* per inizializzare la raccolta.</span><span class="sxs-lookup"><span data-stu-id="d528d-130">If the contents of a collection are known in advance, you can use a *collection initializer* to initialize the collection.</span></span> <span data-ttu-id="d528d-131">Per ulteriori informazioni, vedere [gli inizializzatori di insieme](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).</span><span class="sxs-lookup"><span data-stu-id="d528d-131">For more information, see [Collection Initializers](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).</span></span>  
  
 <span data-ttu-id="d528d-132">L'esempio seguente è identico all'esempio precedente, ma usa un inizializzatore di raccolta per aggiungere elementi alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="d528d-132">The following example is the same as the previous example, except a collection initializer is used to add elements to the collection.</span></span>  
  
```vb  
' Create a list of strings by using a  
' collection initializer.  
Dim salmons As New List(Of String) From  
    {"chinook", "coho", "pink", "sockeye"}  
  
For Each salmon As String In salmons  
    Console.Write(salmon & " ")  
Next  
'Output: chinook coho pink sockeye  
```  
  
 <span data-ttu-id="d528d-133">È possibile utilizzare un [per... Avanti](../../../visual-basic/language-reference/statements/for-next-statement.md) istruzione anziché un `For Each` istruzione per scorrere una raccolta.</span><span class="sxs-lookup"><span data-stu-id="d528d-133">You can use a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) statement instead of a `For Each` statement to iterate through a collection.</span></span> <span data-ttu-id="d528d-134">Questo è possibile mediante l'accesso agli elementi della raccolta dalla posizione di indice.</span><span class="sxs-lookup"><span data-stu-id="d528d-134">You accomplish this by accessing the collection elements by the index position.</span></span> <span data-ttu-id="d528d-135">L'indice degli elementi inizia da 0 e termina in corrispondenza del numero di elementi meno 1.</span><span class="sxs-lookup"><span data-stu-id="d528d-135">The index of the elements starts at 0 and ends at the element count minus 1.</span></span>  
  
 <span data-ttu-id="d528d-136">Nell'esempio seguente scorre gli elementi di una raccolta tramite `For…Next` anziché `For Each`.</span><span class="sxs-lookup"><span data-stu-id="d528d-136">The following example iterates through the elements of a collection by using `For…Next` instead of `For Each`.</span></span>  
  
```vb  
Dim salmons As New List(Of String) From  
    {"chinook", "coho", "pink", "sockeye"}  
  
For index = 0 To salmons.Count - 1  
    Console.Write(salmons(index) & " ")  
Next  
'Output: chinook coho pink sockeye  
```  
  
 <span data-ttu-id="d528d-137">Nell'esempio seguente viene rimosso un elemento dalla raccolta specificando l'oggetto da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="d528d-137">The following example removes an element from the collection by specifying the object to remove.</span></span>  
  
```vb  
' Create a list of strings by using a  
' collection initializer.  
Dim salmons As New List(Of String) From  
    {"chinook", "coho", "pink", "sockeye"}  
  
' Remove an element in the list by specifying  
' the object.  
salmons.Remove("coho")  
  
For Each salmon As String In salmons  
    Console.Write(salmon & " ")  
Next  
'Output: chinook pink sockeye  
```  
  
 <span data-ttu-id="d528d-138">Nell'esempio seguente vengono rimossi elementi da un elenco generico.</span><span class="sxs-lookup"><span data-stu-id="d528d-138">The following example removes elements from a generic list.</span></span> <span data-ttu-id="d528d-139">Invece di un `For Each` istruzione, una [per... Avanti](../../../visual-basic/language-reference/statements/for-next-statement.md) viene utilizzata l'istruzione che esegue l'iterazione in ordine decrescente.</span><span class="sxs-lookup"><span data-stu-id="d528d-139">Instead of a `For Each` statement, a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) statement that iterates in descending order is used.</span></span> <span data-ttu-id="d528d-140">In questo modo il <xref:System.Collections.Generic.List%601.RemoveAt%2A>(metodo), gli elementi dopo un elemento rimosso un valore di indice più basso.</xref:System.Collections.Generic.List%601.RemoveAt%2A></span><span class="sxs-lookup"><span data-stu-id="d528d-140">This is because the <xref:System.Collections.Generic.List%601.RemoveAt%2A> method causes elements after a removed element to have a lower index value.</span></span>  
  
```vb  
Dim numbers As New List(Of Integer) From  
    {0, 1, 2, 3, 4, 5, 6, 7, 8, 9}  
  
' Remove odd numbers.  
For index As Integer = numbers.Count - 1 To 0 Step -1  
    If numbers(index) Mod 2 = 1 Then  
        ' Remove the element by specifying  
        ' the zero-based index in the list.  
        numbers.RemoveAt(index)  
    End If  
Next  
  
' Iterate through the list.  
' A lambda expression is placed in the ForEach method  
' of the List(T) object.  
numbers.ForEach(  
    Sub(number) Console.Write(number & " "))  
' Output: 0 2 4 6 8  
```  
  
 <span data-ttu-id="d528d-141">Per il tipo di elementi <xref:System.Collections.Generic.List%601>è inoltre possibile definire la propria classe.</xref:System.Collections.Generic.List%601></span><span class="sxs-lookup"><span data-stu-id="d528d-141">For the type of elements in the <xref:System.Collections.Generic.List%601>, you can also define your own class.</span></span> <span data-ttu-id="d528d-142">Nell'esempio seguente, il `Galaxy` classe che viene utilizzato il <xref:System.Collections.Generic.List%601>è definito nel codice.</xref:System.Collections.Generic.List%601></span><span class="sxs-lookup"><span data-stu-id="d528d-142">In the following example, the `Galaxy` class that is used by the <xref:System.Collections.Generic.List%601> is defined in the code.</span></span>  
  
```vb  
Private Sub IterateThroughList()  
    Dim theGalaxies As New List(Of Galaxy) From  
        {  
            New Galaxy With {.Name = "Tadpole", .MegaLightYears = 400},  
            New Galaxy With {.Name = "Pinwheel", .MegaLightYears = 25},  
            New Galaxy With {.Name = "Milky Way", .MegaLightYears = 0},  
            New Galaxy With {.Name = "Andromeda", .MegaLightYears = 3}  
        }  
  
    For Each theGalaxy In theGalaxies  
        With theGalaxy  
            Console.WriteLine(.Name & "  " & .MegaLightYears)  
        End With  
    Next  
  
    ' Output:  
    '  Tadpole  400  
    '  Pinwheel  25  
    '  Milky Way  0  
    '  Andromeda  3  
End Sub  
  
Public Class Galaxy  
    Public Property Name As String  
    Public Property MegaLightYears As Integer  
End Class  
```  
  
<a name="BKMK_KindsOfCollections"></a>
## <a name="kinds-of-collections"></a><span data-ttu-id="d528d-143">Tipi di raccolte</span><span class="sxs-lookup"><span data-stu-id="d528d-143">Kinds of Collections</span></span>   
 <span data-ttu-id="d528d-144">Molte raccolte comuni vengono fornite da .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d528d-144">Many common collections are provided by the .NET Framework.</span></span> <span data-ttu-id="d528d-145">Ogni tipo di raccolta è progettato per uno scopo specifico.</span><span class="sxs-lookup"><span data-stu-id="d528d-145">Each type of collection is designed for a specific purpose.</span></span>  
  
 <span data-ttu-id="d528d-146">In questa sezione sono descritte alcune classi di raccolte comuni:</span><span class="sxs-lookup"><span data-stu-id="d528d-146">Some of the common collection classes are described in this section:</span></span>  
  
-   <span data-ttu-id="d528d-147">@System.Collections.Genericclassi</span><span class="sxs-lookup"><span data-stu-id="d528d-147">@System.Collections.Generic classes</span></span>  
  
-   <span data-ttu-id="d528d-148">@System.Collections.Concurrentclassi</span><span class="sxs-lookup"><span data-stu-id="d528d-148">@System.Collections.Concurrent classes</span></span>  
  
-   <span data-ttu-id="d528d-149">@System.Collectionsclassi</span><span class="sxs-lookup"><span data-stu-id="d528d-149">@System.Collections classes</span></span>  
  
-   <span data-ttu-id="d528d-150">Visual Basic `Collection` (classe)</span><span class="sxs-lookup"><span data-stu-id="d528d-150">Visual Basic `Collection` class</span></span>  
  
<a name="BKMK_Generic"></a>
### <a name="systemcollectionsgeneric-classes"></a><span data-ttu-id="d528d-151">Classi System.Collections.Generic</span><span class="sxs-lookup"><span data-stu-id="d528d-151">System.Collections.Generic Classes</span></span>  

 <span data-ttu-id="d528d-152">È possibile creare una raccolta generica utilizzando una delle classi di <xref:System.Collections.Generic>dello spazio dei nomi.</xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="d528d-152">You can create a generic collection by using one of the classes in the <xref:System.Collections.Generic> namespace.</span></span> <span data-ttu-id="d528d-153">Una raccolta generica è utile quando ogni elemento al suo interno presenta lo stesso tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="d528d-153">A generic collection is useful when every item in the collection has the same data type.</span></span> <span data-ttu-id="d528d-154">Una raccolta generica applica la tipizzazione forte consentendo di aggiungere soltanto i tipi di dati desiderati.</span><span class="sxs-lookup"><span data-stu-id="d528d-154">A generic collection enforces strong typing by allowing only the desired data type to be added.</span></span>  
  
 <span data-ttu-id="d528d-155">Nella tabella seguente sono elencate alcune delle classi di frequente il <xref:System.Collections.Generic?displayProperty=fullName>dello spazio dei nomi:</xref:System.Collections.Generic?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d528d-155">The following table lists some of the frequently used classes of the <xref:System.Collections.Generic?displayProperty=fullName> namespace:</span></span>  
  
|<span data-ttu-id="d528d-156">Classe</span><span class="sxs-lookup"><span data-stu-id="d528d-156">Class</span></span>|<span data-ttu-id="d528d-157">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d528d-157">Description</span></span>|  
|---|---|  
|<span data-ttu-id="d528d-158"><xref:System.Collections.Generic.Dictionary%602></xref:System.Collections.Generic.Dictionary%602></span><span class="sxs-lookup"><span data-stu-id="d528d-158"><xref:System.Collections.Generic.Dictionary%602></span></span>|<span data-ttu-id="d528d-159">Rappresenta una raccolta di coppie chiave/valore organizzate in base alla chiave.</span><span class="sxs-lookup"><span data-stu-id="d528d-159">Represents a collection of key/value pairs that are organized based on the key.</span></span>|  
|<span data-ttu-id="d528d-160"><xref:System.Collections.Generic.List%601></xref:System.Collections.Generic.List%601></span><span class="sxs-lookup"><span data-stu-id="d528d-160"><xref:System.Collections.Generic.List%601></span></span>|<span data-ttu-id="d528d-161">Rappresenta un elenco di oggetti accessibile in base all'indice.</span><span class="sxs-lookup"><span data-stu-id="d528d-161">Represents a list of objects that can be accessed by index.</span></span> <span data-ttu-id="d528d-162">Fornisce metodi per la ricerca, l'ordinamento e la modifica degli elenchi.</span><span class="sxs-lookup"><span data-stu-id="d528d-162">Provides methods to search, sort, and modify lists.</span></span>|  
|<span data-ttu-id="d528d-163"><xref:System.Collections.Generic.Queue%601></xref:System.Collections.Generic.Queue%601></span><span class="sxs-lookup"><span data-stu-id="d528d-163"><xref:System.Collections.Generic.Queue%601></span></span>|<span data-ttu-id="d528d-164">Rappresenta una raccolta di oggetti FIFO (First-In First-Out).</span><span class="sxs-lookup"><span data-stu-id="d528d-164">Represents a first in, first out (FIFO) collection of objects.</span></span>|  
|<span data-ttu-id="d528d-165"><xref:System.Collections.Generic.SortedList%602></xref:System.Collections.Generic.SortedList%602></span><span class="sxs-lookup"><span data-stu-id="d528d-165"><xref:System.Collections.Generic.SortedList%602></span></span>|<span data-ttu-id="d528d-166">Rappresenta una raccolta di coppie chiave/valore ordinate per chiave in base alle associato <xref:System.Collections.Generic.IComparer%601>implementazione.</xref:System.Collections.Generic.IComparer%601></span><span class="sxs-lookup"><span data-stu-id="d528d-166">Represents a collection of key/value pairs that are sorted by key based on the associated <xref:System.Collections.Generic.IComparer%601> implementation.</span></span>|  
|<span data-ttu-id="d528d-167"><xref:System.Collections.Generic.Stack%601></xref:System.Collections.Generic.Stack%601></span><span class="sxs-lookup"><span data-stu-id="d528d-167"><xref:System.Collections.Generic.Stack%601></span></span>|<span data-ttu-id="d528d-168">Rappresenta una raccolta di oggetti LIFO (Last-In First-Out).</span><span class="sxs-lookup"><span data-stu-id="d528d-168">Represents a last in, first out (LIFO) collection of objects.</span></span>|  
  
 <span data-ttu-id="d528d-169">Per ulteriori informazioni, vedere [utilizzati tipi di raccolte comunemente](http://msdn.microsoft.com/library/f5d4c6a4-0d7b-4944-a9fb-3b12d9ebfd55), [selezione di una classe di raccolta](../../../standard/collections/selecting-a-collection-class.md)e <xref:System.Collections.Generic?displayProperty=fullName>.</xref:System.Collections.Generic?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d528d-169">For additional information, see [Commonly Used Collection Types](http://msdn.microsoft.com/library/f5d4c6a4-0d7b-4944-a9fb-3b12d9ebfd55), [Selecting a Collection Class](../../../standard/collections/selecting-a-collection-class.md), and <xref:System.Collections.Generic?displayProperty=fullName>.</span></span>  
  
<a name="BKMK_Concurrent"></a>
### <a name="systemcollectionsconcurrent-classes"></a><span data-ttu-id="d528d-170">Classi System.Collections.Concurrent</span><span class="sxs-lookup"><span data-stu-id="d528d-170">System.Collections.Concurrent Classes</span></span>   
 <span data-ttu-id="d528d-171">In .NET Framework 4 o successive, gli insiemi di <xref:System.Collections.Concurrent>dello spazio dei nomi forniscono operazioni thread-safe efficienti per accedere agli elementi della raccolta da più thread.</xref:System.Collections.Concurrent></span><span class="sxs-lookup"><span data-stu-id="d528d-171">In the .NET Framework 4 or newer, the collections in the <xref:System.Collections.Concurrent> namespace provide efficient thread-safe operations for accessing collection items from multiple threads.</span></span>  
  
 <span data-ttu-id="d528d-172">Le classi di <xref:System.Collections.Concurrent>è necessario utilizzare lo spazio dei nomi anziché i tipi corrispondenti nel <xref:System.Collections.Generic?displayProperty=fullName>e <xref:System.Collections?displayProperty=fullName>gli spazi dei nomi ogni volta che più thread accedono contemporaneamente alla raccolta.</xref:System.Collections?displayProperty=fullName> </xref:System.Collections.Generic?displayProperty=fullName> </xref:System.Collections.Concurrent></span><span class="sxs-lookup"><span data-stu-id="d528d-172">The classes in the <xref:System.Collections.Concurrent> namespace should be used instead of the corresponding types in the <xref:System.Collections.Generic?displayProperty=fullName> and <xref:System.Collections?displayProperty=fullName> namespaces whenever multiple threads are accessing the collection concurrently.</span></span> <span data-ttu-id="d528d-173">Per ulteriori informazioni, vedere [raccolte Thread-Safe](../../../standard/collections/threadsafe/index.md) e <xref:System.Collections.Concurrent>.</xref:System.Collections.Concurrent></span><span class="sxs-lookup"><span data-stu-id="d528d-173">For more information, see [Thread-Safe Collections](../../../standard/collections/threadsafe/index.md) and <xref:System.Collections.Concurrent>.</span></span>  
  
 <span data-ttu-id="d528d-174">Alcune classi incluse nel <xref:System.Collections.Concurrent>dello spazio dei nomi sono <xref:System.Collections.Concurrent.BlockingCollection%601>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602>, <xref:System.Collections.Concurrent.ConcurrentQueue%601>e <xref:System.Collections.Concurrent.ConcurrentStack%601>.</xref:System.Collections.Concurrent.ConcurrentStack%601> </xref:System.Collections.Concurrent.ConcurrentQueue%601> </xref:System.Collections.Concurrent.ConcurrentDictionary%602> </xref:System.Collections.Concurrent.BlockingCollection%601> </xref:System.Collections.Concurrent></span><span class="sxs-lookup"><span data-stu-id="d528d-174">Some classes included in the <xref:System.Collections.Concurrent> namespace are <xref:System.Collections.Concurrent.BlockingCollection%601>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602>, <xref:System.Collections.Concurrent.ConcurrentQueue%601>, and <xref:System.Collections.Concurrent.ConcurrentStack%601>.</span></span>  
  
<a name="BKMK_Collections"></a>
### <a name="systemcollections-classes"></a><span data-ttu-id="d528d-175">Classi System.Collections</span><span class="sxs-lookup"><span data-stu-id="d528d-175">System.Collections Classes</span></span>    
 <span data-ttu-id="d528d-176">Le classi di <xref:System.Collections?displayProperty=fullName>dello spazio dei nomi non archiviare elementi come oggetti tipizzati in modo specifico, ma come oggetti di tipo `Object`.</xref:System.Collections?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d528d-176">The classes in the <xref:System.Collections?displayProperty=fullName> namespace do not store elements as specifically typed objects, but as objects of type `Object`.</span></span>  
  
 <span data-ttu-id="d528d-177">Quando possibile, utilizzare le raccolte generiche nel <xref:System.Collections.Generic?displayProperty=fullName>dello spazio dei nomi o <xref:System.Collections.Concurrent>dello spazio dei nomi anziché i tipi legacy nel `System.Collections` dello spazio dei nomi.</xref:System.Collections.Concurrent> </xref:System.Collections.Generic?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d528d-177">Whenever possible, you should use the generic collections in the <xref:System.Collections.Generic?displayProperty=fullName> namespace or the <xref:System.Collections.Concurrent> namespace instead of the legacy types in the `System.Collections` namespace.</span></span>  
  
 <span data-ttu-id="d528d-178">Nella tabella seguente sono elencate alcune delle classi utilizzate di frequente il `System.Collections` dello spazio dei nomi:</span><span class="sxs-lookup"><span data-stu-id="d528d-178">The following table lists some of the frequently used classes in the `System.Collections` namespace:</span></span>  
  
|<span data-ttu-id="d528d-179">Classe</span><span class="sxs-lookup"><span data-stu-id="d528d-179">Class</span></span>|<span data-ttu-id="d528d-180">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d528d-180">Description</span></span>|  
|---|---|  
|<span data-ttu-id="d528d-181"><xref:System.Collections.ArrayList></xref:System.Collections.ArrayList></span><span class="sxs-lookup"><span data-stu-id="d528d-181"><xref:System.Collections.ArrayList></span></span>|<span data-ttu-id="d528d-182">Rappresenta una matrice di oggetti le cui dimensioni sono incrementate in modo dinamico in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="d528d-182">Represents an array of objects whose size is dynamically increased as required.</span></span>|  
|<span data-ttu-id="d528d-183"><xref:System.Collections.Hashtable></xref:System.Collections.Hashtable></span><span class="sxs-lookup"><span data-stu-id="d528d-183"><xref:System.Collections.Hashtable></span></span>|<span data-ttu-id="d528d-184">Rappresenta una raccolta di coppie chiave/valore organizzate in base al codice hash della chiave.</span><span class="sxs-lookup"><span data-stu-id="d528d-184">Represents a collection of key/value pairs that are organized based on the hash code of the key.</span></span>|  
|<span data-ttu-id="d528d-185"><xref:System.Collections.Queue></xref:System.Collections.Queue></span><span class="sxs-lookup"><span data-stu-id="d528d-185"><xref:System.Collections.Queue></span></span>|<span data-ttu-id="d528d-186">Rappresenta una raccolta di oggetti FIFO (First-In First-Out).</span><span class="sxs-lookup"><span data-stu-id="d528d-186">Represents a first in, first out (FIFO) collection of objects.</span></span>|  
|<span data-ttu-id="d528d-187"><xref:System.Collections.Stack></xref:System.Collections.Stack></span><span class="sxs-lookup"><span data-stu-id="d528d-187"><xref:System.Collections.Stack></span></span>|<span data-ttu-id="d528d-188">Rappresenta una raccolta di oggetti LIFO (Last-In First-Out).</span><span class="sxs-lookup"><span data-stu-id="d528d-188">Represents a last in, first out (LIFO) collection of objects.</span></span>|  
  
 <span data-ttu-id="d528d-189">Il <xref:System.Collections.Specialized>dello spazio dei nomi fornisce classi di raccolte specializzate e fortemente tipizzate, ad esempio elenchi collegati e ibridi dizionari e raccolte di stringa.</xref:System.Collections.Specialized></span><span class="sxs-lookup"><span data-stu-id="d528d-189">The <xref:System.Collections.Specialized> namespace provides specialized and strongly typed collection classes, such as string-only collections and linked-list and hybrid dictionaries.</span></span>  

<a name="BKMK_VisualBasic"></a> 
###  <a name="visual-basic-collection-class"></a><span data-ttu-id="d528d-190">Classe Collection di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d528d-190">Visual Basic Collection Class</span></span>  
 <span data-ttu-id="d528d-191">È possibile utilizzare Visual Basic <xref:Microsoft.VisualBasic.Collection>di accedere a una raccolta di elementi utilizzando entrambi un indice numerico o una classe `String` chiave.</xref:Microsoft.VisualBasic.Collection></span><span class="sxs-lookup"><span data-stu-id="d528d-191">You can use the Visual Basic <xref:Microsoft.VisualBasic.Collection> class to access a collection item by using either a numeric index or a `String` key.</span></span> <span data-ttu-id="d528d-192">Per aggiungere elementi a un oggetto raccolta, è possibile specificare o non specificare una chiave.</span><span class="sxs-lookup"><span data-stu-id="d528d-192">You can add items to a collection object either with or without specifying a key.</span></span> <span data-ttu-id="d528d-193">Se si aggiunge un elemento senza una chiave, è necessario usare il relativo indice numerico per accedervi.</span><span class="sxs-lookup"><span data-stu-id="d528d-193">If you add an item without a key, you must use its numeric index to access it.</span></span>  
  
 <span data-ttu-id="d528d-194">Visual Basic `Collection` classe archivia tutti i relativi elementi come tipo `Object`, pertanto è possibile aggiungere un elemento di qualsiasi tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="d528d-194">The Visual Basic `Collection` class stores all its elements as type `Object`, so you can add an item of any data type.</span></span> <span data-ttu-id="d528d-195">Non esiste alcuna misura per impedire l'aggiunta di tipi di dati non appropriati.</span><span class="sxs-lookup"><span data-stu-id="d528d-195">There is no safeguard against inappropriate data types being added.</span></span>  
  
 <span data-ttu-id="d528d-196">Quando si utilizza Visual Basic `Collection` (classe), il primo elemento in una raccolta include un indice di 1.</span><span class="sxs-lookup"><span data-stu-id="d528d-196">When you use the Visual Basic `Collection` class, the first item in a collection has an index of 1.</span></span> <span data-ttu-id="d528d-197">Questo comportamento è diverso rispetto alle classi Collection di .NET Framework, per cui l'indice iniziale è 0.</span><span class="sxs-lookup"><span data-stu-id="d528d-197">This differs from the .NET Framework collection classes, for which the starting index is 0.</span></span>  
  
 <span data-ttu-id="d528d-198">Quando possibile, utilizzare le raccolte generiche nel <xref:System.Collections.Generic?displayProperty=fullName>dello spazio dei nomi o <xref:System.Collections.Concurrent>dello spazio dei nomi anziché Visual Basic `Collection` classe</xref:System.Collections.Concurrent> </xref:System.Collections.Generic?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d528d-198">Whenever possible, you should use the generic collections in the <xref:System.Collections.Generic?displayProperty=fullName> namespace or the <xref:System.Collections.Concurrent> namespace instead of the Visual Basic `Collection` class.</span></span>  
  
 <span data-ttu-id="d528d-199">Per ulteriori informazioni, vedere <xref:Microsoft.VisualBasic.Collection>.</xref:Microsoft.VisualBasic.Collection></span><span class="sxs-lookup"><span data-stu-id="d528d-199">For more information, see <xref:Microsoft.VisualBasic.Collection>.</span></span>  
  
<a name="BKMK_KeyValuePairs"></a>
## <a name="implementing-a-collection-of-keyvalue-pairs"></a><span data-ttu-id="d528d-200">Implementazione di una raccolta di coppie chiave/valore</span><span class="sxs-lookup"><span data-stu-id="d528d-200">Implementing a Collection of Key/Value Pairs</span></span>   
 <span data-ttu-id="d528d-201">Il <xref:System.Collections.Generic.Dictionary%602>insieme generico consente di accedere agli elementi in una raccolta utilizzando la chiave di ogni elemento.</xref:System.Collections.Generic.Dictionary%602></span><span class="sxs-lookup"><span data-stu-id="d528d-201">The <xref:System.Collections.Generic.Dictionary%602> generic collection enables you to access to elements in a collection by using the key of each element.</span></span> <span data-ttu-id="d528d-202">Ogni aggiunta al dizionario è costituita da un valore e dalla chiave associata corrispondente.</span><span class="sxs-lookup"><span data-stu-id="d528d-202">Each addition to the dictionary consists of a value and its associated key.</span></span> <span data-ttu-id="d528d-203">Il recupero di un valore tramite la relativa chiave è veloci perché la `Dictionary` classe viene implementata come una tabella hash.</span><span class="sxs-lookup"><span data-stu-id="d528d-203">Retrieving a value by using its key is fast because the `Dictionary` class is implemented as a hash table.</span></span>  
  
 <span data-ttu-id="d528d-204">Nell'esempio seguente viene creato un `Dictionary` insieme e scorrere il dizionario con un `For Each` istruzione.</span><span class="sxs-lookup"><span data-stu-id="d528d-204">The following example creates a `Dictionary` collection and iterates through the dictionary by using a `For Each` statement.</span></span>  
  
```vb  
Private Sub IterateThroughDictionary()  
    Dim elements As Dictionary(Of String, Element) = BuildDictionary()  
  
    For Each kvp As KeyValuePair(Of String, Element) In elements  
        Dim theElement As Element = kvp.Value  
  
        Console.WriteLine("key: " & kvp.Key)  
        With theElement  
            Console.WriteLine("values: " & .Symbol & " " &  
                .Name & " " & .AtomicNumber)  
        End With  
    Next  
End Sub  
  
Private Function BuildDictionary() As Dictionary(Of String, Element)  
    Dim elements As New Dictionary(Of String, Element)  
  
    AddToDictionary(elements, "K", "Potassium", 19)  
    AddToDictionary(elements, "Ca", "Calcium", 20)  
    AddToDictionary(elements, "Sc", "Scandium", 21)  
    AddToDictionary(elements, "Ti", "Titanium", 22)  
  
    Return elements  
End Function  
  
Private Sub AddToDictionary(ByVal elements As Dictionary(Of String, Element),  
ByVal symbol As String, ByVal name As String, ByVal atomicNumber As Integer)  
    Dim theElement As New Element  
  
    theElement.Symbol = symbol  
    theElement.Name = name  
    theElement.AtomicNumber = atomicNumber  
  
    elements.Add(Key:=theElement.Symbol, value:=theElement)  
End Sub  
  
Public Class Element  
    Public Property Symbol As String  
    Public Property Name As String  
    Public Property AtomicNumber As Integer  
End Class  
```  
  
 <span data-ttu-id="d528d-205">Utilizzare invece un inizializzatore di raccolta per creare il `Dictionary` raccolta, è possibile sostituire il `BuildDictionary` e `AddToDictionary` metodi con il metodo seguente.</span><span class="sxs-lookup"><span data-stu-id="d528d-205">To instead use a collection initializer to build the `Dictionary` collection, you can replace the `BuildDictionary` and `AddToDictionary` methods with the following method.</span></span>  
  
```vb  
Private Function BuildDictionary2() As Dictionary(Of String, Element)  
    Return New Dictionary(Of String, Element) From  
        {  
            {"K", New Element With  
                {.Symbol = "K", .Name = "Potassium", .AtomicNumber = 19}},  
            {"Ca", New Element With  
                {.Symbol = "Ca", .Name = "Calcium", .AtomicNumber = 20}},  
            {"Sc", New Element With  
                {.Symbol = "Sc", .Name = "Scandium", .AtomicNumber = 21}},  
            {"Ti", New Element With  
                {.Symbol = "Ti", .Name = "Titanium", .AtomicNumber = 22}}  
        }  
End Function  
```  
  
 <span data-ttu-id="d528d-206">Nell'esempio seguente viene utilizzato il <xref:System.Collections.Generic.Dictionary%602.ContainsKey%2A>(metodo) e <xref:System.Collections.Generic.Dictionary%602.Item%2A>proprietà di `Dictionary` per trovare rapidamente un elemento dalla chiave.</xref:System.Collections.Generic.Dictionary%602.Item%2A> </xref:System.Collections.Generic.Dictionary%602.ContainsKey%2A></span><span class="sxs-lookup"><span data-stu-id="d528d-206">The following example uses the <xref:System.Collections.Generic.Dictionary%602.ContainsKey%2A> method and the <xref:System.Collections.Generic.Dictionary%602.Item%2A> property of `Dictionary` to quickly find an item by key.</span></span> <span data-ttu-id="d528d-207">Il `Item` proprietà consente di accedere a un elemento di `elements` raccolta utilizzando il `elements(symbol)` codice in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d528d-207">The `Item` property enables you to access an item in the `elements` collection by using the `elements(symbol)` code in Visual Basic.</span></span>  
  
```vb  
Private Sub FindInDictionary(ByVal symbol As String)  
    Dim elements As Dictionary(Of String, Element) = BuildDictionary()  
  
    If elements.ContainsKey(symbol) = False Then  
        Console.WriteLine(symbol & " not found")  
    Else  
        Dim theElement = elements(symbol)  
        Console.WriteLine("found: " & theElement.Name)  
    End If  
End Sub  
```  
  
 <span data-ttu-id="d528d-208">Nell'esempio seguente utilizza invece il <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A>metodo per trovare rapidamente un elemento chiave.</xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A></span><span class="sxs-lookup"><span data-stu-id="d528d-208">The following example instead uses the <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A> method quickly find an item by key.</span></span>  
  
```vb  
Private Sub FindInDictionary2(ByVal symbol As String)  
    Dim elements As Dictionary(Of String, Element) = BuildDictionary()  
  
    Dim theElement As Element = Nothing  
    If elements.TryGetValue(symbol, theElement) = False Then  
        Console.WriteLine(symbol & " not found")  
    Else  
        Console.WriteLine("found: " & theElement.Name)  
    End If  
End Sub  
```  
  
<a name="BKMK_LINQ"></a> 
##  <a name="using-linq-to-access-a-collection"></a><span data-ttu-id="d528d-209">Uso di LINQ per accedere a una raccolta</span><span class="sxs-lookup"><span data-stu-id="d528d-209">Using LINQ to Access a Collection</span></span>  
 <span data-ttu-id="d528d-210">È possibile usare LINQ (Language-Integrated Query) per accedere alle raccolte.</span><span class="sxs-lookup"><span data-stu-id="d528d-210">LINQ (Language-Integrated Query) can be used to access collections.</span></span> <span data-ttu-id="d528d-211">Le query LINQ forniscono funzionalità di filtro, ordinamento e raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="d528d-211">LINQ queries provide filtering, ordering, and grouping capabilities.</span></span> <span data-ttu-id="d528d-212">Per ulteriori informazioni, vedere [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md).</span><span class="sxs-lookup"><span data-stu-id="d528d-212">For more information, see [Getting Started with LINQ in Visual Basic](../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md).</span></span>  
  
 <span data-ttu-id="d528d-213">Nell'esempio seguente esegue una query LINQ rispetto generico `List`.</span><span class="sxs-lookup"><span data-stu-id="d528d-213">The following example runs a LINQ query against a generic `List`.</span></span> <span data-ttu-id="d528d-214">La query LINQ restituisce una raccolta diversa che contiene i risultati.</span><span class="sxs-lookup"><span data-stu-id="d528d-214">The LINQ query returns a different collection that contains the results.</span></span>  
  
```vb  
Private Sub ShowLINQ()  
    Dim elements As List(Of Element) = BuildList()  
  
    ' LINQ Query.  
    Dim subset = From theElement In elements  
                  Where theElement.AtomicNumber < 22  
                  Order By theElement.Name  
  
    For Each theElement In subset  
        Console.WriteLine(theElement.Name & " " & theElement.AtomicNumber)  
    Next  
  
    ' Output:  
    '  Calcium 20  
    '  Potassium 19  
    '  Scandium 21  
End Sub  
  
Private Function BuildList() As List(Of Element)  
    Return New List(Of Element) From  
        {  
            {New Element With  
                {.Symbol = "K", .Name = "Potassium", .AtomicNumber = 19}},  
            {New Element With  
                {.Symbol = "Ca", .Name = "Calcium", .AtomicNumber = 20}},  
            {New Element With  
                {.Symbol = "Sc", .Name = "Scandium", .AtomicNumber = 21}},  
            {New Element With  
                {.Symbol = "Ti", .Name = "Titanium", .AtomicNumber = 22}}  
        }  
End Function  
  
Public Class Element  
    Public Property Symbol As String  
    Public Property Name As String  
    Public Property AtomicNumber As Integer  
End Class  
```  
  
 <a name="BKMK_Sorting"></a> 
## <a name="sorting-a-collection"></a><span data-ttu-id="d528d-215">Ordinamento di una raccolta</span><span class="sxs-lookup"><span data-stu-id="d528d-215">Sorting a Collection</span></span>  
 <span data-ttu-id="d528d-216">L'esempio seguente illustra una procedura per ordinare una raccolta.</span><span class="sxs-lookup"><span data-stu-id="d528d-216">The following example illustrates a procedure for sorting a collection.</span></span> <span data-ttu-id="d528d-217">Nell'esempio consente di ordinare le istanze di `Car` (classe) che vengono archiviati in un <xref:System.Collections.Generic.List%601>.</xref:System.Collections.Generic.List%601></span><span class="sxs-lookup"><span data-stu-id="d528d-217">The example sorts instances of the `Car` class that are stored in a <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="d528d-218">Il `Car` implementa il <xref:System.IComparable%601>interfaccia, che è necessario che il <xref:System.IComparable%601.CompareTo%2A>metodo essere implementato.</xref:System.IComparable%601.CompareTo%2A> </xref:System.IComparable%601></span><span class="sxs-lookup"><span data-stu-id="d528d-218">The `Car` class implements the <xref:System.IComparable%601> interface, which requires that the <xref:System.IComparable%601.CompareTo%2A> method be implemented.</span></span>  
  
 <span data-ttu-id="d528d-219">Ogni chiamata al <xref:System.IComparable%601.CompareTo%2A>metodo effettua un confronto singolo che viene utilizzato per l'ordinamento.</xref:System.IComparable%601.CompareTo%2A></span><span class="sxs-lookup"><span data-stu-id="d528d-219">Each call to the <xref:System.IComparable%601.CompareTo%2A> method makes a single comparison that is used for sorting.</span></span> <span data-ttu-id="d528d-220">Codice scritto dall'utente di `CompareTo` metodo restituisce un valore per ogni confronto dell'oggetto corrente con un altro oggetto.</span><span class="sxs-lookup"><span data-stu-id="d528d-220">User-written code in the `CompareTo` method returns a value for each comparison of the current object with another object.</span></span> <span data-ttu-id="d528d-221">Il valore restituito è minore di zero se l'oggetto corrente è inferiore all'altro oggetto, maggiore di zero se l'oggetto corrente è superiore all'altro oggetto e zero se sono uguali.</span><span class="sxs-lookup"><span data-stu-id="d528d-221">The value returned is less than zero if the current object is less than the other object, greater than zero if the current object is greater than the other object, and zero if they are equal.</span></span> <span data-ttu-id="d528d-222">In questo modo è possibile definire nel codice i criteri di maggiore, minore e uguale.</span><span class="sxs-lookup"><span data-stu-id="d528d-222">This enables you to define in code the criteria for greater than, less than, and equal.</span></span>  
  
 <span data-ttu-id="d528d-223">Nel `ListCars` (metodo), il `cars.Sort()` istruzione Ordina l'elenco.</span><span class="sxs-lookup"><span data-stu-id="d528d-223">In the `ListCars` method, the `cars.Sort()` statement sorts the list.</span></span> <span data-ttu-id="d528d-224">Questa chiamata al <xref:System.Collections.Generic.List%601.Sort%2A>metodo il <xref:System.Collections.Generic.List%601>fa sì che il `CompareTo` metodo da chiamare automaticamente per il `Car` gli oggetti il `List`.</xref:System.Collections.Generic.List%601> </xref:System.Collections.Generic.List%601.Sort%2A></span><span class="sxs-lookup"><span data-stu-id="d528d-224">This call to the <xref:System.Collections.Generic.List%601.Sort%2A> method of the <xref:System.Collections.Generic.List%601> causes the `CompareTo` method to be called automatically for the `Car` objects in the `List`.</span></span>  
  
```vb  
Public Sub ListCars()  
  
    ' Create some new cars.  
    Dim cars As New List(Of Car) From  
    {  
        New Car With {.Name = "car1", .Color = "blue", .Speed = 20},  
        New Car With {.Name = "car2", .Color = "red", .Speed = 50},  
        New Car With {.Name = "car3", .Color = "green", .Speed = 10},  
        New Car With {.Name = "car4", .Color = "blue", .Speed = 50},  
        New Car With {.Name = "car5", .Color = "blue", .Speed = 30},  
        New Car With {.Name = "car6", .Color = "red", .Speed = 60},  
        New Car With {.Name = "car7", .Color = "green", .Speed = 50}  
    }  
  
    ' Sort the cars by color alphabetically, and then by speed  
    ' in descending order.  
    cars.Sort()  
  
    ' View all of the cars.  
    For Each thisCar As Car In cars  
        Console.Write(thisCar.Color.PadRight(5) & " ")  
        Console.Write(thisCar.Speed.ToString & " ")  
        Console.Write(thisCar.Name)  
        Console.WriteLine()  
    Next  
  
    ' Output:  
    '  blue  50 car4  
    '  blue  30 car5  
    '  blue  20 car1  
    '  green 50 car7  
    '  green 10 car3  
    '  red   60 car6  
    '  red   50 car2  
End Sub  
  
Public Class Car  
    Implements IComparable(Of Car)  
  
    Public Property Name As String  
    Public Property Speed As Integer  
    Public Property Color As String  
  
    Public Function CompareTo(ByVal other As Car) As Integer _  
        Implements System.IComparable(Of Car).CompareTo  
        ' A call to this method makes a single comparison that is  
        ' used for sorting.  
  
        ' Determine the relative order of the objects being compared.  
        ' Sort by color alphabetically, and then by speed in  
        ' descending order.  
  
        ' Compare the colors.  
        Dim compare As Integer  
        compare = String.Compare(Me.Color, other.Color, True)  
  
        ' If the colors are the same, compare the speeds.  
        If compare = 0 Then  
            compare = Me.Speed.CompareTo(other.Speed)  
  
            ' Use descending order for speed.  
            compare = -compare  
        End If  
  
        Return compare  
    End Function  
End Class  
```  
  
<a name="BKMK_CustomCollection"></a> 
## <a name="defining-a-custom-collection"></a><span data-ttu-id="d528d-225">Definizione di una raccolta personalizzata</span><span class="sxs-lookup"><span data-stu-id="d528d-225">Defining a Custom Collection</span></span>  
 <span data-ttu-id="d528d-226">È possibile definire una raccolta mediante l'implementazione di <xref:System.Collections.Generic.IEnumerable%601>o <xref:System.Collections.IEnumerable>interfaccia.</xref:System.Collections.IEnumerable> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="d528d-226">You can define a collection by implementing the <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Collections.IEnumerable> interface.</span></span> <span data-ttu-id="d528d-227">Per ulteriori informazioni, vedere [enumerando una raccolta di](http://msdn.microsoft.com/en-us/71807ea7-9180-48a6-916f-35a5251d477f).</span><span class="sxs-lookup"><span data-stu-id="d528d-227">For additional information, see [Enumerating a Collection](http://msdn.microsoft.com/en-us/71807ea7-9180-48a6-916f-35a5251d477f).</span></span>  
  
 <span data-ttu-id="d528d-228">Sebbene sia possibile definire un insieme personalizzato, è preferibile utilizzare invece le raccolte che vengono inclusi in .NET Framework, che sono descritti in [tipi di raccolte](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b) precedentemente in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d528d-228">Although you can define a custom collection, it is usually better to instead use the collections that are included in the .NET Framework, which are described in [Kinds of Collections](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b) earlier in this topic.</span></span>  
  
 <span data-ttu-id="d528d-229">Nell'esempio seguente viene definita una classe di raccolta personalizzato denominata `AllColors`.</span><span class="sxs-lookup"><span data-stu-id="d528d-229">The following example defines a custom collection class named `AllColors`.</span></span> <span data-ttu-id="d528d-230">Questa classe implementa il <xref:System.Collections.IEnumerable>interfaccia, che è necessario che il <xref:System.Collections.IEnumerable.GetEnumerator%2A>metodo essere implementato.</xref:System.Collections.IEnumerable.GetEnumerator%2A> </xref:System.Collections.IEnumerable></span><span class="sxs-lookup"><span data-stu-id="d528d-230">This class implements the <xref:System.Collections.IEnumerable> interface, which requires that the <xref:System.Collections.IEnumerable.GetEnumerator%2A> method be implemented.</span></span>  
  
 <span data-ttu-id="d528d-231">Il `GetEnumerator` metodo restituisce un'istanza di `ColorEnumerator` (classe).</span><span class="sxs-lookup"><span data-stu-id="d528d-231">The `GetEnumerator` method returns an instance of the `ColorEnumerator` class.</span></span> <span data-ttu-id="d528d-232">`ColorEnumerator`implementa il <xref:System.Collections.IEnumerator>interfaccia, che è necessario che il <xref:System.Collections.IEnumerator.Current%2A>proprietà <xref:System.Collections.IEnumerator.MoveNext%2A>(metodo), e <xref:System.Collections.IEnumerator.Reset%2A>metodo essere implementato.</xref:System.Collections.IEnumerator.Reset%2A> </xref:System.Collections.IEnumerator.MoveNext%2A> </xref:System.Collections.IEnumerator.Current%2A> </xref:System.Collections.IEnumerator></span><span class="sxs-lookup"><span data-stu-id="d528d-232">`ColorEnumerator` implements the <xref:System.Collections.IEnumerator> interface, which requires that the <xref:System.Collections.IEnumerator.Current%2A> property, <xref:System.Collections.IEnumerator.MoveNext%2A> method, and <xref:System.Collections.IEnumerator.Reset%2A> method be implemented.</span></span>  
  
```vb  
Public Sub ListColors()  
    Dim colors As New AllColors()  
  
    For Each theColor As Color In colors  
        Console.Write(theColor.Name & " ")  
    Next  
    Console.WriteLine()  
    ' Output: red blue green  
End Sub  
  
' Collection class.  
Public Class AllColors  
    Implements System.Collections.IEnumerable  
  
    Private _colors() As Color =  
    {  
        New Color With {.Name = "red"},  
        New Color With {.Name = "blue"},  
        New Color With {.Name = "green"}  
    }  
  
    Public Function GetEnumerator() As System.Collections.IEnumerator _  
        Implements System.Collections.IEnumerable.GetEnumerator  
  
        Return New ColorEnumerator(_colors)  
  
        ' Instead of creating a custom enumerator, you could  
        ' use the GetEnumerator of the array.  
        'Return _colors.GetEnumerator  
    End Function  
  
    ' Custom enumerator.  
    Private Class ColorEnumerator  
        Implements System.Collections.IEnumerator  
  
        Private _colors() As Color  
        Private _position As Integer = -1  
  
        Public Sub New(ByVal colors() As Color)  
            _colors = colors  
        End Sub  
  
        Public ReadOnly Property Current() As Object _  
            Implements System.Collections.IEnumerator.Current  
            Get  
                Return _colors(_position)  
            End Get  
        End Property  
  
        Public Function MoveNext() As Boolean _  
            Implements System.Collections.IEnumerator.MoveNext  
            _position += 1  
            Return (_position < _colors.Length)  
        End Function  
  
        Public Sub Reset() Implements System.Collections.IEnumerator.Reset  
            _position = -1  
        End Sub  
    End Class  
End Class  
  
' Element class.  
Public Class Color  
    Public Property Name As String  
End Class  
```  
  
<a name="BKMK_Iterators"></a>
##  <a name="iterators"></a><span data-ttu-id="d528d-233">Iteratori</span><span class="sxs-lookup"><span data-stu-id="d528d-233">Iterators</span></span>  
 <span data-ttu-id="d528d-234">Un *iteratore* viene utilizzato per eseguire un'iterazione personalizzata su una raccolta.</span><span class="sxs-lookup"><span data-stu-id="d528d-234">An *iterator* is used to perform a custom iteration over a collection.</span></span> <span data-ttu-id="d528d-235">Un iteratore può essere un metodo o un `get` della funzione di accesso.</span><span class="sxs-lookup"><span data-stu-id="d528d-235">An iterator can be a method or a `get` accessor.</span></span> <span data-ttu-id="d528d-236">Un iteratore utilizza un [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) istruzione per la restituzione di ogni elemento della raccolta uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="d528d-236">An iterator uses a [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) statement to return each element of the collection one at a time.</span></span>  
  
 <span data-ttu-id="d528d-237">Viene chiamato un iteratore utilizzando un [For Each... Avanti](../../../visual-basic/language-reference/statements/for-each-next-statement.md) istruzione.</span><span class="sxs-lookup"><span data-stu-id="d528d-237">You call an iterator by using a [For Each…Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement.</span></span> <span data-ttu-id="d528d-238">Ogni iterazione del `For Each` ciclo chiama l'iteratore.</span><span class="sxs-lookup"><span data-stu-id="d528d-238">Each iteration of the `For Each` loop calls the iterator.</span></span> <span data-ttu-id="d528d-239">Quando un `Yield` viene raggiunta l'istruzione nell'iteratore, viene restituita un'espressione e viene mantenuta la posizione corrente nel codice.</span><span class="sxs-lookup"><span data-stu-id="d528d-239">When a `Yield` statement is reached in the iterator, an expression is returned, and the current location in code is retained.</span></span> <span data-ttu-id="d528d-240">L'esecuzione viene ripresa a partire da quella posizione la volta successiva che viene chiamato l'iteratore.</span><span class="sxs-lookup"><span data-stu-id="d528d-240">Execution is restarted from that location the next time that the iterator is called.</span></span>  
  
 <span data-ttu-id="d528d-241">Per ulteriori informazioni, vedere [iteratori (Visual Basic)](../../../visual-basic/programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="d528d-241">For more information, see [Iterators (Visual Basic)](../../../visual-basic/programming-guide/concepts/iterators.md).</span></span>  
  
 <span data-ttu-id="d528d-242">Nell'esempio seguente viene usato un metodo iteratore.</span><span class="sxs-lookup"><span data-stu-id="d528d-242">The following example uses an iterator method.</span></span> <span data-ttu-id="d528d-243">Il metodo iteratore è un `Yield` istruzione all'interno di un [per... Avanti](../../../visual-basic/language-reference/statements/for-next-statement.md) ciclo.</span><span class="sxs-lookup"><span data-stu-id="d528d-243">The iterator method has a `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop.</span></span> <span data-ttu-id="d528d-244">Nel `ListEvenNumbers` (metodo), ogni iterazione del `For Each` corpo dell'istruzione crea una chiamata al metodo iteratore, che consente di passare alla successiva `Yield` istruzione.</span><span class="sxs-lookup"><span data-stu-id="d528d-244">In the `ListEvenNumbers` method, each iteration of the `For Each` statement body creates a call to the iterator method, which proceeds to the next `Yield` statement.</span></span>  
  
```vb  
Public Sub ListEvenNumbers()  
    For Each number As Integer In EvenSequence(5, 18)  
        Console.Write(number & " ")  
    Next  
    Console.WriteLine()  
    ' Output: 6 8 10 12 14 16 18  
End Sub  
  
Private Iterator Function EvenSequence(  
ByVal firstNumber As Integer, ByVal lastNumber As Integer) _  
As IEnumerable(Of Integer)  
  
' Yield even numbers in the range.  
    For number = firstNumber To lastNumber  
        If number Mod 2 = 0 Then  
            Yield number  
        End If  
    Next  
End Function  
```  
  
## <a name="see-also"></a><span data-ttu-id="d528d-245">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d528d-245">See Also</span></span>  
 <span data-ttu-id="d528d-246">[Inizializzatori di insieme](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md) </span><span class="sxs-lookup"><span data-stu-id="d528d-246">[Collection Initializers](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md) </span></span>  
<span data-ttu-id="d528d-247"> [Concetti di programmazione (Visual Basic)](../../../visual-basic/programming-guide/concepts/index.md) </span><span class="sxs-lookup"><span data-stu-id="d528d-247"> [Programming Concepts (Visual Basic)](../../../visual-basic/programming-guide/concepts/index.md) </span></span>  
<span data-ttu-id="d528d-248"> [Istruzione Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) </span><span class="sxs-lookup"><span data-stu-id="d528d-248"> [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md) </span></span>  
<span data-ttu-id="d528d-249"> [LINQ to Objects (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md) </span><span class="sxs-lookup"><span data-stu-id="d528d-249"> [LINQ to Objects (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md) </span></span>  
<span data-ttu-id="d528d-250"> [Parallel LINQ (PLINQ)](http://msdn.microsoft.com/library/3d4d0cd3-bde4-490b-99e7-f4e41be96455) </span><span class="sxs-lookup"><span data-stu-id="d528d-250"> [Parallel LINQ (PLINQ)](http://msdn.microsoft.com/library/3d4d0cd3-bde4-490b-99e7-f4e41be96455) </span></span>  
<span data-ttu-id="d528d-251"> [Raccolte e strutture di dati](../../../standard/collections/index.md) </span><span class="sxs-lookup"><span data-stu-id="d528d-251"> [Collections and Data Structures](../../../standard/collections/index.md) </span></span>  
<span data-ttu-id="d528d-252"> [Creazione e modifica delle raccolte](http://msdn.microsoft.com/en-us/2065398e-eb1a-4821-9188-75f16e42e069) </span><span class="sxs-lookup"><span data-stu-id="d528d-252"> [Creating and Manipulating Collections](http://msdn.microsoft.com/en-us/2065398e-eb1a-4821-9188-75f16e42e069) </span></span>  
<span data-ttu-id="d528d-253"> [Selezione di una classe di raccolta](../../../standard/collections/selecting-a-collection-class.md) </span><span class="sxs-lookup"><span data-stu-id="d528d-253"> [Selecting a Collection Class](../../../standard/collections/selecting-a-collection-class.md) </span></span>  
<span data-ttu-id="d528d-254"> [Confronti e ordinamenti all'interno delle raccolte](../../../standard/collections/comparisons-and-sorts-within-collections.md) </span><span class="sxs-lookup"><span data-stu-id="d528d-254"> [Comparisons and Sorts Within Collections](../../../standard/collections/comparisons-and-sorts-within-collections.md) </span></span>  
<span data-ttu-id="d528d-255"> [Quando utilizzare raccolte generiche](../../../standard/collections/when-to-use-generic-collections.md)</span><span class="sxs-lookup"><span data-stu-id="d528d-255"> [When to Use Generic Collections](../../../standard/collections/when-to-use-generic-collections.md)</span></span>
