---
title: "Procedura: ottenere l'indirizzo di una variabile (Guida per programmatori C#)"
ms.date: 07/20/2015
helpviewer_keywords:
- variables [C#], address of
- pointers [C#], & operator
- pointer expressions [C#], address-of operator
ms.assetid: 44fe2cd9-a64f-4ef5-be2a-09ce807c0182
ms.openlocfilehash: bb52aee3341194697b40b30ec14afced61a200be
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33340125"
---
# <a name="how-to-obtain-the-address-of-a-variable-c-programming-guide"></a><span data-ttu-id="63a80-102">Procedura: ottenere l'indirizzo di una variabile (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="63a80-102">How to: Obtain the Address of a Variable (C# Programming Guide)</span></span>
<span data-ttu-id="63a80-103">Per ottenere l'indirizzo di un'espressione unaria, che restituisce una variabile fissa, usare l'operatore address-of `&`:</span><span class="sxs-lookup"><span data-stu-id="63a80-103">To obtain the address of a unary expression, which evaluates to a fixed variable, use the address-of operator `&`:</span></span>  
  
```csharp  
int number;  
int* p = &number; //address-of operator &  
```  
  
 <span data-ttu-id="63a80-104">L'operatore address-of può essere applicato solo a una variabile.</span><span class="sxs-lookup"><span data-stu-id="63a80-104">The address-of operator can only be applied to a variable.</span></span> <span data-ttu-id="63a80-105">Se la variabile è spostabile, è possibile usare l'[istruzione fissa](../../../csharp/language-reference/keywords/fixed-statement.md) per fissare temporaneamente la variabile prima di ottenerne l'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="63a80-105">If the variable is a moveable variable, you can use the [fixed statement](../../../csharp/language-reference/keywords/fixed-statement.md) to temporarily fix the variable before obtaining its address.</span></span>  
  
 <span data-ttu-id="63a80-106">È compito del programmatore garantire che la variabile sia inizializzata.</span><span class="sxs-lookup"><span data-stu-id="63a80-106">It's your responsibility to ensure that the variable is initialized.</span></span> <span data-ttu-id="63a80-107">Il compilatore non genera un messaggio di errore se la variabile non è inizializzata.</span><span class="sxs-lookup"><span data-stu-id="63a80-107">The compiler doesn't issue an error message if the variable is not initialized.</span></span>  
  
 <span data-ttu-id="63a80-108">Non è possibile ottenere l'indirizzo di una costante o di un valore.</span><span class="sxs-lookup"><span data-stu-id="63a80-108">You can't get the address of a constant or a value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63a80-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="63a80-109">Example</span></span>  
 <span data-ttu-id="63a80-110">In questo esempio viene dichiarato un puntatore a `int`, `p`, e gli viene assegnato l'indirizzo di una variabile di tipo integer, `number`.</span><span class="sxs-lookup"><span data-stu-id="63a80-110">In this example, a pointer to `int`, `p`, is declared and assigned the address of an integer variable, `number`.</span></span> <span data-ttu-id="63a80-111">La variabile `number` viene inizializzata in seguito all'assegnazione a `*p`.</span><span class="sxs-lookup"><span data-stu-id="63a80-111">The variable `number` is initialized as a result of the assignment to `*p`.</span></span> <span data-ttu-id="63a80-112">Se si imposta l'istruzione di assegnazione come commento, l'inizializzazione della variabile `number` viene rimossa, ma non viene generato alcun errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="63a80-112">If you comment out this assignment statement, the initialization of the variable `number` is removed, but no compile-time error is issued.</span></span>  

> [!NOTE]
> <span data-ttu-id="63a80-113">Compilare questo esempio con l'opzione del compilatore [ `-unsafe` ](../../language-reference/compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="63a80-113">Compile this example with the [`-unsafe`](../../language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span>
  
 [!code-csharp[address-of-a-variable](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#8)]  
  
## <a name="see-also"></a><span data-ttu-id="63a80-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63a80-114">See Also</span></span>  
 [<span data-ttu-id="63a80-115">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="63a80-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="63a80-116">Espressioni puntatore</span><span class="sxs-lookup"><span data-stu-id="63a80-116">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [<span data-ttu-id="63a80-117">Tipi di puntatori</span><span class="sxs-lookup"><span data-stu-id="63a80-117">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [<span data-ttu-id="63a80-118">Tipi</span><span class="sxs-lookup"><span data-stu-id="63a80-118">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="63a80-119">unsafe</span><span class="sxs-lookup"><span data-stu-id="63a80-119">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="63a80-120">Istruzione fixed</span><span class="sxs-lookup"><span data-stu-id="63a80-120">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="63a80-121">stackalloc</span><span class="sxs-lookup"><span data-stu-id="63a80-121">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
