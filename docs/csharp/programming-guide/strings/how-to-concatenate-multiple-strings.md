---
title: "Procedura: concatenare più stringhe (Guida per programmatori C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- joining strings [C#]
- concatenating strings [C#]
- strings [C#], concatenation
ms.assetid: 8e16736f-4096-4f3f-be0f-9d4c3ff63520
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b191a61258a496115a4d7045046f9b4a2dbee58c
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-concatenate-multiple-strings-c-programming-guide"></a><span data-ttu-id="724b3-102">Procedura: concatenare più stringhe (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="724b3-102">How to: Concatenate Multiple Strings (C# Programming Guide)</span></span>
<span data-ttu-id="724b3-103">La *concatenazione* è il processo di aggiunta di una stringa alla fine di un'altra stringa.</span><span class="sxs-lookup"><span data-stu-id="724b3-103">*Concatenation* is the process of appending one string to the end of another string.</span></span> <span data-ttu-id="724b3-104">Quando si concatenano valori letterali stringa o costanti di stringa usando l'operatore `+`, il compilatore crea una singola stringa.</span><span class="sxs-lookup"><span data-stu-id="724b3-104">When you concatenate string literals or string constants by using the `+` operator, the compiler creates a single string.</span></span> <span data-ttu-id="724b3-105">Non viene eseguita alcuna concatenazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="724b3-105">No run time concatenation occurs.</span></span> <span data-ttu-id="724b3-106">Le variabili di stringa tuttavia possono essere concatenate solo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="724b3-106">However, string variables can be concatenated only at run time.</span></span> <span data-ttu-id="724b3-107">In questo caso, è necessario comprendere le implicazioni dei vari approcci sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="724b3-107">In this case, you should understand the performance implications of the various approaches.</span></span>  
  
## <a name="example"></a><span data-ttu-id="724b3-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="724b3-108">Example</span></span>  
 <span data-ttu-id="724b3-109">L'esempio seguente illustra come suddividere un valore letterale stringa lungo in stringhe più piccole, per migliorare la leggibilità nel codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="724b3-109">The following example shows how to split a long string literal into smaller strings in order to improve readability in the source code.</span></span> <span data-ttu-id="724b3-110">Queste parti verranno concatenate in una singola stringa in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="724b3-110">These parts will be concatenated into a single string at compile time.</span></span> <span data-ttu-id="724b3-111">Non c'è alcun impatto sulle prestazioni in fase di esecuzione, indipendentemente dal numero di stringhe coinvolte.</span><span class="sxs-lookup"><span data-stu-id="724b3-111">There is no run time performance cost regardless of the number of strings involved.</span></span>  
  
 <span data-ttu-id="724b3-112">[!code-cs[csProgGuideStrings#30](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="724b3-112">[!code-cs[csProgGuideStrings#30](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="724b3-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="724b3-113">Example</span></span>  
 <span data-ttu-id="724b3-114">Per concatenare le variabili di stringa, è possibile usare gli operatori `+` o `+=` oppure i metodi <xref:System.String.Concat%2A?displayProperty=fullName>, <xref:System.String.Format%2A?displayProperty=fullName> o <xref:System.Text.StringBuilder.Append%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="724b3-114">To concatenate string variables, you can use the `+` or `+=` operators, or the <xref:System.String.Concat%2A?displayProperty=fullName>, <xref:System.String.Format%2A?displayProperty=fullName> or <xref:System.Text.StringBuilder.Append%2A?displayProperty=fullName> methods.</span></span> <span data-ttu-id="724b3-115">L'operatore `+` è facile da usare e rende il codice intuitivo.</span><span class="sxs-lookup"><span data-stu-id="724b3-115">The `+` operator is easy to use and makes for intuitive code.</span></span> <span data-ttu-id="724b3-116">Anche se si usano diversi operatori + in un'unica istruzione, il contenuto della stringa viene copiato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="724b3-116">Even if you use several + operators in one statement, the string content is copied only once.</span></span> <span data-ttu-id="724b3-117">Se però si ripete l'operazione più volte, ad esempio in un ciclo, potrebbero verificarsi problemi di efficienza.</span><span class="sxs-lookup"><span data-stu-id="724b3-117">But if you repeat this operation multiple times, for example in a loop, it might cause efficiency problems.</span></span> <span data-ttu-id="724b3-118">Ad esempio, si noti il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="724b3-118">For example, note the following code:</span></span>  
  
 <span data-ttu-id="724b3-119">[!code-cs[csProgGuideStrings#23](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="724b3-119">[!code-cs[csProgGuideStrings#23](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_2.cs)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="724b3-120">Nelle operazioni di concatenazione di stringhe il compilatore C# tratta una stringa Null come se fosse una stringa vuota, ma non converte il valore della stringa Null originale.</span><span class="sxs-lookup"><span data-stu-id="724b3-120">In string concatenation operations, the C# compiler treats a null string the same as an empty string, but it does not convert the value of the original null string.</span></span>  
  
 <span data-ttu-id="724b3-121">Se non si deve concatenare un elevato numero di stringhe (ad esempio, in un ciclo), il costo in termini di prestazioni di questo codice è probabilmente poco rilevante.</span><span class="sxs-lookup"><span data-stu-id="724b3-121">If you are not concatenating large numbers of strings (for example, in a loop), the performance cost of this code is probably not significant.</span></span> <span data-ttu-id="724b3-122">Lo stesso vale per i metodi <xref:System.String.Concat%2A?displayProperty=fullName> e <xref:System.String.Format%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="724b3-122">The same is true for the <xref:System.String.Concat%2A?displayProperty=fullName> and <xref:System.String.Format%2A?displayProperty=fullName> methods.</span></span>  
  
 <span data-ttu-id="724b3-123">Tuttavia, quando le prestazioni sono importanti, è sempre opportuno usare la classe <xref:System.Text.StringBuilder> per concatenare le stringhe.</span><span class="sxs-lookup"><span data-stu-id="724b3-123">However, when performance is important, you should always use the <xref:System.Text.StringBuilder> class to concatenate strings.</span></span> <span data-ttu-id="724b3-124">Il codice seguente usa il metodo <xref:System.Text.StringBuilder.Append%2A> della classe <xref:System.Text.StringBuilder> per concatenare le stringhe senza l'effetto di concatenazione dell'operatore `+`.</span><span class="sxs-lookup"><span data-stu-id="724b3-124">The following code uses the <xref:System.Text.StringBuilder.Append%2A> method of the <xref:System.Text.StringBuilder> class to concatenate strings without the chaining effect of the `+` operator.</span></span>  
  
 <span data-ttu-id="724b3-125">[!code-cs[csProgGuideStrings#22](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="724b3-125">[!code-cs[csProgGuideStrings#22](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-concatenate-multiple-strings_3.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="724b3-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="724b3-126">See Also</span></span>  
 <span data-ttu-id="724b3-127"><xref:System.String></span><span class="sxs-lookup"><span data-stu-id="724b3-127"><xref:System.String></span></span>   
 <span data-ttu-id="724b3-128"><xref:System.Text.StringBuilder></span><span class="sxs-lookup"><span data-stu-id="724b3-128"><xref:System.Text.StringBuilder></span></span>   
 <span data-ttu-id="724b3-129">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="724b3-129">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="724b3-130">Stringhe</span><span class="sxs-lookup"><span data-stu-id="724b3-130">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)

