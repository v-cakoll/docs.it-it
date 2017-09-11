---
title: 'Procedura: implementare conversioni tra struct definite dall''utente (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- user-defined conversions [C#]
ms.assetid: 97839aef-8fbc-40d5-9769-6b569bc2710b
caps.latest.revision: 11
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
ms.openlocfilehash: cc8856bb3bf8943c1b6648f7d81447a3e59b9489
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-implement-user-defined-conversions-between-structs-c-programming-guide"></a><span data-ttu-id="785b0-102">Procedura: implementare conversioni tra struct definite dall'utente (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="785b0-102">How to: Implement User-Defined Conversions Between Structs (C# Programming Guide)</span></span>
<span data-ttu-id="785b0-103">Questo esempio definisce due struct, `RomanNumeral` e `BinaryNumeral`, e illustra le conversioni tra di loro.</span><span class="sxs-lookup"><span data-stu-id="785b0-103">This example defines two structs, `RomanNumeral` and `BinaryNumeral`, and demonstrates conversions between them.</span></span>  
  
## <a name="example"></a><span data-ttu-id="785b0-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="785b0-104">Example</span></span>  
 <span data-ttu-id="785b0-105">[!code-cs[csProgGuideStatements#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="785b0-105">[!code-cs[csProgGuideStatements#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_1.cs)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="785b0-106">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="785b0-106">Robust Programming</span></span>  
  
-   <span data-ttu-id="785b0-107">Nell'esempio precedente l'istruzione:</span><span class="sxs-lookup"><span data-stu-id="785b0-107">In the previous example, the statement:</span></span>  
  
     <span data-ttu-id="785b0-108">[!code-cs[csProgGuideStatements#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="785b0-108">[!code-cs[csProgGuideStatements#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_2.cs)]</span></span>  
  
     <span data-ttu-id="785b0-109">esegue una conversione da `RomanNumeral` a `BinaryNumeral`.</span><span class="sxs-lookup"><span data-stu-id="785b0-109">performs a conversion from a `RomanNumeral` to a `BinaryNumeral`.</span></span> <span data-ttu-id="785b0-110">Poiché non c'è una conversione diretta da `RomanNumeral` a `BinaryNumeral`, vengono usati un cast per la conversione da `RomanNumeral` a `int` e un altro cast per la conversione da `int` a `BinaryNumeral`.</span><span class="sxs-lookup"><span data-stu-id="785b0-110">Because there is no direct conversion from `RomanNumeral` to `BinaryNumeral`, a cast is used to convert from a `RomanNumeral` to an `int`, and another cast to convert from an `int` to a `BinaryNumeral`.</span></span>  
  
-   <span data-ttu-id="785b0-111">Anche l'istruzione</span><span class="sxs-lookup"><span data-stu-id="785b0-111">Also the statement</span></span>  
  
     <span data-ttu-id="785b0-112">[!code-cs[csProgGuideStatements#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="785b0-112">[!code-cs[csProgGuideStatements#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_3.cs)]</span></span>  
  
     <span data-ttu-id="785b0-113">esegue una conversione da `BinaryNumeral` a `RomanNumeral`.</span><span class="sxs-lookup"><span data-stu-id="785b0-113">performs a conversion from a `BinaryNumeral` to a `RomanNumeral`.</span></span> <span data-ttu-id="785b0-114">Poiché `RomanNumeral` definisce una conversione implicita da `BinaryNumeral`, non è necessario il cast.</span><span class="sxs-lookup"><span data-stu-id="785b0-114">Because `RomanNumeral` defines an implicit conversion from `BinaryNumeral`, no cast is required.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="785b0-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="785b0-115">See Also</span></span>  
 <span data-ttu-id="785b0-116">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="785b0-116">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="785b0-117">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="785b0-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="785b0-118">Operatori di conversione</span><span class="sxs-lookup"><span data-stu-id="785b0-118">Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)

