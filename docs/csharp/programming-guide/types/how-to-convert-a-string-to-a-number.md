---
title: 'Procedura: Convertire una stringa in un numero - Guida per programmatori C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [C#]
- conversions [C#], string to int
- converting strings to int [C#]
- strings [C#], converting to int
ms.assetid: 467b9979-86ee-4afd-b734-30299cda91e3
ms.openlocfilehash: d7971bfb4b6f96a2d8efb9c09f96c0bd2856b9d0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54528719"
---
# <a name="how-to-convert-a-string-to-a-number-c-programming-guide"></a><span data-ttu-id="a0e03-102">Procedura: Convertire una stringa in un numero (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="a0e03-102">How to: Convert a String to a Number (C# Programming Guide)</span></span>
<span data-ttu-id="a0e03-103">È possibile convertire una [stringa`TryParse` in un numero usando i metodi della classe ](../../../csharp/language-reference/keywords/string.md) o usando il metodo <xref:System.Convert> presente nei diversi tipi numerici (int, long, float e così via).</span><span class="sxs-lookup"><span data-stu-id="a0e03-103">You can convert a [string](../../../csharp/language-reference/keywords/string.md) to a number by using methods in the <xref:System.Convert> class or by using the `TryParse` method found on the various numeric types (int, long, float, etc.).</span></span>  
  
 <span data-ttu-id="a0e03-104">Se si ha una stringa, è leggermente più efficiente e semplice chiamare un metodo `TryParse` (ad esempio, [`int.TryParse("11", out number)`](xref:System.Int32.TryParse%2A)).</span><span class="sxs-lookup"><span data-stu-id="a0e03-104">If you have a string, it is slightly more efficient and straightforward to call a `TryParse` method (for example, [`int.TryParse("11", out number)`](xref:System.Int32.TryParse%2A)).</span></span>  <span data-ttu-id="a0e03-105">L'uso di un metodo <xref:System.Convert> è più utile per gli oggetti generali che implementano <xref:System.IConvertible>.</span><span class="sxs-lookup"><span data-stu-id="a0e03-105">Using a <xref:System.Convert> method is more useful for general objects that implement <xref:System.IConvertible>.</span></span>  
  
 <span data-ttu-id="a0e03-106">È possibile usare i metodi `Parse` o `TryParse` sul tipo numerico che si prevede sia contenuto nella stringa, ad esempio il tipo <xref:System.Int32?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a0e03-106">You can use `Parse` or `TryParse` methods on the numeric type you expect the string contains, such as the <xref:System.Int32?displayProperty=nameWithType> type.</span></span>  <span data-ttu-id="a0e03-107">Il metodo <xref:System.Convert.ToUInt32%2A?displayProperty=nameWithType> utilizza il metodo <xref:System.Int32.Parse%2A> internamente.</span><span class="sxs-lookup"><span data-stu-id="a0e03-107">The <xref:System.Convert.ToUInt32%2A?displayProperty=nameWithType> method uses <xref:System.Int32.Parse%2A> internally.</span></span>  <span data-ttu-id="a0e03-108">Se il formato della stringa non è valido, il metodo `Parse` genera un'eccezione, mentre il metodo `TryParse` restituisce [false](../../../csharp/language-reference/keywords/false.md).</span><span class="sxs-lookup"><span data-stu-id="a0e03-108">If the string is not in a valid format, `Parse` throws an exception whereas `TryParse` returns [false](../../../csharp/language-reference/keywords/false.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0e03-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="a0e03-109">Example</span></span>  
 <span data-ttu-id="a0e03-110">I metodi `Parse` e `TryParse` ignorano lo spazio vuoto all'inizio e alla fine della stringa, ma tutti gli altri devono essere caratteri che costituiscono il tipo numerico appropriato (int, long, ulong, float, decimal e così via).</span><span class="sxs-lookup"><span data-stu-id="a0e03-110">The `Parse` and `TryParse` methods ignore white space at the beginning and at the end of the string, but all other characters must be characters that form the appropriate numeric type (int, long, ulong, float, decimal, etc.).</span></span>  <span data-ttu-id="a0e03-111">Gli spazi vuoti all'interno dei caratteri che costituiscono il numero generano un errore.</span><span class="sxs-lookup"><span data-stu-id="a0e03-111">Any white space within the characters that form the number cause an error.</span></span>  <span data-ttu-id="a0e03-112">Ad esempio, è possibile usare `decimal.TryParse` per analizzare "10", "10,3", "  10  ", ma non è possibile usare questo metodo per analizzare 10 in "10X", "1 0" (si noti lo spazio), "10 ,3" (si noti lo spazio), "10e1" (in questo caso funziona `float.TryParse`) e così via.</span><span class="sxs-lookup"><span data-stu-id="a0e03-112">For example, you can use `decimal.TryParse` to parse "10", "10.3", "  10  ", but you cannot use this method to parse 10 from "10X", "1 0" (note space), "10 .3" (note space), "10e1" (`float.TryParse` works here), and so on.</span></span>  
  
 <span data-ttu-id="a0e03-113">Negli esempi riportati di seguito vengono illustrate chiamate con esito positivo e negativo ai metodi `Parse` e `TryParse`.</span><span class="sxs-lookup"><span data-stu-id="a0e03-113">The examples below demonstrate both successful and unsuccessful calls to `Parse` and `TryParse`.</span></span>  
  
 [!code-csharp[csProgGuideTypes#5555](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_1.cs)]  
[!code-csharp[csProgGuideTypes#25](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_2.cs)]  
[!code-csharp[csProgGuideTypes#26](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_3.cs)]  
[!code-csharp[csProgGuideTypes#27](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_4.cs)]  
[!code-csharp[csProgGuideTypes#28](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_5.cs)]  
[!code-csharp[csProgGuideTypes#100](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_6.cs)]  
  
## <a name="example"></a><span data-ttu-id="a0e03-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="a0e03-114">Example</span></span>  
 <span data-ttu-id="a0e03-115">Nella tabella seguente sono elencati alcuni dei metodi della classe <xref:System.Convert> che è possibile usare.</span><span class="sxs-lookup"><span data-stu-id="a0e03-115">The following table lists some of the methods from the <xref:System.Convert> class that you can use.</span></span>  
  
|<span data-ttu-id="a0e03-116">Tipo numerico</span><span class="sxs-lookup"><span data-stu-id="a0e03-116">Numeric Type</span></span>|<span data-ttu-id="a0e03-117">Metodo</span><span class="sxs-lookup"><span data-stu-id="a0e03-117">Method</span></span>|  
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
  
 <span data-ttu-id="a0e03-118">In questo esempio viene chiamato il metodo <xref:System.Convert.ToInt32%28System.String%29?displayProperty=nameWithType> per convertire un tipo [string](../../../csharp/language-reference/keywords/string.md) di input in un tipo [int](../../../csharp/language-reference/keywords/int.md).</span><span class="sxs-lookup"><span data-stu-id="a0e03-118">This example calls the <xref:System.Convert.ToInt32%28System.String%29?displayProperty=nameWithType> method to convert an input [string](../../../csharp/language-reference/keywords/string.md) to an [int](../../../csharp/language-reference/keywords/int.md) .</span></span> <span data-ttu-id="a0e03-119">Il codice rileva le due eccezioni più comuni che possono essere generate da questo metodo, <xref:System.FormatException> e <xref:System.OverflowException>.</span><span class="sxs-lookup"><span data-stu-id="a0e03-119">The code catches the two most common exceptions that can be thrown by this method, <xref:System.FormatException> and <xref:System.OverflowException>.</span></span> <span data-ttu-id="a0e03-120">Se è possibile incrementare il numero senza provocare l'overflow nella posizione di archiviazione di Integer, il programma aggiunge 1 al risultato e stampa l'output.</span><span class="sxs-lookup"><span data-stu-id="a0e03-120">If the number can be incremented without overflowing the integer storage location, the program adds 1 to the result and prints the output.</span></span>  
  
 [!code-csharp[csProgGuideTypes#5555](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_1.cs)]  
[!code-csharp[csProgGuideTypes#24](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_7.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="a0e03-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0e03-121">See also</span></span>

- [<span data-ttu-id="a0e03-122">Tipi</span><span class="sxs-lookup"><span data-stu-id="a0e03-122">Types</span></span>](../../../csharp/programming-guide/types/index.md)
- [<span data-ttu-id="a0e03-123">Procedura: Determinare se una stringa rappresenta un valore numerico</span><span class="sxs-lookup"><span data-stu-id="a0e03-123">How to: Determine Whether a String Represents a Numeric Value</span></span>](../../../csharp/programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md)
- <span data-ttu-id="a0e03-124">[.NET Framework 4 Formatting Utility](https://code.msdn.microsoft.com/NET-Framework-4-Formatting-9c4dae8d) (Utilità di formattazione in .NET Framework 4)</span><span class="sxs-lookup"><span data-stu-id="a0e03-124">[.NET Framework 4 Formatting Utility](https://code.msdn.microsoft.com/NET-Framework-4-Formatting-9c4dae8d)</span></span>
