---
title: 'Procedura: eseguire la conversione tra stringhe esadecimali e tipi numerici (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- hexadecimal strings [C#], converting to numeric type
- conversions [C#], hexidecimal strings
- strings [C#], converting hexadecimal strings
- hexadecimal strings [C#]
ms.assetid: 7115c49f-7d1d-40c3-8bd9-aae0cc1d46b6
caps.latest.revision: 19
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
ms.openlocfilehash: 312b18e6bf30ace166435e51b1b83937b5c6bf38
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-convert-between-hexadecimal-strings-and-numeric-types-c-programming-guide"></a><span data-ttu-id="8839d-102">Procedura: eseguire la conversione tra stringhe esadecimali e tipi numerici (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="8839d-102">How to: Convert Between Hexadecimal Strings and Numeric Types (C# Programming Guide)</span></span>
<span data-ttu-id="8839d-103">In questi esempi viene mostrato come effettuare le seguenti attività:</span><span class="sxs-lookup"><span data-stu-id="8839d-103">These examples show you how to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="8839d-104">Ottenere il valore esadecimale di ogni carattere in un oggetto [string](../../../csharp/language-reference/keywords/string.md).</span><span class="sxs-lookup"><span data-stu-id="8839d-104">Obtain the hexadecimal value of each character in a [string](../../../csharp/language-reference/keywords/string.md).</span></span>  
  
-   <span data-ttu-id="8839d-105">Ottenere l'oggetto [char](../../../csharp/language-reference/keywords/char.md) che corrisponde a ogni valore in una stringa esadecimale.</span><span class="sxs-lookup"><span data-stu-id="8839d-105">Obtain the [char](../../../csharp/language-reference/keywords/char.md) that corresponds to each value in a hexadecimal string.</span></span>  
  
-   <span data-ttu-id="8839d-106">Convertire un oggetto `string` esadecimale in un oggetto [int](../../../csharp/language-reference/keywords/int.md).</span><span class="sxs-lookup"><span data-stu-id="8839d-106">Convert a hexadecimal `string` to an [int](../../../csharp/language-reference/keywords/int.md).</span></span>  
  
-   <span data-ttu-id="8839d-107">Convertire un oggetto `string` esadecimale in un oggetto [float](../../../csharp/language-reference/keywords/float.md).</span><span class="sxs-lookup"><span data-stu-id="8839d-107">Convert a hexadecimal `string` to a [float](../../../csharp/language-reference/keywords/float.md).</span></span>  
  
-   <span data-ttu-id="8839d-108">Convertire una matrice di [byte](../../../csharp/language-reference/keywords/byte.md) in un oggetto `string` esadecimale.</span><span class="sxs-lookup"><span data-stu-id="8839d-108">Convert a [byte](../../../csharp/language-reference/keywords/byte.md) array to a hexadecimal `string`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8839d-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="8839d-109">Example</span></span>  
 <span data-ttu-id="8839d-110">Questo esempio restituisce il valore esadecimale di ogni carattere in un oggetto `string`.</span><span class="sxs-lookup"><span data-stu-id="8839d-110">This example outputs the hexadecimal value of each character in a `string`.</span></span> <span data-ttu-id="8839d-111">Prima viene analizzato l'oggetto `string` in una matrice di caratteri.</span><span class="sxs-lookup"><span data-stu-id="8839d-111">First it parses the `string` to an array of characters.</span></span> <span data-ttu-id="8839d-112">Poi viene chiamato <xref:System.Convert.ToInt32%28System.Char%29> in ogni carattere per ottenere il rispettivo valore numerico.</span><span class="sxs-lookup"><span data-stu-id="8839d-112">Then it calls <xref:System.Convert.ToInt32%28System.Char%29> on each character to obtain its numeric value.</span></span> <span data-ttu-id="8839d-113">Il numero viene infine formattato come esadecimale in un oggetto `string`.</span><span class="sxs-lookup"><span data-stu-id="8839d-113">Finally, it formats the number as its hexadecimal representation in a `string`.</span></span>  
  
 <span data-ttu-id="8839d-114">[!code-cs[csProgGuideTypes#30](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="8839d-114">[!code-cs[csProgGuideTypes#30](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="8839d-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="8839d-115">Example</span></span>  
 <span data-ttu-id="8839d-116">Questo esempio analizza un oggetto `string` di valori esadecimali e restituisce il carattere corrispondente a ogni valore esadecimale.</span><span class="sxs-lookup"><span data-stu-id="8839d-116">This example parses a `string` of hexadecimal values and outputs the character corresponding to each hexadecimal value.</span></span> <span data-ttu-id="8839d-117">Prima viene chiamato il metodo [Split(Char\[\])](xref:System.String.Split(System.Char[])) per ottenere ogni valore esadecimale come singolo oggetto `string` in una matrice.</span><span class="sxs-lookup"><span data-stu-id="8839d-117">First it calls the [Split(Char\[\])](xref:System.String.Split(System.Char[])) method to obtain each hexadecimal value as an individual `string` in an array.</span></span> <span data-ttu-id="8839d-118">Poi viene chiamato <xref:System.Convert.ToInt32%28System.String%2CSystem.Int32%29> per convertire il valore esadecimale in un valore decimale rappresentato come [int](../../../csharp/language-reference/keywords/int.md).</span><span class="sxs-lookup"><span data-stu-id="8839d-118">Then it calls <xref:System.Convert.ToInt32%28System.String%2CSystem.Int32%29> to convert the hexadecimal value to a decimal value represented as an [int](../../../csharp/language-reference/keywords/int.md).</span></span> <span data-ttu-id="8839d-119">Per ottenere il carattere corrispondente al codice di tale carattere vengono illustrate due modalità diverse.</span><span class="sxs-lookup"><span data-stu-id="8839d-119">It shows two different ways to obtain the character corresponding to that character code.</span></span> <span data-ttu-id="8839d-120">La prima tecnica usa `string` che restituisce il carattere corrispondente all'argomento Integer come <xref:System.Char.ConvertFromUtf32%28System.Int32%29>.</span><span class="sxs-lookup"><span data-stu-id="8839d-120">The first technique uses <xref:System.Char.ConvertFromUtf32%28System.Int32%29>, which returns the character corresponding to the integer argument as a `string`.</span></span> <span data-ttu-id="8839d-121">La seconda tecnica esegue il cast in modo esplicito del valore `int` a un valore [char](../../../csharp/language-reference/keywords/char.md).</span><span class="sxs-lookup"><span data-stu-id="8839d-121">The second technique explicitly casts the `int` to a [char](../../../csharp/language-reference/keywords/char.md).</span></span>  
  
 <span data-ttu-id="8839d-122">[!code-cs[csProgGuideTypes#31](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="8839d-122">[!code-cs[csProgGuideTypes#31](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="8839d-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="8839d-123">Example</span></span>  
 <span data-ttu-id="8839d-124">Questo esempio illustra un altro modo per convertire un valore esadecimale `string` in un Integer, chiamando il metodo <xref:System.Int32.Parse%28System.String%2CSystem.Globalization.NumberStyles%29>.</span><span class="sxs-lookup"><span data-stu-id="8839d-124">This example shows another way to convert a hexadecimal `string` to an integer, by calling the <xref:System.Int32.Parse%28System.String%2CSystem.Globalization.NumberStyles%29> method.</span></span>  
  
 <span data-ttu-id="8839d-125">[!code-cs[csProgGuideTypes#32](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="8839d-125">[!code-cs[csProgGuideTypes#32](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_3.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="8839d-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="8839d-126">Example</span></span>  
 <span data-ttu-id="8839d-127">L'esempio seguente illustra come convertire un tipo `string` esadecimale in [float](../../../csharp/language-reference/keywords/float.md) usando la classe <xref:System.BitConverter?displayProperty=fullName> e il metodo <xref:System.Int32.Parse%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="8839d-127">The following example shows how to convert a hexadecimal `string` to a [float](../../../csharp/language-reference/keywords/float.md) by using the <xref:System.BitConverter?displayProperty=fullName> class and the <xref:System.Int32.Parse%2A?displayProperty=fullName> method.</span></span>  
  
 <span data-ttu-id="8839d-128">[!code-cs[csProgGuideTypes#39](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="8839d-128">[!code-cs[csProgGuideTypes#39](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_4.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="8839d-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="8839d-129">Example</span></span>  
 <span data-ttu-id="8839d-130">L'esempio seguente illustra come convertire una matrice [byte](../../../csharp/language-reference/keywords/byte.md) in una stringa esadecimale tramite la classe <xref:System.BitConverter?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="8839d-130">The following example shows how to convert a [byte](../../../csharp/language-reference/keywords/byte.md) array to a hexadecimal string by using the <xref:System.BitConverter?displayProperty=fullName> class.</span></span>  
  
 <span data-ttu-id="8839d-131">[!code-cs[csProgGuideTypes#38](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="8839d-131">[!code-cs[csProgGuideTypes#38](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_5.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8839d-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8839d-132">See Also</span></span>  
 <span data-ttu-id="8839d-133">[Stringhe di formato numerico standard](../../../standard/base-types/standard-numeric-format-strings.md) </span><span class="sxs-lookup"><span data-stu-id="8839d-133">[Standard Numeric Format Strings](../../../standard/base-types/standard-numeric-format-strings.md) </span></span>  
 <span data-ttu-id="8839d-134">[Tipi](../../../csharp/programming-guide/types/index.md) </span><span class="sxs-lookup"><span data-stu-id="8839d-134">[Types](../../../csharp/programming-guide/types/index.md) </span></span>  
 [<span data-ttu-id="8839d-135">Procedura: Determinare se una stringa rappresenta un valore numerico</span><span class="sxs-lookup"><span data-stu-id="8839d-135">How to: Determine Whether a String Represents a Numeric Value</span></span>](../../../csharp/programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md)

