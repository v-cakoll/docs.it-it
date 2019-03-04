---
title: Confronto tra puntatori - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], comparison
ms.assetid: fcafd514-7405-4deb-8490-cc58efda5495
ms.openlocfilehash: 5185bd5e1686858452efcc7c89e2c1977e094386
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56969206"
---
# <a name="pointer-comparison-c-programming-guide"></a><span data-ttu-id="4b74b-102">Confronto tra puntatori (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="4b74b-102">Pointer Comparison (C# Programming Guide)</span></span>
<span data-ttu-id="4b74b-103">Per confrontare puntatori di qualsiasi tipo, è possibile applicare gli operatori seguenti:</span><span class="sxs-lookup"><span data-stu-id="4b74b-103">You can apply the following operators to compare pointers of any type:</span></span>  
  
 <span data-ttu-id="4b74b-104">**==   !=   \<   >   \<=   >=**</span><span class="sxs-lookup"><span data-stu-id="4b74b-104">**==   !=   \<   >   \<=   >=**</span></span>  
  
 <span data-ttu-id="4b74b-105">Gli operatori di confronto consentono di confrontare gli indirizzi dei due operandi come se fossero Unsigned Integer.</span><span class="sxs-lookup"><span data-stu-id="4b74b-105">The comparison operators compare the addresses of the two operands as if they are unsigned integers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b74b-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="4b74b-106">Example</span></span>  
 [!code-csharp[csProgGuidePointers#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#16)]  
  
 [!code-csharp[csProgGuidePointers#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#17)]  
  
## <a name="sample-output"></a><span data-ttu-id="4b74b-107">Esempio di output</span><span class="sxs-lookup"><span data-stu-id="4b74b-107">Sample Output</span></span>  
 `True`  
  
 `False`  
  
## <a name="see-also"></a><span data-ttu-id="4b74b-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b74b-108">See also</span></span>

- [<span data-ttu-id="4b74b-109">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="4b74b-109">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="4b74b-110">Espressioni puntatore</span><span class="sxs-lookup"><span data-stu-id="4b74b-110">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)
- [<span data-ttu-id="4b74b-111">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="4b74b-111">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
- [<span data-ttu-id="4b74b-112">Modifica dei puntatori</span><span class="sxs-lookup"><span data-stu-id="4b74b-112">Manipulating Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)
- [<span data-ttu-id="4b74b-113">Tipi di puntatori</span><span class="sxs-lookup"><span data-stu-id="4b74b-113">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="4b74b-114">Tipi</span><span class="sxs-lookup"><span data-stu-id="4b74b-114">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="4b74b-115">unsafe</span><span class="sxs-lookup"><span data-stu-id="4b74b-115">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="4b74b-116">Istruzione fixed</span><span class="sxs-lookup"><span data-stu-id="4b74b-116">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="4b74b-117">stackalloc</span><span class="sxs-lookup"><span data-stu-id="4b74b-117">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
