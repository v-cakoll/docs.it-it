---
title: Confronto tra puntatori (Guida per programmatori C#)
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], comparison
ms.assetid: fcafd514-7405-4deb-8490-cc58efda5495
ms.openlocfilehash: af264cd1572faafe25ee170b35cbeb48ed0fb2aa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33337704"
---
# <a name="pointer-comparison-c-programming-guide"></a><span data-ttu-id="b0191-102">Confronto tra puntatori (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="b0191-102">Pointer Comparison (C# Programming Guide)</span></span>
<span data-ttu-id="b0191-103">Per confrontare puntatori di qualsiasi tipo, è possibile applicare gli operatori seguenti:</span><span class="sxs-lookup"><span data-stu-id="b0191-103">You can apply the following operators to compare pointers of any type:</span></span>  
  
 <span data-ttu-id="b0191-104">**==   !=   \<   >   \<=   >=**</span><span class="sxs-lookup"><span data-stu-id="b0191-104">**==   !=   \<   >   \<=   >=**</span></span>  
  
 <span data-ttu-id="b0191-105">Gli operatori di confronto consentono di confrontare gli indirizzi dei due operandi come se fossero Unsigned Integer.</span><span class="sxs-lookup"><span data-stu-id="b0191-105">The comparison operators compare the addresses of the two operands as if they are unsigned integers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0191-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="b0191-106">Example</span></span>  
 [!code-csharp[csProgGuidePointers#16](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-comparison_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#17](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-comparison_2.cs)]  
  
## <a name="sample-output"></a><span data-ttu-id="b0191-107">Esempio di output</span><span class="sxs-lookup"><span data-stu-id="b0191-107">Sample Output</span></span>  
 `True`  
  
 `False`  
  
## <a name="see-also"></a><span data-ttu-id="b0191-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0191-108">See Also</span></span>  
 [<span data-ttu-id="b0191-109">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="b0191-109">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="b0191-110">Espressioni puntatore</span><span class="sxs-lookup"><span data-stu-id="b0191-110">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [<span data-ttu-id="b0191-111">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="b0191-111">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="b0191-112">Modifica dei puntatori</span><span class="sxs-lookup"><span data-stu-id="b0191-112">Manipulating Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)  
 [<span data-ttu-id="b0191-113">Tipi di puntatori</span><span class="sxs-lookup"><span data-stu-id="b0191-113">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [<span data-ttu-id="b0191-114">Tipi</span><span class="sxs-lookup"><span data-stu-id="b0191-114">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="b0191-115">unsafe</span><span class="sxs-lookup"><span data-stu-id="b0191-115">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="b0191-116">Istruzione fixed</span><span class="sxs-lookup"><span data-stu-id="b0191-116">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="b0191-117">stackalloc</span><span class="sxs-lookup"><span data-stu-id="b0191-117">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
