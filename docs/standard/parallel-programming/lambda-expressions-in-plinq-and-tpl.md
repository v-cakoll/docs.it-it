---
title: Espressioni lambda in PLINQ e TPL
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Func delegate, creating with lambda expression
- Action delegate, creating with lambda expression
- lambda expressions, with Action and Func
ms.assetid: 645b2c17-29d0-4ffa-8684-430743cc2f2d
ms.openlocfilehash: 4e5be295a52edc1a7f0a0a3aa98f55335ae3e31b
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453000"
---
# <a name="lambda-expressions-in-plinq-and-tpl"></a><span data-ttu-id="7a3dc-102">Espressioni lambda in PLINQ e TPL</span><span class="sxs-lookup"><span data-stu-id="7a3dc-102">Lambda Expressions in PLINQ and TPL</span></span>

<span data-ttu-id="7a3dc-103">Task Parallel Library (TPL) contiene numerosi metodi che accettano una delle famiglie di delegati <xref:System.Func%601?displayProperty=nameWithType> o <xref:System.Action?displayProperty=nameWithType> come parametri di input.</span><span class="sxs-lookup"><span data-stu-id="7a3dc-103">The Task Parallel Library (TPL) contains many methods that take one of the <xref:System.Func%601?displayProperty=nameWithType> or <xref:System.Action?displayProperty=nameWithType> family of delegates as input parameters.</span></span> <span data-ttu-id="7a3dc-104">Questi delegati vengono usati per passare la logica di programma personalizzata al ciclo, all'attività o alla query parallela.</span><span class="sxs-lookup"><span data-stu-id="7a3dc-104">You use these delegates to pass in your custom program logic to the parallel loop, task or query.</span></span> <span data-ttu-id="7a3dc-105">Gli esempi di codice per TPL e PLINQ usano espressioni lambda per creare istanze dei delegati come blocchi di codice inline.</span><span class="sxs-lookup"><span data-stu-id="7a3dc-105">The code examples for TPL as well as PLINQ use lambda expressions to create instances of those delegates as inline code blocks.</span></span> <span data-ttu-id="7a3dc-106">Questo argomento offre una breve introduzione a Func e Action e illustra come usare le espressioni lambda in TPL e PLINQ.</span><span class="sxs-lookup"><span data-stu-id="7a3dc-106">This topic provides a brief introduction to Func and Action and shows you how to use lambda expressions in the Task Parallel Library and PLINQ.</span></span>

> [!NOTE]
> <span data-ttu-id="7a3dc-107">Per ulteriori informazioni sui delegati in generale [, vedere delegati](../../csharp/programming-guide/delegates/index.md) [e delegati](../../visual-basic/programming-guide/language-features/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="7a3dc-107">For more information about delegates in general, see [Delegates](../../csharp/programming-guide/delegates/index.md) and [Delegates](../../visual-basic/programming-guide/language-features/delegates/index.md).</span></span> <span data-ttu-id="7a3dc-108">Per altre informazioni sulle espressioni lambda in C# e Visual Basic, vedere [Espressioni lambda (Guida per programmatori C#)](../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) e [Espressioni lambda (Visual Basic)](../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="7a3dc-108">For more information about lambda expressions in C# and Visual Basic, see [Lambda Expressions](../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) and [Lambda Expressions](../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>

## <a name="func-delegate"></a><span data-ttu-id="7a3dc-109">Delegato Func</span><span class="sxs-lookup"><span data-stu-id="7a3dc-109">Func Delegate</span></span>

<span data-ttu-id="7a3dc-110">Un delegato `Func` incapsula un metodo che restituisce un valore.</span><span class="sxs-lookup"><span data-stu-id="7a3dc-110">A `Func` delegate encapsulates a method that returns a value.</span></span> <span data-ttu-id="7a3dc-111">In una firma `Func`, l'ultimo parametro di tipo, o più a destra, specifica sempre il tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="7a3dc-111">In a `Func` signature, the last, or rightmost, type parameter always specifies the return type.</span></span> <span data-ttu-id="7a3dc-112">Una causa comune degli errori del compilatore è il tentativo di passare due parametri di input a un tipo <xref:System.Func%602?displayProperty=nameWithType>, che accetta un solo parametro di input.</span><span class="sxs-lookup"><span data-stu-id="7a3dc-112">One common cause of compiler errors is to attempt to pass in two input parameters to a <xref:System.Func%602?displayProperty=nameWithType>; in fact this type takes only one input parameter.</span></span> <span data-ttu-id="7a3dc-113">.NET definisce 17 versioni di `Func`: <xref:System.Func%601?displayProperty=nameWithType>, <xref:System.Func%602?displayProperty=nameWithType>, <xref:System.Func%603?displayProperty=nameWithType>e così via fino a <xref:System.Func%6017?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7a3dc-113">.NET defines 17 versions of `Func`: <xref:System.Func%601?displayProperty=nameWithType>, <xref:System.Func%602?displayProperty=nameWithType>, <xref:System.Func%603?displayProperty=nameWithType>, and so on up through <xref:System.Func%6017?displayProperty=nameWithType>.</span></span>

## <a name="action-delegate"></a><span data-ttu-id="7a3dc-114">Delegato Action</span><span class="sxs-lookup"><span data-stu-id="7a3dc-114">Action Delegate</span></span>

<span data-ttu-id="7a3dc-115">Un delegato <xref:System.Action?displayProperty=nameWithType> incapsula un metodo (Sub in Visual Basic) che non restituisce un valore.</span><span class="sxs-lookup"><span data-stu-id="7a3dc-115">A <xref:System.Action?displayProperty=nameWithType> delegate encapsulates a method (Sub in Visual Basic) that does not return a value.</span></span> <span data-ttu-id="7a3dc-116">In una firma di tipo `Action`, i parametri di tipo rappresentano solo i parametri di input.</span><span class="sxs-lookup"><span data-stu-id="7a3dc-116">In an `Action` type signature, the type parameters represent only input parameters.</span></span> <span data-ttu-id="7a3dc-117">Come `Func`, .NET definisce 17 versioni di `Action`, da una versione priva di parametri di tipo fino a una versione con 16 parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="7a3dc-117">Like `Func`, .NET defines 17 versions of `Action`, from a version that has no type parameters up through a version that has 16 type parameters.</span></span>

## <a name="example"></a><span data-ttu-id="7a3dc-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="7a3dc-118">Example</span></span>

<span data-ttu-id="7a3dc-119">L'esempio seguente per il metodo <xref:System.Threading.Tasks.Parallel.ForEach%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%601%7D%2CSystem.Func%7B%60%600%2CSystem.Threading.Tasks.ParallelLoopState%2C%60%601%2C%60%601%7D%2CSystem.Action%7B%60%601%7D%29?displayProperty=nameWithType> mostra come esprimere entrambi i delegati Func e Action usando espressioni lambda.</span><span class="sxs-lookup"><span data-stu-id="7a3dc-119">The following example for the <xref:System.Threading.Tasks.Parallel.ForEach%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%601%7D%2CSystem.Func%7B%60%600%2CSystem.Threading.Tasks.ParallelLoopState%2C%60%601%2C%60%601%7D%2CSystem.Action%7B%60%601%7D%29?displayProperty=nameWithType> method shows how to express both Func and Action delegates by using lambda expressions.</span></span>

[!code-csharp[System.Threading.Tasks.Parallel#02](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.threading.tasks.parallel/cs/parallelforeach.cs#02)]
[!code-vb[System.Threading.Tasks.Parallel#02](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.threading.tasks.parallel/vb/parallelforeach.vb#02)]

## <a name="see-also"></a><span data-ttu-id="7a3dc-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a3dc-120">See also</span></span>

- [<span data-ttu-id="7a3dc-121">Programmazione parallela</span><span class="sxs-lookup"><span data-stu-id="7a3dc-121">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)
