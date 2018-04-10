---
title: Istruzione using (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- using statement [C#]
ms.assetid: afc355e6-f0b9-4240-94dd-0d93f17d9fc3
caps.latest.revision: 31
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1fdf37e1bfc57bf850b332f167e57d3e05d23e78
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="using-statement-c-reference"></a><span data-ttu-id="4a84b-102">Istruzione using (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="4a84b-102">using Statement (C# Reference)</span></span>
<span data-ttu-id="4a84b-103">Offre una comoda sintassi che verifica l'uso corretto degli oggetti <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="4a84b-103">Provides a convenient syntax that ensures the correct use of <xref:System.IDisposable> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a84b-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="4a84b-104">Example</span></span>  
 <span data-ttu-id="4a84b-105">L'esempio seguente illustra come usare l'istruzione using.</span><span class="sxs-lookup"><span data-stu-id="4a84b-105">The following example shows how to use the using statement.</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_1.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="4a84b-106">Note</span><span class="sxs-lookup"><span data-stu-id="4a84b-106">Remarks</span></span>  
 <span data-ttu-id="4a84b-107"><xref:System.IO.File> e <xref:System.Drawing.Font> sono esempi di tipi gestiti che accedono a risorse non gestite (in questo caso handle di file e contesti di dispositivo).</span><span class="sxs-lookup"><span data-stu-id="4a84b-107"><xref:System.IO.File> and <xref:System.Drawing.Font> are examples of managed types that access unmanaged resources (in this case file handles and device contexts).</span></span> <span data-ttu-id="4a84b-108">Esistono molti altri tipi di risorse non gestite e tipi della libreria di classi che le incapsulano.</span><span class="sxs-lookup"><span data-stu-id="4a84b-108">There are many other kinds of unmanaged resources and class library types that encapsulate them.</span></span> <span data-ttu-id="4a84b-109">Ogni tipo deve implementare l'interfaccia <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="4a84b-109">All such types must implement the <xref:System.IDisposable> interface.</span></span>  
  
<span data-ttu-id="4a84b-110">Quando la durata di un `IDisposable` oggetto è limitato a un singolo metodo, è necessario dichiarare e creare un'istanza in un `using` istruzione.</span><span class="sxs-lookup"><span data-stu-id="4a84b-110">When the lifetime of an `IDisposable` object is limited to a single method, you should declare and instantiate it in a `using` statement.</span></span> <span data-ttu-id="4a84b-111">L'istruzione `using` chiama il metodo <xref:System.IDisposable.Dispose%2A> sull'oggetto in modo corretto e, quando viene usata come illustrato in precedenza, fa in modo che l'oggetto stesso esca dall'ambito non appena viene chiamato il metodo <xref:System.IDisposable.Dispose%2A>.</span><span class="sxs-lookup"><span data-stu-id="4a84b-111">The `using` statement calls the <xref:System.IDisposable.Dispose%2A> method on the object in the correct way, and (when you use it as shown earlier) it also causes the object itself to go out of scope as soon as <xref:System.IDisposable.Dispose%2A> is called.</span></span> <span data-ttu-id="4a84b-112">All'interno del blocco `using` l'oggetto è di sola lettura e non può essere modificato o riassegnato.</span><span class="sxs-lookup"><span data-stu-id="4a84b-112">Within the `using` block, the object is read-only and cannot be modified or reassigned.</span></span>  
  
 <span data-ttu-id="4a84b-113">L'istruzione `using` verifica che il metodo <xref:System.IDisposable.Dispose%2A> venga chiamato anche se si verifica un'eccezione mentre si chiamano i metodi sull'oggetto.</span><span class="sxs-lookup"><span data-stu-id="4a84b-113">The `using` statement ensures that <xref:System.IDisposable.Dispose%2A> is called even if an exception occurs while you are calling methods on the object.</span></span> <span data-ttu-id="4a84b-114">È possibile ottenere lo stesso risultato inserendo l'oggetto all'interno di un blocco try e chiamando `using` in un blocco finally. Di fatto questo è il modo in cui l'istruzione <xref:System.IDisposable.Dispose%2A> viene convertita dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="4a84b-114">You can achieve the same result by putting the object inside a try block and then calling <xref:System.IDisposable.Dispose%2A> in a finally block; in fact, this is how the `using` statement is translated by the compiler.</span></span> <span data-ttu-id="4a84b-115">L'esempio di codice precedente si espande al codice seguente in fase di compilazione (si notino le parentesi graffe aggiuntive per creare l'ambito limitato per l'oggetto):</span><span class="sxs-lookup"><span data-stu-id="4a84b-115">The code example earlier expands to the following code at compile time (note the extra curly braces to create the limited scope for the object):</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_2.cs)]  
  
 <span data-ttu-id="4a84b-116">È possibile dichiarare più istanze di un tipo in un'istruzione `using`, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="4a84b-116">Multiple instances of a type can be declared in a `using` statement, as shown in the following example.</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_3.cs)]  
  
 <span data-ttu-id="4a84b-117">È possibile creare un'istanza dell'oggetto risorsa e quindi passare la variabile all'istruzione `using`, ma questa procedura non è consigliata.</span><span class="sxs-lookup"><span data-stu-id="4a84b-117">You can instantiate the resource object and then pass the variable to the `using` statement, but this is not a best practice.</span></span> <span data-ttu-id="4a84b-118">In questo caso l'oggetto rimane nell'ambito quando il controllo lascia il blocco `using`, anche se probabilmente non avrà più accesso alle relative risorse non gestite.</span><span class="sxs-lookup"><span data-stu-id="4a84b-118">In this case, the object remains in scope after control leaves the `using` block even though it will probably no longer have access to its unmanaged resources.</span></span> <span data-ttu-id="4a84b-119">In altre parole, non verrà più completamente inizializzato.</span><span class="sxs-lookup"><span data-stu-id="4a84b-119">In other words, it will no longer be fully initialized.</span></span> <span data-ttu-id="4a84b-120">Se si tenta di usare l'oggetto di fuori del blocco `using`, si rischia di causare la generazione di un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="4a84b-120">If you try to use the object outside the `using` block, you risk causing an exception to be thrown.</span></span> <span data-ttu-id="4a84b-121">Per questo motivo, in genere è preferibile creare un'istanza dell'oggetto nell'istruzione `using` e limitare l'ambito al blocco `using`.</span><span class="sxs-lookup"><span data-stu-id="4a84b-121">For this reason, it is generally better to instantiate the object in the `using` statement and limit its scope to the `using` block.</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_4.cs)]  
  
<span data-ttu-id="4a84b-122">Per ulteriori informazioni sull'eliminazione di `IDisposable` degli oggetti, vedere [utilizzando gli oggetti che implementano IDisposable](../../../standard/garbage-collection/using-objects.md).</span><span class="sxs-lookup"><span data-stu-id="4a84b-122">For more information on disposing of `IDisposable` objects, see [Using objects that implement IDisposable](../../../standard/garbage-collection/using-objects.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="4a84b-123">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="4a84b-123">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4a84b-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a84b-124">See Also</span></span>  
 [<span data-ttu-id="4a84b-125">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="4a84b-125">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="4a84b-126">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="4a84b-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="4a84b-127">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="4a84b-127">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="4a84b-128">Direttiva using</span><span class="sxs-lookup"><span data-stu-id="4a84b-128">using Directive</span></span>](../../../csharp/language-reference/keywords/using-directive.md)  
 [<span data-ttu-id="4a84b-129">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="4a84b-129">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)  
 [<span data-ttu-id="4a84b-130">Uso di oggetti che implementano IDisposable</span><span class="sxs-lookup"><span data-stu-id="4a84b-130">Using objects that implement IDisposable</span></span>](../../../standard/garbage-collection/using-objects.md)  
 [<span data-ttu-id="4a84b-131">Interfaccia IDisposable</span><span class="sxs-lookup"><span data-stu-id="4a84b-131">IDisposable interface</span></span>](xref:System.IDisposable)
