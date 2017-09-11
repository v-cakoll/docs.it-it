---
title: 'Procedura: convertire una stringa in un numero (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- conversions [C#]
- conversions [C#], string to int
- converting strings to int [C#]
- strings [C#], converting to int
ms.assetid: 467b9979-86ee-4afd-b734-30299cda91e3
caps.latest.revision: 34
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
ms.openlocfilehash: 08d13e40a385ce8e9011b508b04361b2e050f904
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-convert-a-string-to-a-number-c-programming-guide"></a><span data-ttu-id="619e8-102">Procedura: convertire una stringa in un numero (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="619e8-102">How to: Convert a String to a Number (C# Programming Guide)</span></span>
<span data-ttu-id="619e8-103">È possibile convertire una [stringa`TryParse` in un numero usando i metodi della classe ](../../../csharp/language-reference/keywords/string.md) o usando il metodo <xref:System.Convert> presente nei diversi tipi numerici (int, long, float e così via).</span><span class="sxs-lookup"><span data-stu-id="619e8-103">You can convert a [string](../../../csharp/language-reference/keywords/string.md) to a number by using methods in the <xref:System.Convert> class or by using the `TryParse` method found on the various numeric types (int, long, float, etc.).</span></span>  
  
 <span data-ttu-id="619e8-104">Se si dispone di una stringa, è leggermente più efficiente e semplice chiamare un metodo `TryParse` (ad esempio, `int.TryParse("11")`).</span><span class="sxs-lookup"><span data-stu-id="619e8-104">If you have a string, it is slightly more efficient and straightforward to call a `TryParse` method (for example, `int.TryParse("11")`).</span></span>  <span data-ttu-id="619e8-105">L'uso di un metodo `Convert` è più utile per gli oggetti generali che implementano <xref:System.IConvertible>.</span><span class="sxs-lookup"><span data-stu-id="619e8-105">Using a `Convert` method is more useful for general objects that implement <xref:System.IConvertible>.</span></span>  
  
 <span data-ttu-id="619e8-106">È possibile usare i metodi `Parse` o `TryParse` sul tipo numerico che si prevede sia contenuto nella stringa, ad esempio il tipo <xref:System.Int32?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="619e8-106">You can use `Parse` or `TryParse` methods on the numeric type you expect the string contains, such as the <xref:System.Int32?displayProperty=fullName> type.</span></span>  <span data-ttu-id="619e8-107">Il metodo <xref:System.Convert.ToUInt32%2A?displayProperty=fullName> utilizza il metodo <xref:System.Int32.Parse%2A> internamente.</span><span class="sxs-lookup"><span data-stu-id="619e8-107">The <xref:System.Convert.ToUInt32%2A?displayProperty=fullName> method uses <xref:System.Int32.Parse%2A> internally.</span></span>  <span data-ttu-id="619e8-108">Se il formato della stringa non è valido, il metodo `Parse` genera un'eccezione, mentre il metodo `TryParse` restituisce [false](../../../csharp/language-reference/keywords/false.md).</span><span class="sxs-lookup"><span data-stu-id="619e8-108">If the string is not in a valid format, `Parse` throws an exception whereas `TryParse` returns [false](../../../csharp/language-reference/keywords/false.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="619e8-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="619e8-109">Example</span></span>  
 <span data-ttu-id="619e8-110">I metodi `Parse` e `TryParse` ignorano lo spazio vuoto all'inizio e alla fine della stringa, ma tutti gli altri devono essere caratteri che costituiscono il tipo numerico appropriato (int, long, ulong, float, decimal e così via).</span><span class="sxs-lookup"><span data-stu-id="619e8-110">The `Parse` and `TryParse` methods ignore whitespace at the beginning and at the end of the string, but all other characters must be characters that form the appropriate numeric type (int, long, ulong, float, decimal, etc.).</span></span>  <span data-ttu-id="619e8-111">Gli spazi vuoti all'interno di caratteri che costituiscono il numero generano un errore.</span><span class="sxs-lookup"><span data-stu-id="619e8-111">Any whitespace within the characters that form the number cause an error.</span></span>  <span data-ttu-id="619e8-112">Ad esempio, è possibile usare `decimal.TryParse` per analizzare "10", "10,3", "  10  ", ma non è possibile usare questo metodo per analizzare 10 in "10X", "1 0" (si noti lo spazio), "10 ,3" (si noti lo spazio), "10e1" (in questo caso funziona `float.TryParse`) e così via.</span><span class="sxs-lookup"><span data-stu-id="619e8-112">For example, you can use `decimal.TryParse` to parse "10", "10.3", "  10  ", but you cannot use this method to parse 10 from "10X", "1 0" (note space), "10 .3" (note space), "10e1" (`float.TryParse` works here), and so on.</span></span>  
  
 <span data-ttu-id="619e8-113">Negli esempi riportati di seguito vengono illustrate chiamate con esito positivo e negativo ai metodi `Parse` e `TryParse`.</span><span class="sxs-lookup"><span data-stu-id="619e8-113">The examples below demonstrate both successful and unsuccessful calls to `Parse` and `TryParse`.</span></span>  
  
 <span data-ttu-id="619e8-114">[!code-cs[csProgGuideTypes#5555](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="619e8-114">[!code-cs[csProgGuideTypes#5555](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_1.cs)]</span></span>  
<span data-ttu-id="619e8-115">[!code-cs[csProgGuideTypes#25](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="619e8-115">[!code-cs[csProgGuideTypes#25](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_2.cs)]</span></span>  
<span data-ttu-id="619e8-116">[!code-cs[csProgGuideTypes#26](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="619e8-116">[!code-cs[csProgGuideTypes#26](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_3.cs)]</span></span>  
<span data-ttu-id="619e8-117">[!code-cs[csProgGuideTypes#27](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="619e8-117">[!code-cs[csProgGuideTypes#27](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_4.cs)]</span></span>  
<span data-ttu-id="619e8-118">[!code-cs[csProgGuideTypes#28](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="619e8-118">[!code-cs[csProgGuideTypes#28](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_5.cs)]</span></span>  
<span data-ttu-id="619e8-119">[!code-cs[csProgGuideTypes#100](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="619e8-119">[!code-cs[csProgGuideTypes#100](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_6.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="619e8-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="619e8-120">Example</span></span>  
 <span data-ttu-id="619e8-121">Nella tabella seguente sono elencati alcuni dei metodi della classe <xref:System.Convert> che è possibile usare.</span><span class="sxs-lookup"><span data-stu-id="619e8-121">The following table lists some of the methods from the <xref:System.Convert> class that you can use.</span></span>  
  
|<span data-ttu-id="619e8-122">Tipo numerico</span><span class="sxs-lookup"><span data-stu-id="619e8-122">Numeric Type</span></span>|<span data-ttu-id="619e8-123">Metodo</span><span class="sxs-lookup"><span data-stu-id="619e8-123">Method</span></span>|  
|------------------|------------|  
|`decimal`|<xref:System.Convert.ToDecimal%28System.String%29>|  
|`float`|<xref:System.Convert.ToSingle%28System.String%29>|  
|`double`|<xref:System.Convert.ToDouble%28System.String%29>|  
|`short`|<xref:System.Convert.ToInt16%28System.String%29>|  
|`int`|<xref:System.Convert.ToInt32%28System.String%29>|  
|`long`|<xref:System.Convert.ToInt64%28System.String%29>|  
|`ushort`|<xref:System.Convert.ToUInt16%28System.String%29>|  
|`uint`|<xref:System.Convert.ToUInt32%28System.String%29>|  
|`ulong`|<xref:System.Convert.ToUInt64%28System.String%29>|  
  
 <span data-ttu-id="619e8-124">In questo esempio viene chiamato il metodo <xref:System.Convert.ToInt32%28System.String%29?displayProperty=fullName> per convertire un tipo [string](../../../csharp/language-reference/keywords/string.md) di input in un tipo [int](../../../csharp/language-reference/keywords/int.md).</span><span class="sxs-lookup"><span data-stu-id="619e8-124">This example calls the <xref:System.Convert.ToInt32%28System.String%29?displayProperty=fullName> method to convert an input [string](../../../csharp/language-reference/keywords/string.md) to an [int](../../../csharp/language-reference/keywords/int.md) .</span></span> <span data-ttu-id="619e8-125">Il codice rileva le due eccezioni più comuni che possono essere generate da questo metodo, <xref:System.FormatException> e <xref:System.OverflowException>.</span><span class="sxs-lookup"><span data-stu-id="619e8-125">The code catches the two most common exceptions that can be thrown by this method, <xref:System.FormatException> and <xref:System.OverflowException>.</span></span> <span data-ttu-id="619e8-126">Se è possibile incrementare il numero senza provocare l'overflow nella posizione di archiviazione di Integer, il programma aggiunge 1 al risultato e stampa l'output.</span><span class="sxs-lookup"><span data-stu-id="619e8-126">If the number can be incremented without overflowing the integer storage location, the program adds 1 to the result and prints the output.</span></span>  
  
 <span data-ttu-id="619e8-127">[!code-cs[csProgGuideTypes#5555](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="619e8-127">[!code-cs[csProgGuideTypes#5555](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_1.cs)]</span></span>  
<span data-ttu-id="619e8-128">[!code-cs[csProgGuideTypes#24](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="619e8-128">[!code-cs[csProgGuideTypes#24](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_7.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="619e8-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="619e8-129">See Also</span></span>  
 <span data-ttu-id="619e8-130">[Tipi](../../../csharp/programming-guide/types/index.md) </span><span class="sxs-lookup"><span data-stu-id="619e8-130">[Types](../../../csharp/programming-guide/types/index.md) </span></span>  
 <span data-ttu-id="619e8-131">[Procedura: Determinare se una stringa rappresenta un valore numerico](../../../csharp/programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md) </span><span class="sxs-lookup"><span data-stu-id="619e8-131">[How to: Determine Whether a String Represents a Numeric Value](../../../csharp/programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md) </span></span>  
 <span data-ttu-id="619e8-132">[.NET Framework 4 Formatting Utility](http://code.msdn.microsoft.com/NET-Framework-4-Formatting-9c4dae8d) (Utilità di formattazione in .NET Framework 4)</span><span class="sxs-lookup"><span data-stu-id="619e8-132">[.NET Framework 4 Formatting Utility](http://code.msdn.microsoft.com/NET-Framework-4-Formatting-9c4dae8d)</span></span>

