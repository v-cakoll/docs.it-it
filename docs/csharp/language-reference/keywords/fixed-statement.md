---
title: Istruzione fixed (Riferimenti per C#)
ms.date: 05/10/2018
f1_keywords:
- fixed_CSharpKeyword
- fixed
helpviewer_keywords:
- fixed keyword [C#]
ms.openlocfilehash: 021fc3bd63922394bd70495bd4335b068fc51cdd
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2018
ms.locfileid: "42929299"
---
# <a name="fixed-statement-c-reference"></a><span data-ttu-id="b8347-102">Istruzione fixed (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="b8347-102">fixed Statement (C# Reference)</span></span>

<span data-ttu-id="b8347-103">L'istruzione `fixed` impedisce che il Garbage Collector esegua la rilocazione di una variabile mobile.</span><span class="sxs-lookup"><span data-stu-id="b8347-103">The `fixed` statement prevents the garbage collector from relocating a movable variable.</span></span> <span data-ttu-id="b8347-104">L'istruzione `fixed` è consentita solo in un contesto di tipo [unsafe](unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="b8347-104">The `fixed` statement is only permitted in an [unsafe](unsafe.md) context.</span></span> <span data-ttu-id="b8347-105">È possibile usare `fixed` anche per creare [buffer a dimensione fissa](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span><span class="sxs-lookup"><span data-stu-id="b8347-105">`fixed` can also be used to create [fixed size buffers](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span></span>

<span data-ttu-id="b8347-106">L'istruzione `fixed` imposta un puntatore a una variabile gestita e la blocca durante l'esecuzione dell'istruzione.</span><span class="sxs-lookup"><span data-stu-id="b8347-106">The `fixed` statement sets a pointer to a managed variable and "pins" that variable during the execution of the statement.</span></span> <span data-ttu-id="b8347-107">I puntatori alle variabili mobili gestite sono utili solo in un contesto `fixed`.</span><span class="sxs-lookup"><span data-stu-id="b8347-107">Pointers to movable managed variables are useful only in a `fixed` context.</span></span> <span data-ttu-id="b8347-108">Senza un contesto `fixed`, l'operazione di garbage collection potrebbe spostare le variabili in modo imprevedibile.</span><span class="sxs-lookup"><span data-stu-id="b8347-108">Without a `fixed` context, garbage collection could relocate the variables unpredictably.</span></span> <span data-ttu-id="b8347-109">Il compilatore C# consente di assegnare un puntatore a una variabile gestita in un'istruzione `fixed`.</span><span class="sxs-lookup"><span data-stu-id="b8347-109">The C# compiler only lets you assign a pointer to a managed variable in a `fixed` statement.</span></span>

[!code-csharp[Accessing fixed memory](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#1)]

<span data-ttu-id="b8347-110">È possibile inizializzare un puntatore usando una matrice, una stringa, un buffer a dimensione fissa o l'indirizzo di una variabile.</span><span class="sxs-lookup"><span data-stu-id="b8347-110">You can initialize a pointer by using an array, a string, a fixed-size buffer, or the address of a variable.</span></span> <span data-ttu-id="b8347-111">Nell'esempio seguente viene illustrato l'uso di indirizzi, matrici e stringhe di una variabile.</span><span class="sxs-lookup"><span data-stu-id="b8347-111">The following example illustrates the use of variable addresses, arrays, and strings.</span></span> <span data-ttu-id="b8347-112">Per altre informazioni sui buffer a dimensione fissa, vedere [Buffer a dimensione fissa](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span><span class="sxs-lookup"><span data-stu-id="b8347-112">For more information about fixed-size buffers, see [Fixed Size Buffers](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span></span>

[!code-csharp[Initializing fixed size buffers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#2)]

<span data-ttu-id="b8347-113">A partire da C# 7.3, l'istruzione `fixed` opera su tipi aggiuntivi oltre a matrici, stringhe, buffer a dimensione fissa o variabili non gestite.</span><span class="sxs-lookup"><span data-stu-id="b8347-113">Starting with C# 7.3, the `fixed` statement operates on additional types beyond arrays, strings, fixed-size buffers, or unmanaged variables.</span></span> <span data-ttu-id="b8347-114">È possibile bloccare qualsiasi tipo che implementa un metodo denominato `GetPinnableReference`.</span><span class="sxs-lookup"><span data-stu-id="b8347-114">Any type that implements a method named `GetPinnableReference` can be pinned.</span></span> <span data-ttu-id="b8347-115">`GetPinnableReference` deve restituire una variabile `ref` a un tipo non gestito.</span><span class="sxs-lookup"><span data-stu-id="b8347-115">The `GetPinnableReference` must return a `ref` variable to an unmanaged type.</span></span> <span data-ttu-id="b8347-116">Vedere l'argomento sui [tipi di puntatore](../../programming-guide/unsafe-code-pointers/pointer-types.md) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="b8347-116">See the topic on [pointer types](../../programming-guide/unsafe-code-pointers/pointer-types.md) for more information.</span></span> <span data-ttu-id="b8347-117">I tipi .NET <xref:System.Span%601?displayProperty=nameWithType> e <xref:System.ReadOnlySpan%601?displayProperty=nameWithType> introdotti in .NET Core 2.0 usano questo modello e possono essere bloccati.</span><span class="sxs-lookup"><span data-stu-id="b8347-117">The .NET types <xref:System.Span%601?displayProperty=nameWithType> and <xref:System.ReadOnlySpan%601?displayProperty=nameWithType> introduced in .NET Core 2.0 make use of this pattern and can be pinned.</span></span> <span data-ttu-id="b8347-118">Questa operazione è illustrata nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="b8347-118">This is shown in the following example:</span></span>

[!code-csharp[Accessing fixed memory](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#FixedSpan)]

<span data-ttu-id="b8347-119">Se si creano tipi che devono partecipare a questo modello, vedere <xref:System.Span%601.GetPinnableReference?displayProperty=nameWithType> per un esempio di implementazione del modello.</span><span class="sxs-lookup"><span data-stu-id="b8347-119">If you are creating types that should participate in this pattern, see <xref:System.Span%601.GetPinnableReference?displayProperty=nameWithType> for an example of implementing the pattern.</span></span>

<span data-ttu-id="b8347-120">Se sono dello stesso tipo, è possibile inizializzare più puntatori in un'unica istruzione:</span><span class="sxs-lookup"><span data-stu-id="b8347-120">Multiple pointers can be initialized in one statement if they are all the same type:</span></span>

```csharp
fixed (byte* ps = srcarray, pd = dstarray) {...}
```

<span data-ttu-id="b8347-121">Per inizializzare puntatori di tipi diversi, annidare semplicemente le istruzioni `fixed` come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="b8347-121">To initialize pointers of different types, simply nest `fixed` statements, as shown in the following example.</span></span>

[!code-csharp[Initializing multiple pointers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#3)]

<span data-ttu-id="b8347-122">Dopo aver eseguito il codice nell'istruzione, le variabili bloccate vengono sbloccate e sottoposte al Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="b8347-122">After the code in the statement is executed, any pinned variables are unpinned and subject to garbage collection.</span></span> <span data-ttu-id="b8347-123">Di conseguenza, evitare di puntare alle variabili esterne all'istruzione `fixed`.</span><span class="sxs-lookup"><span data-stu-id="b8347-123">Therefore, do not point to those variables outside the `fixed` statement.</span></span> <span data-ttu-id="b8347-124">Le variabili dichiarate nell'istruzione `fixed` rientrano nell'ambito di tale istruzione, semplificandola:</span><span class="sxs-lookup"><span data-stu-id="b8347-124">The variables declared in the `fixed` statement are scoped to that statement, making this easier:</span></span>

```csharp
fixed (byte* ps = srcarray, pd = dstarray)
{
   ...
}
// ps and pd are no longer in scope here.
```

<span data-ttu-id="b8347-125">I puntatori inizializzati nelle istruzioni `fixed` sono variabili di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="b8347-125">Pointers initialized in `fixed` statements are readonly variables.</span></span> <span data-ttu-id="b8347-126">Per modificare il valore puntatore, è necessario dichiarare una seconda variabile e quindi modificarla.</span><span class="sxs-lookup"><span data-stu-id="b8347-126">If you want to modify the pointer value, you must declare a second pointer variable, and modify that.</span></span> <span data-ttu-id="b8347-127">La variabile dichiarata nell'istruzione `fixed` non può essere modificata:</span><span class="sxs-lookup"><span data-stu-id="b8347-127">The variable declared in the `fixed` statement cannot be modified:</span></span>

```csharp
fixed (byte* ps = srcarray, pd = dstarray)
{
    byte* pSourceCopy = ps;
    pSourceCopy++; // point to the next element.
    ps++; // invalid: cannot modify ps, as it is declared in the fixed statement.
}
```


<span data-ttu-id="b8347-128">Nella modalità di tipo unsafe è possibile allocare la memoria nello stack, che non è necessario bloccare perché non viene sottoposto al Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="b8347-128">In unsafe mode, you can allocate memory on the stack, where it is not subject to garbage collection and therefore does not need to be pinned.</span></span> <span data-ttu-id="b8347-129">Per altre informazioni, vedere [stackalloc](stackalloc.md).</span><span class="sxs-lookup"><span data-stu-id="b8347-129">For more information, see [stackalloc](stackalloc.md).</span></span>

[!code-csharp[Initializing multiple pointers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="b8347-130">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="b8347-130">C# Language Specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="b8347-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8347-131">See Also</span></span>

- [<span data-ttu-id="b8347-132">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="b8347-132">C# Reference</span></span>](../index.md)  
- [<span data-ttu-id="b8347-133">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="b8347-133">C# Programming Guide</span></span>](../../programming-guide/index.md)  
- [<span data-ttu-id="b8347-134">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="b8347-134">C# Keywords</span></span>](index.md)  
- [<span data-ttu-id="b8347-135">unsafe</span><span class="sxs-lookup"><span data-stu-id="b8347-135">unsafe</span></span>](unsafe.md)  
- [<span data-ttu-id="b8347-136">Buffer a dimensione fissa</span><span class="sxs-lookup"><span data-stu-id="b8347-136">Fixed Size Buffers</span></span>](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
