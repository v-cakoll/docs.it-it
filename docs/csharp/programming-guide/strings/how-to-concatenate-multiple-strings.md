---
title: "Procedura: concatenare più stringhe (Guida per programmatori C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- joining strings [C#]
- concatenating strings [C#]
- strings [C#], concatenation
ms.assetid: 8e16736f-4096-4f3f-be0f-9d4c3ff63520
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ca240523e2483289e11433fd58d9630a31721b33
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-concatenate-multiple-strings-c-programming-guide"></a><span data-ttu-id="ce4e4-102">Procedura: concatenare più stringhe (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="ce4e4-102">How to: Concatenate Multiple Strings (C# Programming Guide)</span></span>
<span data-ttu-id="ce4e4-103">La *concatenazione* è il processo di aggiunta di una stringa alla fine di un'altra stringa.</span><span class="sxs-lookup"><span data-stu-id="ce4e4-103">*Concatenation* is the process of appending one string to the end of another string.</span></span> <span data-ttu-id="ce4e4-104">Quando si concatenano valori letterali stringa o costanti di stringa usando l'operatore `+`, il compilatore crea una singola stringa.</span><span class="sxs-lookup"><span data-stu-id="ce4e4-104">When you concatenate string literals or string constants by using the `+` operator, the compiler creates a single string.</span></span> <span data-ttu-id="ce4e4-105">Non viene eseguita alcuna concatenazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ce4e4-105">No run time concatenation occurs.</span></span> <span data-ttu-id="ce4e4-106">Le variabili di stringa tuttavia possono essere concatenate solo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ce4e4-106">However, string variables can be concatenated only at run time.</span></span> <span data-ttu-id="ce4e4-107">In questo caso, è necessario comprendere le implicazioni dei vari approcci sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="ce4e4-107">In this case, you should understand the performance implications of the various approaches.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce4e4-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="ce4e4-108">Example</span></span>  
 <span data-ttu-id="ce4e4-109">L'esempio seguente illustra come suddividere un valore letterale stringa lungo in stringhe più piccole, per migliorare la leggibilità nel codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="ce4e4-109">The following example shows how to split a long string literal into smaller strings in order to improve readability in the source code.</span></span> <span data-ttu-id="ce4e4-110">Queste parti verranno concatenate in una singola stringa in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="ce4e4-110">These parts will be concatenated into a single string at compile time.</span></span> <span data-ttu-id="ce4e4-111">Non c'è alcun impatto sulle prestazioni in fase di esecuzione, indipendentemente dal numero di stringhe coinvolte.</span><span class="sxs-lookup"><span data-stu-id="ce4e4-111">There is no run time performance cost regardless of the number of strings involved.</span></span>  
  
 [!code-csharp[csProgGuideStrings#30](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="ce4e4-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="ce4e4-112">Example</span></span>  
 <span data-ttu-id="ce4e4-113">Per concatenare le variabili di stringa, è possibile usare gli operatori `+` o `+=` oppure i metodi <xref:System.String.Concat%2A?displayProperty=nameWithType>, <xref:System.String.Format%2A?displayProperty=nameWithType> o <xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ce4e4-113">To concatenate string variables, you can use the `+` or `+=` operators, or the <xref:System.String.Concat%2A?displayProperty=nameWithType>, <xref:System.String.Format%2A?displayProperty=nameWithType> or <xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="ce4e4-114">L'operatore `+` è facile da usare e rende il codice intuitivo.</span><span class="sxs-lookup"><span data-stu-id="ce4e4-114">The `+` operator is easy to use and makes for intuitive code.</span></span> <span data-ttu-id="ce4e4-115">Anche se si usano diversi operatori + in un'unica istruzione, il contenuto della stringa viene copiato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="ce4e4-115">Even if you use several + operators in one statement, the string content is copied only once.</span></span> <span data-ttu-id="ce4e4-116">Se però si ripete l'operazione più volte, ad esempio in un ciclo, potrebbero verificarsi problemi di efficienza.</span><span class="sxs-lookup"><span data-stu-id="ce4e4-116">But if you repeat this operation multiple times, for example in a loop, it might cause efficiency problems.</span></span> <span data-ttu-id="ce4e4-117">Ad esempio, si noti il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="ce4e4-117">For example, note the following code:</span></span>  
  
 [!code-csharp[csProgGuideStrings#23](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_2.cs)]  
  
> [!NOTE]
>  <span data-ttu-id="ce4e4-118">Nelle operazioni di concatenazione di stringhe il compilatore C# tratta una stringa Null come se fosse una stringa vuota, ma non converte il valore della stringa Null originale.</span><span class="sxs-lookup"><span data-stu-id="ce4e4-118">In string concatenation operations, the C# compiler treats a null string the same as an empty string, but it does not convert the value of the original null string.</span></span>  
  
 <span data-ttu-id="ce4e4-119">Se non si deve concatenare un elevato numero di stringhe (ad esempio, in un ciclo), il costo in termini di prestazioni di questo codice è probabilmente poco rilevante.</span><span class="sxs-lookup"><span data-stu-id="ce4e4-119">If you are not concatenating large numbers of strings (for example, in a loop), the performance cost of this code is probably not significant.</span></span> <span data-ttu-id="ce4e4-120">Lo stesso vale per i metodi <xref:System.String.Concat%2A?displayProperty=nameWithType> e <xref:System.String.Format%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ce4e4-120">The same is true for the <xref:System.String.Concat%2A?displayProperty=nameWithType> and <xref:System.String.Format%2A?displayProperty=nameWithType> methods.</span></span>  
  
 <span data-ttu-id="ce4e4-121">Tuttavia, quando le prestazioni sono importanti, è sempre opportuno usare la classe <xref:System.Text.StringBuilder> per concatenare le stringhe.</span><span class="sxs-lookup"><span data-stu-id="ce4e4-121">However, when performance is important, you should always use the <xref:System.Text.StringBuilder> class to concatenate strings.</span></span> <span data-ttu-id="ce4e4-122">Il codice seguente usa il metodo <xref:System.Text.StringBuilder.Append%2A> della classe <xref:System.Text.StringBuilder> per concatenare le stringhe senza l'effetto di concatenazione dell'operatore `+`.</span><span class="sxs-lookup"><span data-stu-id="ce4e4-122">The following code uses the <xref:System.Text.StringBuilder.Append%2A> method of the <xref:System.Text.StringBuilder> class to concatenate strings without the chaining effect of the `+` operator.</span></span>  
  
 [!code-csharp[csProgGuideStrings#22](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_3.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="ce4e4-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce4e4-123">See Also</span></span>  
 <xref:System.String>  
 <xref:System.Text.StringBuilder>  
 [<span data-ttu-id="ce4e4-124">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="ce4e4-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ce4e4-125">Stringhe</span><span class="sxs-lookup"><span data-stu-id="ce4e4-125">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)
