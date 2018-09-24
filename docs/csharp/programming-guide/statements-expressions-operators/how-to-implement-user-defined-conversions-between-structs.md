---
title: "Procedura: implementare conversioni tra struct definite dall'utente (Guida per programmatori C#)"
ms.date: 07/20/2015
helpviewer_keywords:
- user-defined conversions [C#]
ms.assetid: 97839aef-8fbc-40d5-9769-6b569bc2710b
ms.openlocfilehash: cff85d60c1b59f4d1ca028f8fc02fee5728fa3d6
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2018
ms.locfileid: "46696652"
---
# <a name="how-to-implement-user-defined-conversions-between-structs-c-programming-guide"></a><span data-ttu-id="d054e-102">Procedura: implementare conversioni tra struct definite dall'utente (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="d054e-102">How to: Implement User-Defined Conversions Between Structs (C# Programming Guide)</span></span>
<span data-ttu-id="d054e-103">Questo esempio definisce due struct, `RomanNumeral` e `BinaryNumeral`, e illustra le conversioni tra di loro.</span><span class="sxs-lookup"><span data-stu-id="d054e-103">This example defines two structs, `RomanNumeral` and `BinaryNumeral`, and demonstrates conversions between them.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d054e-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="d054e-104">Example</span></span>  
 [!code-csharp[csProgGuideStatements#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_1.cs)]  
  
## <a name="robust-programming"></a><span data-ttu-id="d054e-105">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="d054e-105">Robust Programming</span></span>  
  
-   <span data-ttu-id="d054e-106">Nell'esempio precedente l'istruzione:</span><span class="sxs-lookup"><span data-stu-id="d054e-106">In the previous example, the statement:</span></span>  
  
     [!code-csharp[csProgGuideStatements#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_2.cs)]  
  
     <span data-ttu-id="d054e-107">esegue una conversione da `RomanNumeral` a `BinaryNumeral`.</span><span class="sxs-lookup"><span data-stu-id="d054e-107">performs a conversion from a `RomanNumeral` to a `BinaryNumeral`.</span></span> <span data-ttu-id="d054e-108">Poiché non c'è una conversione diretta da `RomanNumeral` a `BinaryNumeral`, vengono usati un cast per la conversione da `RomanNumeral` a `int` e un altro cast per la conversione da `int` a `BinaryNumeral`.</span><span class="sxs-lookup"><span data-stu-id="d054e-108">Because there is no direct conversion from `RomanNumeral` to `BinaryNumeral`, a cast is used to convert from a `RomanNumeral` to an `int`, and another cast to convert from an `int` to a `BinaryNumeral`.</span></span>  
  
-   <span data-ttu-id="d054e-109">Anche l'istruzione</span><span class="sxs-lookup"><span data-stu-id="d054e-109">Also the statement</span></span>  
  
     [!code-csharp[csProgGuideStatements#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_3.cs)]  
  
     <span data-ttu-id="d054e-110">esegue una conversione da `BinaryNumeral` a `RomanNumeral`.</span><span class="sxs-lookup"><span data-stu-id="d054e-110">performs a conversion from a `BinaryNumeral` to a `RomanNumeral`.</span></span> <span data-ttu-id="d054e-111">Poiché `RomanNumeral` definisce una conversione implicita da `BinaryNumeral`, non è necessario il cast.</span><span class="sxs-lookup"><span data-stu-id="d054e-111">Because `RomanNumeral` defines an implicit conversion from `BinaryNumeral`, no cast is required.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d054e-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d054e-112">See Also</span></span>

- [<span data-ttu-id="d054e-113">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="d054e-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="d054e-114">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="d054e-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="d054e-115">Operatori di conversione</span><span class="sxs-lookup"><span data-stu-id="d054e-115">Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)
