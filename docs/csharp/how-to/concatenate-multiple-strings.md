---
title: Come concatenare più stringhe (Guida di C
description: Esistono diversi modi per concatenare le stringhe in C#. Di seguito sono descritte le opzioni e le motivazioni delle diverse scelte.
ms.date: 02/20/2018
helpviewer_keywords:
- joining strings [C#]
- concatenating strings [C#]
- strings [C#], concatenation
ms.assetid: 8e16736f-4096-4f3f-be0f-9d4c3ff63520
ms.openlocfilehash: 87ec5104f36d0c6cce12037e70dacf2752ef5e62
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121048"
---
# <a name="how-to-concatenate-multiple-strings-c-guide"></a><span data-ttu-id="0c5d4-104">Come concatenare più stringhe (Guida di C</span><span class="sxs-lookup"><span data-stu-id="0c5d4-104">How to concatenate multiple strings (C# Guide)</span></span>

<span data-ttu-id="0c5d4-105">La *concatenazione* è il processo di aggiunta di una stringa alla fine di un'altra stringa.</span><span class="sxs-lookup"><span data-stu-id="0c5d4-105">*Concatenation* is the process of appending one string to the end of another string.</span></span> <span data-ttu-id="0c5d4-106">Le stringhe vengono concatenate usando l'operatore `+`.</span><span class="sxs-lookup"><span data-stu-id="0c5d4-106">You concatenate strings by using the `+` operator.</span></span> <span data-ttu-id="0c5d4-107">Per i valori letterali e le costanti di stringa, la concatenazione viene eseguita in fase di compilazione; non viene eseguita alcuna concatenazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0c5d4-107">For string literals and string constants, concatenation occurs at compile time; no run-time concatenation occurs.</span></span> <span data-ttu-id="0c5d4-108">Per le variabili di stringa, la concatenazione viene eseguita solo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0c5d4-108">For string variables, concatenation occurs only at run time.</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="0c5d4-109">L'esempio seguente usa la concatenazione per suddividere un valore letterale di stringa lungo in stringhe più piccole per migliorare la leggibilità nel codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="0c5d4-109">The following example uses concatenation to split a long string literal into smaller strings in order to improve readability in the source code.</span></span> <span data-ttu-id="0c5d4-110">Queste parti sono concatenate in una singola stringa in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="0c5d4-110">These parts are concatenated into a single string at compile time.</span></span> <span data-ttu-id="0c5d4-111">Non c'è alcun impatto sulle prestazioni in fase di esecuzione, indipendentemente dal numero di stringhe coinvolte.</span><span class="sxs-lookup"><span data-stu-id="0c5d4-111">There is no run-time performance cost regardless of the number of strings involved.</span></span>  
  
 [!code-csharp-interactive[Combining strings at compile time](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#1)]  

<span data-ttu-id="0c5d4-112">Per concatenare le variabili stringa, è possibile utilizzare gli `+` operatori `+=` o , l'interpolazione di [stringa](../language-reference/tokens/interpolated.md) o i <xref:System.String.Format%2A?displayProperty=nameWithType>metodi , <xref:System.String.Concat%2A?displayProperty=nameWithType>, <xref:System.String.Join%2A?displayProperty=nameWithType> o <xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="0c5d4-112">To concatenate string variables, you can use the `+` or `+=` operators, [string interpolation](../language-reference/tokens/interpolated.md) or the <xref:System.String.Format%2A?displayProperty=nameWithType>, <xref:System.String.Concat%2A?displayProperty=nameWithType>, <xref:System.String.Join%2A?displayProperty=nameWithType> or <xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="0c5d4-113">L'operatore `+` è facile da usare e rende il codice intuitivo.</span><span class="sxs-lookup"><span data-stu-id="0c5d4-113">The `+` operator is easy to use and makes for intuitive code.</span></span> <span data-ttu-id="0c5d4-114">Anche se si usano diversi operatori `+` in un'unica istruzione, il contenuto della stringa viene copiato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="0c5d4-114">Even if you use several `+` operators in one statement, the string content is copied only once.</span></span> <span data-ttu-id="0c5d4-115">Il codice seguente mostra esempi dell'uso degli operatori `+` e `+=` per concatenare le stringhe:</span><span class="sxs-lookup"><span data-stu-id="0c5d4-115">The following code shows examples of using the `+` and `+=` operators to concatenate strings:</span></span>

[!code-csharp-interactive[combining strings using +](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#2)]  

<span data-ttu-id="0c5d4-116">In alcune espressioni risulta più semplice concatenare le stringhe usando l'interpolazione di stringhe, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="0c5d4-116">In some expressions, it's easier to concatenate strings using string interpolation, as the following code shows:</span></span>
  
[!code-csharp-interactive[building strings using string interpolation](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#3)]  
  
> [!NOTE]
> <span data-ttu-id="0c5d4-117">Nelle operazioni di concatenazione di stringhe il compilatore C# tratta una stringa Null come se fosse una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="0c5d4-117">In string concatenation operations, the C# compiler treats a null string the same as an empty string.</span></span>

<span data-ttu-id="0c5d4-118">Un altro metodo per concatenare le stringhe è <xref:System.String.Format%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0c5d4-118">Other method to concatenate strings is <xref:System.String.Format%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0c5d4-119">Questo metodo è utile quando si compila una stringa da un numero ridotto di stringhe dei componenti.</span><span class="sxs-lookup"><span data-stu-id="0c5d4-119">This method works well when you are building a string from a small number of component strings.</span></span>

<span data-ttu-id="0c5d4-120">In altri casi è possibile combinare le stringhe in un ciclo, se non si conosce il numero di stringhe di origine da combinare e il numero effettivo di stringhe di origine potrebbe essere elevato.</span><span class="sxs-lookup"><span data-stu-id="0c5d4-120">In other cases you may be combining strings in a loop, where you don't know how many source strings you are combining, and the actual number of source strings may be quite large.</span></span> <span data-ttu-id="0c5d4-121">La classe <xref:System.Text.StringBuilder> è stata progettata per questi scenari.</span><span class="sxs-lookup"><span data-stu-id="0c5d4-121">The <xref:System.Text.StringBuilder> class was designed for these scenarios.</span></span> <span data-ttu-id="0c5d4-122">Il codice seguente usa il metodo <xref:System.Text.StringBuilder.Append%2A> della classe <xref:System.Text.StringBuilder> per concatenare le stringhe.</span><span class="sxs-lookup"><span data-stu-id="0c5d4-122">The following code uses the <xref:System.Text.StringBuilder.Append%2A> method of the <xref:System.Text.StringBuilder> class to concatenate strings.</span></span>  
  
[!code-csharp-interactive[string concatenation using string builder](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#4)]  

<span data-ttu-id="0c5d4-123">Ulteriori informazioni sui motivi per scegliere la [concatenazione `StringBuilder` di stringhe o la classe](xref:System.Text.StringBuilder#StringAndSB).</span><span class="sxs-lookup"><span data-stu-id="0c5d4-123">You can read more about the [reasons to choose string concatenation or the `StringBuilder` class](xref:System.Text.StringBuilder#StringAndSB).</span></span>

<span data-ttu-id="0c5d4-124">Un'altra opzione per unire le stringhe di una raccolta consiste nell'usare il metodo <xref:System.String.Concat%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0c5d4-124">Another option to join strings from a collection is to use <xref:System.String.Concat%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="0c5d4-125">Usare il metodo <xref:System.String.Join%2A?displayProperty=nameWithType> se le stringhe di origine devono essere separate da un delimitatore.</span><span class="sxs-lookup"><span data-stu-id="0c5d4-125">Use <xref:System.String.Join%2A?displayProperty=nameWithType> method if source strings should be separated by a delimeter.</span></span> <span data-ttu-id="0c5d4-126">Il codice seguente combina una matrice di parole con entrambi i metodi:</span><span class="sxs-lookup"><span data-stu-id="0c5d4-126">The following code combines an array of words using both methods:</span></span>

[!code-csharp-interactive[concatenation of string collection](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#5)]

<span data-ttu-id="0c5d4-127">Infine, è possibile usare [LINQ](../programming-guide/concepts/linq/index.md) e il metodo <xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType> per unire le stringhe di una raccolta.</span><span class="sxs-lookup"><span data-stu-id="0c5d4-127">At last, you can use [LINQ](../programming-guide/concepts/linq/index.md) and the <xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType> method to join strings from a collection.</span></span> <span data-ttu-id="0c5d4-128">Questo metodo combina le stringhe di origine usando un'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="0c5d4-128">This method combines the source strings using a lambda expression.</span></span> <span data-ttu-id="0c5d4-129">L'espressione lambda esegue le operazioni necessarie per aggiungere ogni stringa all'accumulo esistente.</span><span class="sxs-lookup"><span data-stu-id="0c5d4-129">The lambda expression does the work to add each string to the existing accumulation.</span></span> <span data-ttu-id="0c5d4-130">L'esempio seguente combina una matrice di parole aggiungendo uno spazio tra ogni parola nella matrice:</span><span class="sxs-lookup"><span data-stu-id="0c5d4-130">The following example combines an array of words by adding a space between each word in the array:</span></span>

[!code-csharp-interactive[string concatenation using LINQ expressions](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#6)]  

<span data-ttu-id="0c5d4-131">È possibile provare questi esempi esaminando il [codice di esempio](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/how-to/strings).</span><span class="sxs-lookup"><span data-stu-id="0c5d4-131">You can try these samples by looking at the [sample code](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/how-to/strings).</span></span> <span data-ttu-id="0c5d4-132">In alternativa, è possibile scaricare gli esempi [come file zip](../../../samples/snippets/csharp/how-to/strings.zip).</span><span class="sxs-lookup"><span data-stu-id="0c5d4-132">Or, you can download the samples [as a zip file](../../../samples/snippets/csharp/how-to/strings.zip).</span></span>

## <a name="see-also"></a><span data-ttu-id="0c5d4-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c5d4-133">See also</span></span>

- <xref:System.String>
- <xref:System.Text.StringBuilder>
- [<span data-ttu-id="0c5d4-134">Guida alla programmazione in C</span><span class="sxs-lookup"><span data-stu-id="0c5d4-134">C# Programming Guide</span></span>](../programming-guide/index.md)
- [<span data-ttu-id="0c5d4-135">Stringhe</span><span class="sxs-lookup"><span data-stu-id="0c5d4-135">Strings</span></span>](../programming-guide/strings/index.md)
