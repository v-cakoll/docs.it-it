---
title: Istruzione using - Riferimenti per C#
ms.date: 10/15/2019
helpviewer_keywords:
- using statement [C#]
ms.assetid: afc355e6-f0b9-4240-94dd-0d93f17d9fc3
ms.openlocfilehash: 52cde99fd029ce50f159b2a87fbfbf47fc79dccc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712962"
---
# <a name="using-statement-c-reference"></a><span data-ttu-id="809b4-102">Istruzione using (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="809b4-102">using statement (C# Reference)</span></span>

<span data-ttu-id="809b4-103">Offre una comoda sintassi che verifica l'uso corretto degli oggetti <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="809b4-103">Provides a convenient syntax that ensures the correct use of <xref:System.IDisposable> objects.</span></span>

## <a name="example"></a><span data-ttu-id="809b4-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="809b4-104">Example</span></span>

<span data-ttu-id="809b4-105">L'esempio seguente mostra come usare l'istruzione `using`.</span><span class="sxs-lookup"><span data-stu-id="809b4-105">The following example shows how to use the `using` statement.</span></span>

[!code-csharp[csrefKeywordsNamespace#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#4)]

<span data-ttu-id="809b4-106">A partire dalla versione 8.0 di C, `using` è possibile usare la sintassi alternativa seguente per l'istruzione che non richiede parentesi graffe:</span><span class="sxs-lookup"><span data-stu-id="809b4-106">Beginning with C# 8.0, you can use the following alternative syntax for the `using` statement that doesn't require braces:</span></span>

[!code-csharp[csrefKeywordsNamespace#New](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#ModernUsing)]

## <a name="remarks"></a><span data-ttu-id="809b4-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="809b4-107">Remarks</span></span>

<span data-ttu-id="809b4-108"><xref:System.IO.File> e <xref:System.Drawing.Font> sono esempi di tipi gestiti che accedono a risorse non gestite (in questo caso handle di file e contesti di dispositivo).</span><span class="sxs-lookup"><span data-stu-id="809b4-108"><xref:System.IO.File> and <xref:System.Drawing.Font> are examples of managed types that access unmanaged resources (in this case file handles and device contexts).</span></span> <span data-ttu-id="809b4-109">Esistono molti altri tipi di risorse non gestite e tipi della libreria di classi che le incapsulano.</span><span class="sxs-lookup"><span data-stu-id="809b4-109">There are many other kinds of unmanaged resources and class library types that encapsulate them.</span></span> <span data-ttu-id="809b4-110">Ogni tipo deve implementare l'interfaccia <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="809b4-110">All such types must implement the <xref:System.IDisposable> interface.</span></span>

<span data-ttu-id="809b4-111">Quando la durata di un oggetto `IDisposable` è limitata a un singolo metodo, è necessario dichiararlo e creare un'istanza nell'istruzione `using`.</span><span class="sxs-lookup"><span data-stu-id="809b4-111">When the lifetime of an `IDisposable` object is limited to a single method, you should declare and instantiate it in the `using` statement.</span></span> <span data-ttu-id="809b4-112">L'istruzione `using` chiama il metodo <xref:System.IDisposable.Dispose%2A> sull'oggetto in modo corretto e, quando viene usata come illustrato in precedenza, fa in modo che l'oggetto stesso esca dall'ambito non appena viene chiamato il metodo <xref:System.IDisposable.Dispose%2A>.</span><span class="sxs-lookup"><span data-stu-id="809b4-112">The `using` statement calls the <xref:System.IDisposable.Dispose%2A> method on the object in the correct way, and (when you use it as shown earlier) it also causes the object itself to go out of scope as soon as <xref:System.IDisposable.Dispose%2A> is called.</span></span> <span data-ttu-id="809b4-113">All'interno del blocco `using` l'oggetto è di sola lettura e non può essere modificato o riassegnato.</span><span class="sxs-lookup"><span data-stu-id="809b4-113">Within the `using` block, the object is read-only and cannot be modified or reassigned.</span></span>

<span data-ttu-id="809b4-114">L'istruzione `using` garantisce che <xref:System.IDisposable.Dispose%2A> venga chiamato anche se si verifica un'eccezione nel blocco `using`.</span><span class="sxs-lookup"><span data-stu-id="809b4-114">The `using` statement ensures that <xref:System.IDisposable.Dispose%2A> is called even if an exception occurs within the `using` block.</span></span> <span data-ttu-id="809b4-115">È possibile ottenere lo stesso risultato inserendo l'oggetto all'interno di un blocco `try` e chiamando <xref:System.IDisposable.Dispose%2A> in un blocco `finally`. Di fatto questo è il modo in cui l'istruzione `using` viene convertita dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="809b4-115">You can achieve the same result by putting the object inside a `try` block and then calling <xref:System.IDisposable.Dispose%2A> in a `finally` block; in fact, this is how the `using` statement is translated by the compiler.</span></span> <span data-ttu-id="809b4-116">L'esempio di codice precedente si espande al codice seguente in fase di compilazione (si notino le parentesi graffe aggiuntive per creare l'ambito limitato per l'oggetto):</span><span class="sxs-lookup"><span data-stu-id="809b4-116">The code example earlier expands to the following code at compile time (note the extra curly braces to create the limited scope for the object):</span></span>

[!code-csharp[csrefKeywordsNamespace#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#5)]

<span data-ttu-id="809b4-117">La sintassi dell'istruzione più recente `using` si traduce in codice molto simile.</span><span class="sxs-lookup"><span data-stu-id="809b4-117">The newer `using` statement syntax translates to very similar code.</span></span> <span data-ttu-id="809b4-118">Il `try` blocco si apre dove viene dichiarata la variabile.</span><span class="sxs-lookup"><span data-stu-id="809b4-118">The `try` block opens where the variable is declared.</span></span> <span data-ttu-id="809b4-119">Il `finally` blocco viene aggiunto alla chiusura del blocco di inclusione, in genere alla fine di un metodo.</span><span class="sxs-lookup"><span data-stu-id="809b4-119">The `finally` block is added at the close of the enclosing block, typically at the end of a method.</span></span>

<span data-ttu-id="809b4-120">Per altre informazioni sull'istruzione `try`-`finally`, vedere l'argomento [try-finally](try-finally.md).</span><span class="sxs-lookup"><span data-stu-id="809b4-120">For more information about the `try`-`finally` statement, see the [try-finally](try-finally.md) topic.</span></span>

<span data-ttu-id="809b4-121">È possibile dichiarare più istanze di un tipo nell'istruzione `using`, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="809b4-121">Multiple instances of a type can be declared in the `using` statement, as shown in the following example:</span></span>

[!code-csharp[csrefKeywordsNamespace#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#6)]

<span data-ttu-id="809b4-122">È possibile combinare più dichiarazioni dello stesso tipo usando anche la nuova sintassi introdotta con C .</span><span class="sxs-lookup"><span data-stu-id="809b4-122">You can combine multiple declarations of the same type using the new syntax introduced with C# 8 as well.</span></span> <span data-ttu-id="809b4-123">Questa operazione è illustrata nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="809b4-123">This is shown in the following example:</span></span>

[!code-csharp[csrefKeywordsNamespace#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#MultipleUsing)]

<span data-ttu-id="809b4-124">È possibile creare un'istanza dell'oggetto risorsa e quindi passare la variabile all'istruzione `using`, ma questa procedura non è consigliata.</span><span class="sxs-lookup"><span data-stu-id="809b4-124">You can instantiate the resource object and then pass the variable to the `using` statement, but this is not a best practice.</span></span> <span data-ttu-id="809b4-125">In questo caso l'oggetto rimane nell'ambito quando il controllo lascia il blocco `using`, anche se probabilmente non avrà più accesso alle relative risorse non gestite.</span><span class="sxs-lookup"><span data-stu-id="809b4-125">In this case, after control leaves the `using` block, the object remains in scope but probably has no access to its unmanaged resources.</span></span> <span data-ttu-id="809b4-126">In altre parole, non è più completamente inizializzato.</span><span class="sxs-lookup"><span data-stu-id="809b4-126">In other words, it's not fully initialized anymore.</span></span> <span data-ttu-id="809b4-127">Se si tenta di usare l'oggetto di fuori del blocco `using`, si rischia di causare la generazione di un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="809b4-127">If you try to use the object outside the `using` block, you risk causing an exception to be thrown.</span></span> <span data-ttu-id="809b4-128">Per questo motivo, in genere è preferibile creare un'istanza dell'oggetto nell'istruzione `using` e limitare l'ambito al blocco `using`.</span><span class="sxs-lookup"><span data-stu-id="809b4-128">For this reason, it's generally better to instantiate the object in the `using` statement and limit its scope to the `using` block.</span></span>

[!code-csharp[csrefKeywordsNamespace#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#7)]

<span data-ttu-id="809b4-129">Per altre informazioni sull'eliminazione degli oggetti `IDisposable`, vedere [Uso di oggetti che implementano IDisposable](../../../standard/garbage-collection/using-objects.md).</span><span class="sxs-lookup"><span data-stu-id="809b4-129">For more information about disposing of `IDisposable` objects, see [Using objects that implement IDisposable](../../../standard/garbage-collection/using-objects.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="809b4-130">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="809b4-130">C# language specification</span></span>

<span data-ttu-id="809b4-131">Per altre informazioni, vedere [Istruzione using](~/_csharplang/spec/statements.md#the-using-statement) nella [specifica del linguaggio C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="809b4-131">For more information, see [The using statement](~/_csharplang/spec/statements.md#the-using-statement) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="809b4-132">La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.</span><span class="sxs-lookup"><span data-stu-id="809b4-132">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="809b4-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="809b4-133">See also</span></span>

- [<span data-ttu-id="809b4-134">Guida di riferimento a C</span><span class="sxs-lookup"><span data-stu-id="809b4-134">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="809b4-135">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="809b4-135">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="809b4-136">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="809b4-136">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="809b4-137">using Direttiva</span><span class="sxs-lookup"><span data-stu-id="809b4-137">using Directive</span></span>](using-directive.md)
- [<span data-ttu-id="809b4-138">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="809b4-138">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="809b4-139">Uso di oggetti che implementano IDisposable</span><span class="sxs-lookup"><span data-stu-id="809b4-139">Using objects that implement IDisposable</span></span>](../../../standard/garbage-collection/using-objects.md)
- [<span data-ttu-id="809b4-140">Interfaccia IDisposable</span><span class="sxs-lookup"><span data-stu-id="809b4-140">IDisposable interface</span></span>](xref:System.IDisposable)
- [<span data-ttu-id="809b4-141">Using (istruzione) in C .</span><span class="sxs-lookup"><span data-stu-id="809b4-141">using statement in C# 8.0</span></span>](~/_csharplang/proposals/csharp-8.0/using.md)
