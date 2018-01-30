---
title: "Procedura: Concatenare più stringhe (Guida di C#)"
description: Esistono diversi modi per concatenare le stringhe in C#. Di seguito sono descritte le opzioni e le motivazioni delle diverse scelte.
ms.date: 01/11/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- joining strings [C#]
- concatenating strings [C#]
- strings [C#], concatenation
ms.assetid: 8e16736f-4096-4f3f-be0f-9d4c3ff63520
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a4bc5e04edba48065746b96841b628ec5843c5e9
ms.sourcegitcommit: f28752eab00d2bd97e971542c0f49ce63cfbc239
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2018
---
# <a name="how-to-concatenate-multiple-strings-c-guide"></a><span data-ttu-id="231eb-104">Procedura: Concatenare più stringhe (Guida di C#)</span><span class="sxs-lookup"><span data-stu-id="231eb-104">How to: Concatenate Multiple Strings (C# Guide)</span></span>

<span data-ttu-id="231eb-105">La *concatenazione* è il processo di aggiunta di una stringa alla fine di un'altra stringa.</span><span class="sxs-lookup"><span data-stu-id="231eb-105">*Concatenation* is the process of appending one string to the end of another string.</span></span> <span data-ttu-id="231eb-106">Le stringhe vengono concatenate usando l'operatore +.</span><span class="sxs-lookup"><span data-stu-id="231eb-106">You concatenate strings by using the + operator.</span></span> <span data-ttu-id="231eb-107">Per i valori letterali e le costanti di stringa, la concatenazione viene eseguita in fase di compilazione; non viene eseguita alcuna concatenazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="231eb-107">For string literals and string constants, concatenation occurs at compile time; no run-time concatenation occurs.</span></span> <span data-ttu-id="231eb-108">Per le variabili di stringa, la concatenazione viene eseguita solo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="231eb-108">For string variables, concatenation occurs only at run time.</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="231eb-109">L'esempio seguente usa la concatenazione per suddividere un valore letterale di stringa lungo in stringhe più piccole per migliorare la leggibilità nel codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="231eb-109">The following example uses concatenation to split a long string literal into smaller strings in order to improve readability in the source code.</span></span> <span data-ttu-id="231eb-110">Queste parti verranno concatenate in una singola stringa in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="231eb-110">These parts will be concatenated into a single string at compile time.</span></span> <span data-ttu-id="231eb-111">Non c'è alcun impatto sulle prestazioni in fase di esecuzione, indipendentemente dal numero di stringhe coinvolte.</span><span class="sxs-lookup"><span data-stu-id="231eb-111">There is no run-time performance cost regardless of the number of strings involved.</span></span>  
  
 [!code-csharp-interactive[Combining strings at compile time](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#1)]  
  

<span data-ttu-id="231eb-112">Per concatenare le variabili di stringa, è possibile usare gli operatori `+` o `+=`, l'[interpolazione d stringa](../tutorials/string-interpolation.md) oppure i metodi <xref:System.String.Concat%2A?displayProperty=nameWithType>, <xref:System.String.Format%2A?displayProperty=nameWithType> o <xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="231eb-112">To concatenate string variables, you can use the `+` or `+=` operators, [string interpolation](../tutorials/string-interpolation.md) or the <xref:System.String.Concat%2A?displayProperty=nameWithType>, <xref:System.String.Format%2A?displayProperty=nameWithType> or <xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="231eb-113">L'operatore `+` è facile da usare e rende il codice intuitivo.</span><span class="sxs-lookup"><span data-stu-id="231eb-113">The `+` operator is easy to use and makes for intuitive code.</span></span> <span data-ttu-id="231eb-114">Anche se si usano diversi operatori + in un'unica istruzione, il contenuto della stringa viene copiato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="231eb-114">Even if you use several + operators in one statement, the string content is copied only once.</span></span> <span data-ttu-id="231eb-115">Il codice seguente mostra due esempi di utilizzo dell'operatore `+` per concatenare le stringhe:</span><span class="sxs-lookup"><span data-stu-id="231eb-115">The following code shows two examples of using the `+` operator to concatenate strings:</span></span>

[!code-csharp-interactive[combining strings using +](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#2)]  

<span data-ttu-id="231eb-116">In alcune espressioni risulta più semplice concatenare le stringhe usando l'interpolazione di stringa, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="231eb-116">In some expressions, it is easier to concatenate strings using string interpolation, as the following code shows:</span></span>
  
[!code-csharp-interactive[building strings using string interpolation](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#3)]  
  
> [!NOTE]
>  <span data-ttu-id="231eb-117">Nelle operazioni di concatenazione di stringhe il compilatore C# tratta una stringa Null come se fosse una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="231eb-117">In string concatenation operations, the C# compiler treats a null string the same as an empty string.</span></span>

<span data-ttu-id="231eb-118">Altri metodi per concatenare le stringhe sono <xref:System.String.Concat%2A?displayProperty=nameWithType> e <xref:System.String.Format%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="231eb-118">Other methods to concatenate strings are <xref:System.String.Concat%2A?displayProperty=nameWithType> and <xref:System.String.Format%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="231eb-119">Questi metodi sono utili quando si compila una stringa da un numero ridotto di stringhe dei componenti.</span><span class="sxs-lookup"><span data-stu-id="231eb-119">These methods work well when you are building a string from a small number of component strings.</span></span> <span data-ttu-id="231eb-120">Questi metodi sono particolarmente adatti quando si conosce il numero di stringhe incluso nella stringa concatenata.</span><span class="sxs-lookup"><span data-stu-id="231eb-120">These methdos are also a great choice when you know the number of strings that make up your concatenated string.</span></span>

<span data-ttu-id="231eb-121">In altri casi è possibile combinare le stringhe in un ciclo, se non si conosce il numero di stringhe di origine da combinare e il numero effettivo di stringhe di origine potrebbe essere elevato.</span><span class="sxs-lookup"><span data-stu-id="231eb-121">In other cases you may be combining strings in a loop, where you don't know how many source strings you are combining, and the actual number of source strings may be quite large.</span></span> <span data-ttu-id="231eb-122">La classe <xref:System.Text.StringBuilder> è stata progettata per questi scenari.</span><span class="sxs-lookup"><span data-stu-id="231eb-122">The <xref:System.Text.StringBuilder> class was designed for these scenarios.</span></span> <span data-ttu-id="231eb-123">Il codice seguente usa il metodo <xref:System.Text.StringBuilder.Append%2A> della classe <xref:System.Text.StringBuilder> per concatenare le stringhe.</span><span class="sxs-lookup"><span data-stu-id="231eb-123">The following code uses the <xref:System.Text.StringBuilder.Append%2A> method of the <xref:System.Text.StringBuilder> class to concatenate strings.</span></span>  
  
[!code-csharp-interactive[string concatenation using string builder](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#4)]  

<span data-ttu-id="231eb-124">Per altre informazioni, vedere le [ragioni per cui scegliere la concatenazione di stringhe o la classe `StringBuilder`](xref:System.Text.StringBuilder#StringAndSB)</span><span class="sxs-lookup"><span data-stu-id="231eb-124">You can read more about the [reasons to choose string concatenation or the `StringBuilder` class](xref:System.Text.StringBuilder#StringAndSB)</span></span>

<span data-ttu-id="231eb-125">Un'altra opzione per unire le stringhe di una raccolta consiste nell'usare [LINQ](../programming-guide/concepts/linq/index.md) e il metodo <xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="231eb-125">Another option to join strings from a collection is to use [LINQ](../programming-guide/concepts/linq/index.md) and the <xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="231eb-126">Questo metodo combina le stringhe di origine usando un'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="231eb-126">This method combines the source strings using a lambda expression.</span></span> <span data-ttu-id="231eb-127">L'espressione lambda esegue le operazioni necessarie per aggiungere ogni stringa all'accumulo esistente.</span><span class="sxs-lookup"><span data-stu-id="231eb-127">The lambda expression does the work to add each string to the existing accumulation.</span></span> <span data-ttu-id="231eb-128">L'esempio seguente combina una matrice di parole aggiungendo uno spazio tra ogni parola nella matrice:</span><span class="sxs-lookup"><span data-stu-id="231eb-128">The following example combines an array of words by adding a space between each word in the array:</span></span>

[!code-csharp-interactive[string concatenation using LINQ expressions](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#5)]  


## <a name="see-also"></a><span data-ttu-id="231eb-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="231eb-129">See Also</span></span>  
 <xref:System.String>  
 <xref:System.Text.StringBuilder>  
 [<span data-ttu-id="231eb-130">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="231eb-130">C# Programming Guide</span></span>](../programming-guide/index.md)  
 [<span data-ttu-id="231eb-131">Stringhe</span><span class="sxs-lookup"><span data-stu-id="231eb-131">Strings</span></span>](../programming-guide/strings/index.md)
