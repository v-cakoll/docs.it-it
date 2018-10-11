---
title: Raccolte (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 5f7749f3-aaf2-4319-b63c-bfa72e1e2b7a
ms.openlocfilehash: 60519de1f580bf1cfa4aa067d4a999b20ea8d54d
ms.sourcegitcommit: 2eb5ca4956231c1a0efd34b6a9cab6153a5438af
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/11/2018
ms.locfileid: "49087375"
---
# <a name="collections-visual-basic"></a><span data-ttu-id="1a91f-102">Raccolte (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1a91f-102">Collections (Visual Basic)</span></span>
<span data-ttu-id="1a91f-103">Per molte applicazioni è utile creare e gestire gruppi di oggetti correlati.</span><span class="sxs-lookup"><span data-stu-id="1a91f-103">For many applications, you want to create and manage groups of related objects.</span></span> <span data-ttu-id="1a91f-104">È possibile raggruppare gli oggetti in due modi: creando matrici di oggetti e creando raccolte di oggetti.</span><span class="sxs-lookup"><span data-stu-id="1a91f-104">There are two ways to group objects: by creating arrays of objects, and by creating collections of objects.</span></span>  
  
 <span data-ttu-id="1a91f-105">Le matrici sono estremamente utili per la creazione e l'uso di un numero fisso di oggetti fortemente tipizzati.</span><span class="sxs-lookup"><span data-stu-id="1a91f-105">Arrays are most useful for creating and working with a fixed number of strongly-typed objects.</span></span> <span data-ttu-id="1a91f-106">Per altre informazioni sulle matrici, vedere [Matrici](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="1a91f-106">For information about arrays, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
 <span data-ttu-id="1a91f-107">Le raccolte consentono di lavorare in modo più flessibile con gruppi di oggetti.</span><span class="sxs-lookup"><span data-stu-id="1a91f-107">Collections provide a more flexible way to work with groups of objects.</span></span> <span data-ttu-id="1a91f-108">A differenza delle matrici, il gruppo di oggetti con cui si lavora può aumentare e diminuire in modo dinamico in base alle esigenze dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1a91f-108">Unlike arrays, the group of objects you work with can grow and shrink dynamically as the needs of the application change.</span></span> <span data-ttu-id="1a91f-109">Per alcune raccolte è possibile assegnare una chiave a qualsiasi oggetto inserito nella raccolta in modo da recuperare rapidamente l'oggetto usando la chiave.</span><span class="sxs-lookup"><span data-stu-id="1a91f-109">For some collections, you can assign a key to any object that you put into the collection so that you can quickly retrieve the object by using the key.</span></span>  
  
 <span data-ttu-id="1a91f-110">Una raccolta è una classe. Di conseguenza, prima di poter aggiungere elementi a una nuova raccolta è necessario dichiarare la raccolta.</span><span class="sxs-lookup"><span data-stu-id="1a91f-110">A collection is a class, so you must declare an instance of the class before you can add elements to that collection.</span></span>  
  
 <span data-ttu-id="1a91f-111">Se la raccolta contiene elementi di un solo tipo di dati, è possibile usare una delle classi dello spazio dei nomi <xref:System.Collections.Generic?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1a91f-111">If your collection contains elements of only one data type, you can use one of the classes in the <xref:System.Collections.Generic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="1a91f-112">In una raccolta generica viene imposta l'indipendenza dai tipi, in modo da impedire che vengano aggiunti altri tipi di dati alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="1a91f-112">A generic collection enforces type safety so that no other data type can be added to it.</span></span> <span data-ttu-id="1a91f-113">Quando si recupera un elemento da una raccolta generica, non è necessario determinarne il tipo di dati né convertirlo.</span><span class="sxs-lookup"><span data-stu-id="1a91f-113">When you retrieve an element from a generic collection, you do not have to determine its data type or convert it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1a91f-114">Per gli esempi in questo argomento, includere [importazioni](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) istruzioni per il `System.Collections.Generic` e `System.Linq` gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="1a91f-114">For the examples in this topic, include [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) statements for the `System.Collections.Generic` and `System.Linq` namespaces.</span></span>  
  
 <span data-ttu-id="1a91f-115">**In questo argomento**</span><span class="sxs-lookup"><span data-stu-id="1a91f-115">**In this topic**</span></span>  
  
-   [<span data-ttu-id="1a91f-116">Uso di una raccolta semplice</span><span class="sxs-lookup"><span data-stu-id="1a91f-116">Using a Simple Collection</span></span>](#BKMK_SimpleCollection)  
  
-   [<span data-ttu-id="1a91f-117">Tipi di raccolte</span><span class="sxs-lookup"><span data-stu-id="1a91f-117">Kinds of Collections</span></span>](#BKMK_KindsOfCollections)  
  
    -   [<span data-ttu-id="1a91f-118">Classi System.Collections.Generic</span><span class="sxs-lookup"><span data-stu-id="1a91f-118">System.Collections.Generic Classes</span></span>](#BKMK_Generic)  
  
    -   [<span data-ttu-id="1a91f-119">Classi System.Collections.Concurrent</span><span class="sxs-lookup"><span data-stu-id="1a91f-119">System.Collections.Concurrent Classes</span></span>](#BKMK_Concurrent)  
  
    -   [<span data-ttu-id="1a91f-120">Classi System.Collections</span><span class="sxs-lookup"><span data-stu-id="1a91f-120">System.Collections Classes</span></span>](#BKMK_Collections)  
  
    -   [<span data-ttu-id="1a91f-121">Classe Collection di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1a91f-121">Visual Basic Collection Class</span></span>](#BKMK_VisualBasic)  
  
-   [<span data-ttu-id="1a91f-122">Implementazione di una raccolta di coppie chiave/valore</span><span class="sxs-lookup"><span data-stu-id="1a91f-122">Implementing a Collection of Key/Value Pairs</span></span>](#BKMK_KeyValuePairs)  
  
-   [<span data-ttu-id="1a91f-123">Uso di LINQ per accedere a una raccolta</span><span class="sxs-lookup"><span data-stu-id="1a91f-123">Using LINQ to Access a Collection</span></span>](#BKMK_LINQ)  
  
-   [<span data-ttu-id="1a91f-124">Ordinamento di una raccolta</span><span class="sxs-lookup"><span data-stu-id="1a91f-124">Sorting a Collection</span></span>](#BKMK_Sorting)  
  
-   [<span data-ttu-id="1a91f-125">Definizione di una raccolta personalizzata</span><span class="sxs-lookup"><span data-stu-id="1a91f-125">Defining a Custom Collection</span></span>](#BKMK_CustomCollection)  
  
-   [<span data-ttu-id="1a91f-126">Iteratori</span><span class="sxs-lookup"><span data-stu-id="1a91f-126">Iterators</span></span>](#BKMK_Iterators)  
  
<a name="BKMK_SimpleCollection"></a>
## <a name="using-a-simple-collection"></a><span data-ttu-id="1a91f-127">Uso di una raccolta semplice</span><span class="sxs-lookup"><span data-stu-id="1a91f-127">Using a Simple Collection</span></span>  
 <span data-ttu-id="1a91f-128">Gli esempi in questa sezione usano la classe generica <xref:System.Collections.Generic.List%601>, che consente di usare un elenco di oggetti fortemente tipizzato.</span><span class="sxs-lookup"><span data-stu-id="1a91f-128">The examples in this section use the generic <xref:System.Collections.Generic.List%601> class, which enables you to work with a strongly typed list of objects.</span></span>  
  
 <span data-ttu-id="1a91f-129">Nell'esempio seguente crea un elenco di stringhe e quindi scorrere le stringhe usando una [For Each... Avanti](../../../visual-basic/language-reference/statements/for-each-next-statement.md) istruzione.</span><span class="sxs-lookup"><span data-stu-id="1a91f-129">The following example creates a list of strings and then iterates through the strings by using a [For Each…Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement.</span></span>  
  
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
  
 <span data-ttu-id="1a91f-130">Se il contenuto di una raccolta è noto in anticipo, si può usare un *inizializzatore di raccolta* per inizializzare la raccolta.</span><span class="sxs-lookup"><span data-stu-id="1a91f-130">If the contents of a collection are known in advance, you can use a *collection initializer* to initialize the collection.</span></span> <span data-ttu-id="1a91f-131">Per altre informazioni, vedere [Inizializzatori di insieme](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).</span><span class="sxs-lookup"><span data-stu-id="1a91f-131">For more information, see [Collection Initializers](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).</span></span>  
  
 <span data-ttu-id="1a91f-132">L'esempio seguente è identico all'esempio precedente, ma usa un inizializzatore di raccolta per aggiungere elementi alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="1a91f-132">The following example is the same as the previous example, except a collection initializer is used to add elements to the collection.</span></span>  
  
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
  
 <span data-ttu-id="1a91f-133">È possibile usare un [per... Prossima](../../../visual-basic/language-reference/statements/for-next-statement.md) istruzione anziché un `For Each` per scorrere una raccolta.</span><span class="sxs-lookup"><span data-stu-id="1a91f-133">You can use a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) statement instead of a `For Each` statement to iterate through a collection.</span></span> <span data-ttu-id="1a91f-134">Questo è possibile mediante l'accesso agli elementi della raccolta dalla posizione di indice.</span><span class="sxs-lookup"><span data-stu-id="1a91f-134">You accomplish this by accessing the collection elements by the index position.</span></span> <span data-ttu-id="1a91f-135">L'indice degli elementi inizia da 0 e termina in corrispondenza del numero di elementi meno 1.</span><span class="sxs-lookup"><span data-stu-id="1a91f-135">The index of the elements starts at 0 and ends at the element count minus 1.</span></span>  
  
 <span data-ttu-id="1a91f-136">Nell'esempio seguente l'iterazione negli elementi di una raccolta avviene mediante `For…Next` anziché mediante `For Each`.</span><span class="sxs-lookup"><span data-stu-id="1a91f-136">The following example iterates through the elements of a collection by using `For…Next` instead of `For Each`.</span></span>  
  
```vb  
Dim salmons As New List(Of String) From  
    {"chinook", "coho", "pink", "sockeye"}  
  
For index = 0 To salmons.Count - 1  
    Console.Write(salmons(index) & " ")  
Next  
'Output: chinook coho pink sockeye  
```  
  
 <span data-ttu-id="1a91f-137">Nell'esempio seguente viene rimosso un elemento dalla raccolta specificando l'oggetto da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="1a91f-137">The following example removes an element from the collection by specifying the object to remove.</span></span>  
  
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
  
 <span data-ttu-id="1a91f-138">Nell'esempio seguente vengono rimossi elementi da un elenco generico.</span><span class="sxs-lookup"><span data-stu-id="1a91f-138">The following example removes elements from a generic list.</span></span> <span data-ttu-id="1a91f-139">Invece di un `For Each` istruzione, una [per... Avanti](../../../visual-basic/language-reference/statements/for-next-statement.md) viene utilizzata l'istruzione che esegue l'iterazione in ordine decrescente.</span><span class="sxs-lookup"><span data-stu-id="1a91f-139">Instead of a `For Each` statement, a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) statement that iterates in descending order is used.</span></span> <span data-ttu-id="1a91f-140">Ciò è necessario perché il metodo <xref:System.Collections.Generic.List%601.RemoveAt%2A> fa sì che gli elementi dopo un elemento rimosso abbiano un valore di indice inferiore.</span><span class="sxs-lookup"><span data-stu-id="1a91f-140">This is because the <xref:System.Collections.Generic.List%601.RemoveAt%2A> method causes elements after a removed element to have a lower index value.</span></span>  
  
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
  
 <span data-ttu-id="1a91f-141">Per il tipo di elementi in <xref:System.Collections.Generic.List%601>, è possibile anche definire una classe personalizzata.</span><span class="sxs-lookup"><span data-stu-id="1a91f-141">For the type of elements in the <xref:System.Collections.Generic.List%601>, you can also define your own class.</span></span> <span data-ttu-id="1a91f-142">Nell'esempio seguente la classe `Galaxy` viene usata dall'oggetto <xref:System.Collections.Generic.List%601> definito nel codice.</span><span class="sxs-lookup"><span data-stu-id="1a91f-142">In the following example, the `Galaxy` class that is used by the <xref:System.Collections.Generic.List%601> is defined in the code.</span></span>  
  
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
## <a name="kinds-of-collections"></a><span data-ttu-id="1a91f-143">Tipi di raccolte</span><span class="sxs-lookup"><span data-stu-id="1a91f-143">Kinds of Collections</span></span>   
 <span data-ttu-id="1a91f-144">Molte raccolte comuni vengono fornite da .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1a91f-144">Many common collections are provided by the .NET Framework.</span></span> <span data-ttu-id="1a91f-145">Ogni tipo di raccolta è progettato per uno scopo specifico.</span><span class="sxs-lookup"><span data-stu-id="1a91f-145">Each type of collection is designed for a specific purpose.</span></span>  
  
 <span data-ttu-id="1a91f-146">In questa sezione sono descritte alcune classi di raccolte comuni:</span><span class="sxs-lookup"><span data-stu-id="1a91f-146">Some of the common collection classes are described in this section:</span></span>  
  
-   <span data-ttu-id="1a91f-147">Classi <xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="1a91f-147"><xref:System.Collections.Generic> classes</span></span>  
  
-   <span data-ttu-id="1a91f-148">Classi <xref:System.Collections.Concurrent></span><span class="sxs-lookup"><span data-stu-id="1a91f-148"><xref:System.Collections.Concurrent> classes</span></span>  
  
-   <span data-ttu-id="1a91f-149">Classi <xref:System.Collections></span><span class="sxs-lookup"><span data-stu-id="1a91f-149"><xref:System.Collections> classes</span></span>  
  
-   <span data-ttu-id="1a91f-150">Classe `Collection` di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1a91f-150">Visual Basic `Collection` class</span></span>  
  
<a name="BKMK_Generic"></a>
### <a name="systemcollectionsgeneric-classes"></a><span data-ttu-id="1a91f-151">Classi System.Collections.Generic</span><span class="sxs-lookup"><span data-stu-id="1a91f-151">System.Collections.Generic Classes</span></span>  

 <span data-ttu-id="1a91f-152">È possibile creare una raccolta generica usando una delle classi dello spazio dei nomi <xref:System.Collections.Generic>.</span><span class="sxs-lookup"><span data-stu-id="1a91f-152">You can create a generic collection by using one of the classes in the <xref:System.Collections.Generic> namespace.</span></span> <span data-ttu-id="1a91f-153">Una raccolta generica è utile quando ogni elemento al suo interno presenta lo stesso tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="1a91f-153">A generic collection is useful when every item in the collection has the same data type.</span></span> <span data-ttu-id="1a91f-154">Una raccolta generica applica la tipizzazione forte consentendo di aggiungere soltanto i tipi di dati desiderati.</span><span class="sxs-lookup"><span data-stu-id="1a91f-154">A generic collection enforces strong typing by allowing only the desired data type to be added.</span></span>  
  
 <span data-ttu-id="1a91f-155">La tabella seguente elenca alcune delle classi di uso frequente dello spazio dei nomi <xref:System.Collections.Generic?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="1a91f-155">The following table lists some of the frequently used classes of the <xref:System.Collections.Generic?displayProperty=nameWithType> namespace:</span></span>  
  
|<span data-ttu-id="1a91f-156">Classe</span><span class="sxs-lookup"><span data-stu-id="1a91f-156">Class</span></span>|<span data-ttu-id="1a91f-157">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1a91f-157">Description</span></span>|  
|---|---|  
|<xref:System.Collections.Generic.Dictionary%602>|<span data-ttu-id="1a91f-158">Rappresenta una raccolta di coppie chiave/valore organizzate in base alla chiave.</span><span class="sxs-lookup"><span data-stu-id="1a91f-158">Represents a collection of key/value pairs that are organized based on the key.</span></span>|  
|<xref:System.Collections.Generic.List%601>|<span data-ttu-id="1a91f-159">Rappresenta un elenco di oggetti accessibile in base all'indice.</span><span class="sxs-lookup"><span data-stu-id="1a91f-159">Represents a list of objects that can be accessed by index.</span></span> <span data-ttu-id="1a91f-160">Fornisce metodi per la ricerca, l'ordinamento e la modifica degli elenchi.</span><span class="sxs-lookup"><span data-stu-id="1a91f-160">Provides methods to search, sort, and modify lists.</span></span>|  
|<xref:System.Collections.Generic.Queue%601>|<span data-ttu-id="1a91f-161">Rappresenta una raccolta di oggetti FIFO (First-In First-Out).</span><span class="sxs-lookup"><span data-stu-id="1a91f-161">Represents a first in, first out (FIFO) collection of objects.</span></span>|  
|<xref:System.Collections.Generic.SortedList%602>|<span data-ttu-id="1a91f-162">Rappresenta una raccolta di coppie chiave/valore ordinate per chiave in base all'implementazione <xref:System.Collections.Generic.IComparer%601> associata.</span><span class="sxs-lookup"><span data-stu-id="1a91f-162">Represents a collection of key/value pairs that are sorted by key based on the associated <xref:System.Collections.Generic.IComparer%601> implementation.</span></span>|  
|<xref:System.Collections.Generic.Stack%601>|<span data-ttu-id="1a91f-163">Rappresenta una raccolta di oggetti LIFO (Last-In First-Out).</span><span class="sxs-lookup"><span data-stu-id="1a91f-163">Represents a last in, first out (LIFO) collection of objects.</span></span>|  
  
 <span data-ttu-id="1a91f-164">Per altre informazioni, vedere [Tipi di raccolte comunemente utilizzate](../../../standard/collections/commonly-used-collection-types.md), [Selezione di una classe Collection](../../../standard/collections/selecting-a-collection-class.md) e <xref:System.Collections.Generic?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1a91f-164">For additional information, see [Commonly Used Collection Types](../../../standard/collections/commonly-used-collection-types.md), [Selecting a Collection Class](../../../standard/collections/selecting-a-collection-class.md), and <xref:System.Collections.Generic?displayProperty=nameWithType>.</span></span>  
  
<a name="BKMK_Concurrent"></a>
### <a name="systemcollectionsconcurrent-classes"></a><span data-ttu-id="1a91f-165">Classi System.Collections.Concurrent</span><span class="sxs-lookup"><span data-stu-id="1a91f-165">System.Collections.Concurrent Classes</span></span>   
 <span data-ttu-id="1a91f-166">In .NET Framework 4 o versioni successive le raccolte dello spazio dei nomi <xref:System.Collections.Concurrent> garantiscono operazioni thread-safe efficienti per accedere agli elementi della raccolta da più thread.</span><span class="sxs-lookup"><span data-stu-id="1a91f-166">In the .NET Framework 4 or newer, the collections in the <xref:System.Collections.Concurrent> namespace provide efficient thread-safe operations for accessing collection items from multiple threads.</span></span>  
  
 <span data-ttu-id="1a91f-167">Le classi dello spazio dei nomi <xref:System.Collections.Concurrent> devono essere usate in sostituzione dei tipi corrispondenti negli spazi dei nomi <xref:System.Collections.Generic?displayProperty=nameWithType> e <xref:System.Collections?displayProperty=nameWithType> ogni volta che più thread accedono contemporaneamente alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="1a91f-167">The classes in the <xref:System.Collections.Concurrent> namespace should be used instead of the corresponding types in the <xref:System.Collections.Generic?displayProperty=nameWithType> and <xref:System.Collections?displayProperty=nameWithType> namespaces whenever multiple threads are accessing the collection concurrently.</span></span> <span data-ttu-id="1a91f-168">Per altre informazioni, vedere [Raccolte thread-safe](../../../standard/collections/thread-safe/index.md) e <xref:System.Collections.Concurrent>.</span><span class="sxs-lookup"><span data-stu-id="1a91f-168">For more information, see [Thread-Safe Collections](../../../standard/collections/thread-safe/index.md) and <xref:System.Collections.Concurrent>.</span></span>  
  
 <span data-ttu-id="1a91f-169">Alcune classi incluse nello spazio dei nomi <xref:System.Collections.Concurrent> sono <xref:System.Collections.Concurrent.BlockingCollection%601>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602>, <xref:System.Collections.Concurrent.ConcurrentQueue%601> e <xref:System.Collections.Concurrent.ConcurrentStack%601>.</span><span class="sxs-lookup"><span data-stu-id="1a91f-169">Some classes included in the <xref:System.Collections.Concurrent> namespace are <xref:System.Collections.Concurrent.BlockingCollection%601>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602>, <xref:System.Collections.Concurrent.ConcurrentQueue%601>, and <xref:System.Collections.Concurrent.ConcurrentStack%601>.</span></span>  
  
<a name="BKMK_Collections"></a>
### <a name="systemcollections-classes"></a><span data-ttu-id="1a91f-170">Classi System.Collections</span><span class="sxs-lookup"><span data-stu-id="1a91f-170">System.Collections Classes</span></span>    
 <span data-ttu-id="1a91f-171">Le classi dello spazio dei nomi <xref:System.Collections?displayProperty=nameWithType> non archiviano gli elementi come oggetti tipizzati in modo specifico, ma come oggetti di tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="1a91f-171">The classes in the <xref:System.Collections?displayProperty=nameWithType> namespace do not store elements as specifically typed objects, but as objects of type `Object`.</span></span>  
  
 <span data-ttu-id="1a91f-172">Quando possibile, usare le raccolte generiche degli spazi dei nomi <xref:System.Collections.Generic?displayProperty=nameWithType> o <xref:System.Collections.Concurrent> al posto dei tipi legacy dello spazio dei nomi `System.Collections`.</span><span class="sxs-lookup"><span data-stu-id="1a91f-172">Whenever possible, you should use the generic collections in the <xref:System.Collections.Generic?displayProperty=nameWithType> namespace or the <xref:System.Collections.Concurrent> namespace instead of the legacy types in the `System.Collections` namespace.</span></span>  
  
 <span data-ttu-id="1a91f-173">La tabella seguente elenca alcune classi di uso frequente nello spazio dei nomi `System.Collections`:</span><span class="sxs-lookup"><span data-stu-id="1a91f-173">The following table lists some of the frequently used classes in the `System.Collections` namespace:</span></span>  
  
|<span data-ttu-id="1a91f-174">Classe</span><span class="sxs-lookup"><span data-stu-id="1a91f-174">Class</span></span>|<span data-ttu-id="1a91f-175">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1a91f-175">Description</span></span>|  
|---|---|  
|<xref:System.Collections.ArrayList>|<span data-ttu-id="1a91f-176">Rappresenta una matrice di oggetti le cui dimensioni sono incrementate in modo dinamico in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="1a91f-176">Represents an array of objects whose size is dynamically increased as required.</span></span>|  
|<xref:System.Collections.Hashtable>|<span data-ttu-id="1a91f-177">Rappresenta una raccolta di coppie chiave/valore organizzate in base al codice hash della chiave.</span><span class="sxs-lookup"><span data-stu-id="1a91f-177">Represents a collection of key/value pairs that are organized based on the hash code of the key.</span></span>|  
|<xref:System.Collections.Queue>|<span data-ttu-id="1a91f-178">Rappresenta una raccolta di oggetti FIFO (First-In First-Out).</span><span class="sxs-lookup"><span data-stu-id="1a91f-178">Represents a first in, first out (FIFO) collection of objects.</span></span>|  
|<xref:System.Collections.Stack>|<span data-ttu-id="1a91f-179">Rappresenta una raccolta di oggetti LIFO (Last-In First-Out).</span><span class="sxs-lookup"><span data-stu-id="1a91f-179">Represents a last in, first out (LIFO) collection of objects.</span></span>|  
  
 <span data-ttu-id="1a91f-180">Lo spazio dei nomi <xref:System.Collections.Specialized> fornisce classi di raccolta fortemente tipizzate e specializzate, ad esempio raccolte di sole stringhe e dizionari ibridi ed elenchi collegati.</span><span class="sxs-lookup"><span data-stu-id="1a91f-180">The <xref:System.Collections.Specialized> namespace provides specialized and strongly typed collection classes, such as string-only collections and linked-list and hybrid dictionaries.</span></span>  

<a name="BKMK_VisualBasic"></a> 
###  <a name="visual-basic-collection-class"></a><span data-ttu-id="1a91f-181">Classe Collection di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1a91f-181">Visual Basic Collection Class</span></span>  
 <span data-ttu-id="1a91f-182">È possibile usare la classe <xref:Microsoft.VisualBasic.Collection> di Visual Basic per accedere a un elemento della raccolta usando un indice numerico o una chiave `String`.</span><span class="sxs-lookup"><span data-stu-id="1a91f-182">You can use the Visual Basic <xref:Microsoft.VisualBasic.Collection> class to access a collection item by using either a numeric index or a `String` key.</span></span> <span data-ttu-id="1a91f-183">Per aggiungere elementi a un oggetto raccolta, è possibile specificare o non specificare una chiave.</span><span class="sxs-lookup"><span data-stu-id="1a91f-183">You can add items to a collection object either with or without specifying a key.</span></span> <span data-ttu-id="1a91f-184">Se si aggiunge un elemento senza una chiave, è necessario usare il relativo indice numerico per accedervi.</span><span class="sxs-lookup"><span data-stu-id="1a91f-184">If you add an item without a key, you must use its numeric index to access it.</span></span>  
  
 <span data-ttu-id="1a91f-185">La classe `Collection` di Visual Basic archivia tutti gli elementi di tipo `Object`, pertanto è possibile aggiungere un elemento di qualsiasi tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="1a91f-185">The Visual Basic `Collection` class stores all its elements as type `Object`, so you can add an item of any data type.</span></span> <span data-ttu-id="1a91f-186">Non esiste alcuna misura per impedire l'aggiunta di tipi di dati non appropriati.</span><span class="sxs-lookup"><span data-stu-id="1a91f-186">There is no safeguard against inappropriate data types being added.</span></span>  
  
 <span data-ttu-id="1a91f-187">Quando si usa la classe `Collection` di Visual Basic, il primo elemento di una raccolta ha indice 1.</span><span class="sxs-lookup"><span data-stu-id="1a91f-187">When you use the Visual Basic `Collection` class, the first item in a collection has an index of 1.</span></span> <span data-ttu-id="1a91f-188">Questo comportamento è diverso rispetto alle classi di raccolte di .NET Framework, per cui l'indice iniziale è 0.</span><span class="sxs-lookup"><span data-stu-id="1a91f-188">This differs from the .NET Framework collection classes, for which the starting index is 0.</span></span>  
  
 <span data-ttu-id="1a91f-189">Quando possibile, usare le raccolte generiche negli spazi dei nomi <xref:System.Collections.Generic?displayProperty=nameWithType> o <xref:System.Collections.Concurrent> al posto della classe `Collection` di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="1a91f-189">Whenever possible, you should use the generic collections in the <xref:System.Collections.Generic?displayProperty=nameWithType> namespace or the <xref:System.Collections.Concurrent> namespace instead of the Visual Basic `Collection` class.</span></span>  
  
 <span data-ttu-id="1a91f-190">Per altre informazioni, vedere <xref:Microsoft.VisualBasic.Collection>.</span><span class="sxs-lookup"><span data-stu-id="1a91f-190">For more information, see <xref:Microsoft.VisualBasic.Collection>.</span></span>  
  
<a name="BKMK_KeyValuePairs"></a>
## <a name="implementing-a-collection-of-keyvalue-pairs"></a><span data-ttu-id="1a91f-191">Implementazione di una raccolta di coppie chiave/valore</span><span class="sxs-lookup"><span data-stu-id="1a91f-191">Implementing a Collection of Key/Value Pairs</span></span>   
 <span data-ttu-id="1a91f-192">La raccolta generica <xref:System.Collections.Generic.Dictionary%602> consente di accedere agli elementi di una raccolta usando la chiave di ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="1a91f-192">The <xref:System.Collections.Generic.Dictionary%602> generic collection enables you to access to elements in a collection by using the key of each element.</span></span> <span data-ttu-id="1a91f-193">Ogni aggiunta al dizionario è costituita da un valore e dalla chiave associata corrispondente.</span><span class="sxs-lookup"><span data-stu-id="1a91f-193">Each addition to the dictionary consists of a value and its associated key.</span></span> <span data-ttu-id="1a91f-194">Il recupero di un valore tramite la relativa chiave è un'operazione veloce, perché la classe `Dictionary` viene implementata come tabella hash.</span><span class="sxs-lookup"><span data-stu-id="1a91f-194">Retrieving a value by using its key is fast because the `Dictionary` class is implemented as a hash table.</span></span>  
  
 <span data-ttu-id="1a91f-195">L'esempio seguente crea una raccolta `Dictionary` ed esegue l'iterazione nel dizionario usando un'istruzione `For Each`.</span><span class="sxs-lookup"><span data-stu-id="1a91f-195">The following example creates a `Dictionary` collection and iterates through the dictionary by using a `For Each` statement.</span></span>  
  
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
  
 <span data-ttu-id="1a91f-196">Per usare invece un inizializzatore di raccolta per compilare la raccolta `Dictionary`, è possibile sostituire i metodi `BuildDictionary` e `AddToDictionary` con il metodo seguente.</span><span class="sxs-lookup"><span data-stu-id="1a91f-196">To instead use a collection initializer to build the `Dictionary` collection, you can replace the `BuildDictionary` and `AddToDictionary` methods with the following method.</span></span>  
  
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
  
 <span data-ttu-id="1a91f-197">L'esempio seguente usa il metodo <xref:System.Collections.Generic.Dictionary%602.ContainsKey%2A> e la proprietà <xref:System.Collections.Generic.Dictionary%602.Item%2A> di `Dictionary` per trovare rapidamente un elemento in base alla chiave.</span><span class="sxs-lookup"><span data-stu-id="1a91f-197">The following example uses the <xref:System.Collections.Generic.Dictionary%602.ContainsKey%2A> method and the <xref:System.Collections.Generic.Dictionary%602.Item%2A> property of `Dictionary` to quickly find an item by key.</span></span> <span data-ttu-id="1a91f-198">Il `Item` proprietà consente di accedere a un elemento nel `elements` insieme, utilizzando il `elements(symbol)` codice in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="1a91f-198">The `Item` property enables you to access an item in the `elements` collection by using the `elements(symbol)` code in Visual Basic.</span></span>  
  
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
  
 <span data-ttu-id="1a91f-199">L'esempio seguente usa invece il metodo <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A> per individuare rapidamente un elemento in base alla chiave.</span><span class="sxs-lookup"><span data-stu-id="1a91f-199">The following example instead uses the <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A> method quickly find an item by key.</span></span>  
  
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
##  <a name="using-linq-to-access-a-collection"></a><span data-ttu-id="1a91f-200">Uso di LINQ per accedere a una raccolta</span><span class="sxs-lookup"><span data-stu-id="1a91f-200">Using LINQ to Access a Collection</span></span>  
 <span data-ttu-id="1a91f-201">È possibile usare LINQ (Language-Integrated Query) per accedere alle raccolte.</span><span class="sxs-lookup"><span data-stu-id="1a91f-201">LINQ (Language-Integrated Query) can be used to access collections.</span></span> <span data-ttu-id="1a91f-202">Le query LINQ forniscono funzionalità di filtro, ordinamento e raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="1a91f-202">LINQ queries provide filtering, ordering, and grouping capabilities.</span></span> <span data-ttu-id="1a91f-203">Per altre informazioni, vedere [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md).</span><span class="sxs-lookup"><span data-stu-id="1a91f-203">For more information, see [Getting Started with LINQ in Visual Basic](../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md).</span></span>  
  
 <span data-ttu-id="1a91f-204">Nell'esempio seguente viene eseguita una query LINQ su un oggetto `List` generico.</span><span class="sxs-lookup"><span data-stu-id="1a91f-204">The following example runs a LINQ query against a generic `List`.</span></span> <span data-ttu-id="1a91f-205">La query LINQ restituisce una raccolta diversa che contiene i risultati.</span><span class="sxs-lookup"><span data-stu-id="1a91f-205">The LINQ query returns a different collection that contains the results.</span></span>  
  
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
## <a name="sorting-a-collection"></a><span data-ttu-id="1a91f-206">Ordinamento di una raccolta</span><span class="sxs-lookup"><span data-stu-id="1a91f-206">Sorting a Collection</span></span>  
 <span data-ttu-id="1a91f-207">L'esempio seguente illustra una procedura per ordinare una raccolta.</span><span class="sxs-lookup"><span data-stu-id="1a91f-207">The following example illustrates a procedure for sorting a collection.</span></span> <span data-ttu-id="1a91f-208">Nell'esempio vengono ordinate le istanze della classe `Car` archiviate in un oggetto <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="1a91f-208">The example sorts instances of the `Car` class that are stored in a <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="1a91f-209">La classe `Car` implementa l'interfaccia <xref:System.IComparable%601>, che richiede l'implementazione del metodo <xref:System.IComparable%601.CompareTo%2A>.</span><span class="sxs-lookup"><span data-stu-id="1a91f-209">The `Car` class implements the <xref:System.IComparable%601> interface, which requires that the <xref:System.IComparable%601.CompareTo%2A> method be implemented.</span></span>  
  
 <span data-ttu-id="1a91f-210">Ogni chiamata al metodo <xref:System.IComparable%601.CompareTo%2A> effettua un confronto unico che viene usato per l'ordinamento.</span><span class="sxs-lookup"><span data-stu-id="1a91f-210">Each call to the <xref:System.IComparable%601.CompareTo%2A> method makes a single comparison that is used for sorting.</span></span> <span data-ttu-id="1a91f-211">Il codice scritto dall'utente presente nel metodo `CompareTo` restituisce un valore per ogni confronto dell'oggetto corrente con un altro oggetto.</span><span class="sxs-lookup"><span data-stu-id="1a91f-211">User-written code in the `CompareTo` method returns a value for each comparison of the current object with another object.</span></span> <span data-ttu-id="1a91f-212">Il valore restituito è minore di zero se l'oggetto corrente è inferiore all'altro oggetto, maggiore di zero se l'oggetto corrente è superiore all'altro oggetto e zero se sono uguali.</span><span class="sxs-lookup"><span data-stu-id="1a91f-212">The value returned is less than zero if the current object is less than the other object, greater than zero if the current object is greater than the other object, and zero if they are equal.</span></span> <span data-ttu-id="1a91f-213">In questo modo è possibile definire nel codice i criteri di maggiore, minore e uguale.</span><span class="sxs-lookup"><span data-stu-id="1a91f-213">This enables you to define in code the criteria for greater than, less than, and equal.</span></span>  
  
 <span data-ttu-id="1a91f-214">Nel metodo `ListCars` l'istruzione `cars.Sort()` ordina l'elenco.</span><span class="sxs-lookup"><span data-stu-id="1a91f-214">In the `ListCars` method, the `cars.Sort()` statement sorts the list.</span></span> <span data-ttu-id="1a91f-215">Questa chiamata al metodo <xref:System.Collections.Generic.List%601.Sort%2A> di <xref:System.Collections.Generic.List%601> determina la chiamata automatica al metodo `CompareTo` per gli oggetti `Car` in `List`.</span><span class="sxs-lookup"><span data-stu-id="1a91f-215">This call to the <xref:System.Collections.Generic.List%601.Sort%2A> method of the <xref:System.Collections.Generic.List%601> causes the `CompareTo` method to be called automatically for the `Car` objects in the `List`.</span></span>  
  
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
## <a name="defining-a-custom-collection"></a><span data-ttu-id="1a91f-216">Definizione di una raccolta personalizzata</span><span class="sxs-lookup"><span data-stu-id="1a91f-216">Defining a Custom Collection</span></span>  
 <span data-ttu-id="1a91f-217">È possibile definire una raccolta implementando l'interfaccia <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Collections.IEnumerable>.</span><span class="sxs-lookup"><span data-stu-id="1a91f-217">You can define a collection by implementing the <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Collections.IEnumerable> interface.</span></span> <span data-ttu-id="1a91f-218">Per altre informazioni, vedere [enumerazione di una raccolta](https://msdn.microsoft.com/library/71807ea7-9180-48a6-916f-35a5251d477f).</span><span class="sxs-lookup"><span data-stu-id="1a91f-218">For additional information, see [Enumerating a Collection](https://msdn.microsoft.com/library/71807ea7-9180-48a6-916f-35a5251d477f).</span></span>  
  
 <span data-ttu-id="1a91f-219">Sebbene sia possibile definire una raccolta personalizzata, in genere è preferibile usare le raccolte incluse in .NET Framework, descritte in [Tipi di raccolte](#kinds-of-collections) in precedenza in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="1a91f-219">Although you can define a custom collection, it is usually better to instead use the collections that are included in the .NET Framework, which are described in [Kinds of Collections](#kinds-of-collections) earlier in this topic.</span></span>  
  
 <span data-ttu-id="1a91f-220">L'esempio seguente definisce una classe di raccolte personalizzata denominata `AllColors`.</span><span class="sxs-lookup"><span data-stu-id="1a91f-220">The following example defines a custom collection class named `AllColors`.</span></span> <span data-ttu-id="1a91f-221">Questa classe implementa l'interfaccia <xref:System.Collections.IEnumerable> che richiede l'implementazione del metodo <xref:System.Collections.IEnumerable.GetEnumerator%2A>.</span><span class="sxs-lookup"><span data-stu-id="1a91f-221">This class implements the <xref:System.Collections.IEnumerable> interface, which requires that the <xref:System.Collections.IEnumerable.GetEnumerator%2A> method be implemented.</span></span>  
  
 <span data-ttu-id="1a91f-222">Il metodo `GetEnumerator` restituisce un'istanza della classe `ColorEnumerator`.</span><span class="sxs-lookup"><span data-stu-id="1a91f-222">The `GetEnumerator` method returns an instance of the `ColorEnumerator` class.</span></span> <span data-ttu-id="1a91f-223">`ColorEnumerator` implementa l'interfaccia <xref:System.Collections.IEnumerator> che richiede l'implementazione della proprietà <xref:System.Collections.IEnumerator.Current%2A> e dei metodi <xref:System.Collections.IEnumerator.MoveNext%2A> e <xref:System.Collections.IEnumerator.Reset%2A>.</span><span class="sxs-lookup"><span data-stu-id="1a91f-223">`ColorEnumerator` implements the <xref:System.Collections.IEnumerator> interface, which requires that the <xref:System.Collections.IEnumerator.Current%2A> property, <xref:System.Collections.IEnumerator.MoveNext%2A> method, and <xref:System.Collections.IEnumerator.Reset%2A> method be implemented.</span></span>  
  
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
##  <a name="iterators"></a><span data-ttu-id="1a91f-224">Iterators</span><span class="sxs-lookup"><span data-stu-id="1a91f-224">Iterators</span></span>  
 <span data-ttu-id="1a91f-225">Un *iteratore* viene usato per eseguire un'iterazione personalizzata in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="1a91f-225">An *iterator* is used to perform a custom iteration over a collection.</span></span> <span data-ttu-id="1a91f-226">Un iteratore può essere un metodo o una funzione di accesso `get`.</span><span class="sxs-lookup"><span data-stu-id="1a91f-226">An iterator can be a method or a `get` accessor.</span></span> <span data-ttu-id="1a91f-227">Un iteratore Usa un' [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) istruzione per restituire ogni elemento della raccolta uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="1a91f-227">An iterator uses a [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) statement to return each element of the collection one at a time.</span></span>  
  
 <span data-ttu-id="1a91f-228">Chiamare un iteratore usando un [For Each... Avanti](../../../visual-basic/language-reference/statements/for-each-next-statement.md) istruzione.</span><span class="sxs-lookup"><span data-stu-id="1a91f-228">You call an iterator by using a [For Each…Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement.</span></span> <span data-ttu-id="1a91f-229">Ogni iterazione del ciclo `For Each` chiama l'iteratore.</span><span class="sxs-lookup"><span data-stu-id="1a91f-229">Each iteration of the `For Each` loop calls the iterator.</span></span> <span data-ttu-id="1a91f-230">Quando si raggiunge un'istruzione `Yield` nell'iteratore, viene restituita un'espressione e viene mantenuta la posizione corrente nel codice.</span><span class="sxs-lookup"><span data-stu-id="1a91f-230">When a `Yield` statement is reached in the iterator, an expression is returned, and the current location in code is retained.</span></span> <span data-ttu-id="1a91f-231">L'esecuzione viene ripresa a partire da quella posizione la volta successiva che viene chiamato l'iteratore.</span><span class="sxs-lookup"><span data-stu-id="1a91f-231">Execution is restarted from that location the next time that the iterator is called.</span></span>  
  
 <span data-ttu-id="1a91f-232">Per altre informazioni, vedere [iteratori (Visual Basic)](../../../visual-basic/programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="1a91f-232">For more information, see [Iterators (Visual Basic)](../../../visual-basic/programming-guide/concepts/iterators.md).</span></span>  
  
 <span data-ttu-id="1a91f-233">Nell'esempio seguente viene usato un metodo iteratore.</span><span class="sxs-lookup"><span data-stu-id="1a91f-233">The following example uses an iterator method.</span></span> <span data-ttu-id="1a91f-234">Il metodo iteratore dispone di un `Yield` istruzione all'interno di un [per... Avanti](../../../visual-basic/language-reference/statements/for-next-statement.md) ciclo.</span><span class="sxs-lookup"><span data-stu-id="1a91f-234">The iterator method has a `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop.</span></span> <span data-ttu-id="1a91f-235">Nel metodo `ListEvenNumbers` ogni iterazione del corpo dell'istruzione `For Each` crea una chiamata al metodo iteratore, che procede all'istruzione `Yield` successiva.</span><span class="sxs-lookup"><span data-stu-id="1a91f-235">In the `ListEvenNumbers` method, each iteration of the `For Each` statement body creates a call to the iterator method, which proceeds to the next `Yield` statement.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1a91f-236">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a91f-236">See also</span></span>

- [<span data-ttu-id="1a91f-237">Inizializzatori di raccolta</span><span class="sxs-lookup"><span data-stu-id="1a91f-237">Collection Initializers</span></span>](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)  
- <span data-ttu-id="1a91f-238">[Programming Concepts (Visual Basic)](../../../visual-basic/programming-guide/concepts/index.md) (Concetti di programmazione (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="1a91f-238">[Programming Concepts (Visual Basic)](../../../visual-basic/programming-guide/concepts/index.md)</span></span>  
- [<span data-ttu-id="1a91f-239">Istruzione Option Strict</span><span class="sxs-lookup"><span data-stu-id="1a91f-239">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
- [<span data-ttu-id="1a91f-240">LINQ to Objects (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1a91f-240">LINQ to Objects (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)  
- [<span data-ttu-id="1a91f-241">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="1a91f-241">Parallel LINQ (PLINQ)</span></span>](../../../standard/parallel-programming/parallel-linq-plinq.md)  
- [<span data-ttu-id="1a91f-242">Raccolte e strutture di dati</span><span class="sxs-lookup"><span data-stu-id="1a91f-242">Collections and Data Structures</span></span>](../../../standard/collections/index.md)  
- [<span data-ttu-id="1a91f-243">Creazione e modifica delle raccolte</span><span class="sxs-lookup"><span data-stu-id="1a91f-243">Creating and Manipulating Collections</span></span>](https://msdn.microsoft.com/library/2065398e-eb1a-4821-9188-75f16e42e069)  
- [<span data-ttu-id="1a91f-244">Selezione di una classe Collection</span><span class="sxs-lookup"><span data-stu-id="1a91f-244">Selecting a Collection Class</span></span>](../../../standard/collections/selecting-a-collection-class.md)  
- [<span data-ttu-id="1a91f-245">Confronti e ordinamenti all'interno delle raccolte</span><span class="sxs-lookup"><span data-stu-id="1a91f-245">Comparisons and Sorts Within Collections</span></span>](../../../standard/collections/comparisons-and-sorts-within-collections.md)  
- [<span data-ttu-id="1a91f-246">Quando utilizzare raccolte generiche</span><span class="sxs-lookup"><span data-stu-id="1a91f-246">When to Use Generic Collections</span></span>](../../../standard/collections/when-to-use-generic-collections.md)
