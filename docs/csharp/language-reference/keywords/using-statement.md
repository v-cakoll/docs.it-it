---
title: Istruzione using (Riferimenti per C#)
ms.date: 07/20/2015
helpviewer_keywords:
- using statement [C#]
ms.assetid: afc355e6-f0b9-4240-94dd-0d93f17d9fc3
ms.openlocfilehash: ec4849dda0f28ad1f0e0ebb2c493a33005107db4
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43480707"
---
# <a name="using-statement-c-reference"></a><span data-ttu-id="712f8-102">Istruzione using (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="712f8-102">using Statement (C# Reference)</span></span>
<span data-ttu-id="712f8-103">Offre una comoda sintassi che verifica l'uso corretto degli oggetti <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="712f8-103">Provides a convenient syntax that ensures the correct use of <xref:System.IDisposable> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="712f8-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="712f8-104">Example</span></span>  
 <span data-ttu-id="712f8-105">L'esempio seguente mostra come usare l'istruzione `using`.</span><span class="sxs-lookup"><span data-stu-id="712f8-105">The following example shows how to use the `using` statement.</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_1.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="712f8-106">Note</span><span class="sxs-lookup"><span data-stu-id="712f8-106">Remarks</span></span>  
 <span data-ttu-id="712f8-107"><xref:System.IO.File> e <xref:System.Drawing.Font> sono esempi di tipi gestiti che accedono a risorse non gestite (in questo caso handle di file e contesti di dispositivo).</span><span class="sxs-lookup"><span data-stu-id="712f8-107"><xref:System.IO.File> and <xref:System.Drawing.Font> are examples of managed types that access unmanaged resources (in this case file handles and device contexts).</span></span> <span data-ttu-id="712f8-108">Esistono molti altri tipi di risorse non gestite e tipi della libreria di classi che le incapsulano.</span><span class="sxs-lookup"><span data-stu-id="712f8-108">There are many other kinds of unmanaged resources and class library types that encapsulate them.</span></span> <span data-ttu-id="712f8-109">Ogni tipo deve implementare l'interfaccia <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="712f8-109">All such types must implement the <xref:System.IDisposable> interface.</span></span>  
  
<span data-ttu-id="712f8-110">Quando la durata di un oggetto `IDisposable` è limitata a un singolo metodo, è necessario dichiararlo e creare un'istanza nell'istruzione `using`.</span><span class="sxs-lookup"><span data-stu-id="712f8-110">When the lifetime of an `IDisposable` object is limited to a single method, you should declare and instantiate it in the `using` statement.</span></span> <span data-ttu-id="712f8-111">L'istruzione `using` chiama il metodo <xref:System.IDisposable.Dispose%2A> sull'oggetto in modo corretto e, quando viene usata come illustrato in precedenza, fa in modo che l'oggetto stesso esca dall'ambito non appena viene chiamato il metodo <xref:System.IDisposable.Dispose%2A>.</span><span class="sxs-lookup"><span data-stu-id="712f8-111">The `using` statement calls the <xref:System.IDisposable.Dispose%2A> method on the object in the correct way, and (when you use it as shown earlier) it also causes the object itself to go out of scope as soon as <xref:System.IDisposable.Dispose%2A> is called.</span></span> <span data-ttu-id="712f8-112">All'interno del blocco `using` l'oggetto è di sola lettura e non può essere modificato o riassegnato.</span><span class="sxs-lookup"><span data-stu-id="712f8-112">Within the `using` block, the object is read-only and cannot be modified or reassigned.</span></span>  
  
 <span data-ttu-id="712f8-113">L'istruzione `using` garantisce che <xref:System.IDisposable.Dispose%2A> venga chiamato anche se si verifica un'eccezione nel blocco `using`.</span><span class="sxs-lookup"><span data-stu-id="712f8-113">The `using` statement ensures that <xref:System.IDisposable.Dispose%2A> is called even if an exception occurs within the `using` block.</span></span> <span data-ttu-id="712f8-114">È possibile ottenere lo stesso risultato inserendo l'oggetto all'interno di un blocco `try` e chiamando <xref:System.IDisposable.Dispose%2A> in un blocco `finally`. Di fatto questo è il modo in cui l'istruzione `using` viene convertita dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="712f8-114">You can achieve the same result by putting the object inside a `try` block and then calling <xref:System.IDisposable.Dispose%2A> in a `finally` block; in fact, this is how the `using` statement is translated by the compiler.</span></span> <span data-ttu-id="712f8-115">L'esempio di codice precedente si espande al codice seguente in fase di compilazione (si notino le parentesi graffe aggiuntive per creare l'ambito limitato per l'oggetto):</span><span class="sxs-lookup"><span data-stu-id="712f8-115">The code example earlier expands to the following code at compile time (note the extra curly braces to create the limited scope for the object):</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_2.cs)]  
 
 <span data-ttu-id="712f8-116">Per altre informazioni sull'istruzione `try`-`finally`, vedere l'argomento [try-finally](try-finally.md).</span><span class="sxs-lookup"><span data-stu-id="712f8-116">For more information about the `try`-`finally` statement, see the [try-finally](try-finally.md) topic.</span></span>
  
 <span data-ttu-id="712f8-117">È possibile dichiarare più istanze di un tipo nell'istruzione `using`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="712f8-117">Multiple instances of a type can be declared in the `using` statement, as shown in the following example:</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_3.cs)]  
  
 <span data-ttu-id="712f8-118">È possibile creare un'istanza dell'oggetto risorsa e quindi passare la variabile all'istruzione `using`, ma questa procedura non è consigliata.</span><span class="sxs-lookup"><span data-stu-id="712f8-118">You can instantiate the resource object and then pass the variable to the `using` statement, but this is not a best practice.</span></span> <span data-ttu-id="712f8-119">In questo caso l'oggetto rimane nell'ambito quando il controllo lascia il blocco `using`, anche se probabilmente non avrà più accesso alle relative risorse non gestite.</span><span class="sxs-lookup"><span data-stu-id="712f8-119">In this case, after control leaves the `using` block, the object remains in scope but probably has no access to its unmanaged resources.</span></span> <span data-ttu-id="712f8-120">In altre parole, non è più completamente inizializzato.</span><span class="sxs-lookup"><span data-stu-id="712f8-120">In other words, it's not fully initialized anymore.</span></span> <span data-ttu-id="712f8-121">Se si tenta di usare l'oggetto di fuori del blocco `using`, si rischia di causare la generazione di un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="712f8-121">If you try to use the object outside the `using` block, you risk causing an exception to be thrown.</span></span> <span data-ttu-id="712f8-122">Per questo motivo, in genere è preferibile creare un'istanza dell'oggetto nell'istruzione `using` e limitare l'ambito al blocco `using`.</span><span class="sxs-lookup"><span data-stu-id="712f8-122">For this reason, it's generally better to instantiate the object in the `using` statement and limit its scope to the `using` block.</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_4.cs)]  
  
<span data-ttu-id="712f8-123">Per altre informazioni sull'eliminazione degli oggetti `IDisposable`, vedere [Uso di oggetti che implementano IDisposable](../../../standard/garbage-collection/using-objects.md).</span><span class="sxs-lookup"><span data-stu-id="712f8-123">For more information about disposing of `IDisposable` objects, see [Using objects that implement IDisposable](../../../standard/garbage-collection/using-objects.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="712f8-124">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="712f8-124">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="712f8-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="712f8-125">See Also</span></span>

- [<span data-ttu-id="712f8-126">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="712f8-126">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="712f8-127">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="712f8-127">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="712f8-128">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="712f8-128">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="712f8-129">Direttiva using</span><span class="sxs-lookup"><span data-stu-id="712f8-129">using Directive</span></span>](../../../csharp/language-reference/keywords/using-directive.md)  
- [<span data-ttu-id="712f8-130">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="712f8-130">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)  
- [<span data-ttu-id="712f8-131">Uso di oggetti che implementano IDisposable</span><span class="sxs-lookup"><span data-stu-id="712f8-131">Using objects that implement IDisposable</span></span>](../../../standard/garbage-collection/using-objects.md)  
- [<span data-ttu-id="712f8-132">Interfaccia IDisposable</span><span class="sxs-lookup"><span data-stu-id="712f8-132">IDisposable interface</span></span>](xref:System.IDisposable)
