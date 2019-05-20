---
title: "Procedura: Ottenere l'indirizzo di una variabile - Guida per programmatori C#"
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- variables [C#], address of
- pointers [C#], & operator
- pointer expressions [C#], address-of operator
ms.assetid: 44fe2cd9-a64f-4ef5-be2a-09ce807c0182
ms.openlocfilehash: bc5776bc57096b88a71ff786915553ae9aa04b7b
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65635066"
---
# <a name="how-to-obtain-the-address-of-a-variable-c-programming-guide"></a><span data-ttu-id="00fae-102">Procedura: Ottenere l'indirizzo di una variabile (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="00fae-102">How to: obtain the address of a variable (C# Programming Guide)</span></span>

<span data-ttu-id="00fae-103">Per ottenere l'indirizzo di un'espressione unaria, che restituisce una variabile fissa, usare l'operatore address-of `&`:</span><span class="sxs-lookup"><span data-stu-id="00fae-103">To obtain the address of a unary expression, which evaluates to a fixed variable, use the address-of operator `&`:</span></span>  
  
```csharp  
int number;  
int* p = &number; //address-of operator &  
```  
  
 <span data-ttu-id="00fae-104">L'operatore address-of può essere applicato solo a una variabile.</span><span class="sxs-lookup"><span data-stu-id="00fae-104">The address-of operator can only be applied to a variable.</span></span> <span data-ttu-id="00fae-105">Se la variabile è spostabile, è possibile usare l'[istruzione fissa](../../../csharp/language-reference/keywords/fixed-statement.md) per fissare temporaneamente la variabile prima di ottenerne l'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="00fae-105">If the variable is a moveable variable, you can use the [fixed statement](../../../csharp/language-reference/keywords/fixed-statement.md) to temporarily fix the variable before obtaining its address.</span></span> <span data-ttu-id="00fae-106">Per altre informazioni sulle variabili mobili, vedere [Variabili fisse e mobili](/dotnet/csharp/language-reference/language-specification/unsafe-code#fixed-and-moveable-variables).</span><span class="sxs-lookup"><span data-stu-id="00fae-106">For more information about moveable variables, see [Fixed and moveable variables](/dotnet/csharp/language-reference/language-specification/unsafe-code#fixed-and-moveable-variables).</span></span> 
  
 <span data-ttu-id="00fae-107">È compito del programmatore garantire che la variabile sia inizializzata.</span><span class="sxs-lookup"><span data-stu-id="00fae-107">It's your responsibility to ensure that the variable is initialized.</span></span> <span data-ttu-id="00fae-108">Il compilatore non genera un messaggio di errore se la variabile non è inizializzata.</span><span class="sxs-lookup"><span data-stu-id="00fae-108">The compiler doesn't issue an error message if the variable is not initialized.</span></span>  
  
 <span data-ttu-id="00fae-109">Non è possibile ottenere l'indirizzo di una costante o di un valore.</span><span class="sxs-lookup"><span data-stu-id="00fae-109">You can't get the address of a constant or a value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00fae-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="00fae-110">Example</span></span>  
 <span data-ttu-id="00fae-111">In questo esempio viene dichiarato un puntatore a `int`, `p`, e gli viene assegnato l'indirizzo di una variabile di tipo integer, `number`.</span><span class="sxs-lookup"><span data-stu-id="00fae-111">In this example, a pointer to `int`, `p`, is declared and assigned the address of an integer variable, `number`.</span></span> <span data-ttu-id="00fae-112">La variabile `number` viene inizializzata in seguito all'assegnazione a `*p`.</span><span class="sxs-lookup"><span data-stu-id="00fae-112">The variable `number` is initialized as a result of the assignment to `*p`.</span></span> <span data-ttu-id="00fae-113">Se si imposta l'istruzione di assegnazione come commento, l'inizializzazione della variabile `number` viene rimossa, ma non viene generato alcun errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="00fae-113">If you comment out this assignment statement, the initialization of the variable `number` is removed, but no compile-time error is issued.</span></span>  

> [!NOTE]
> <span data-ttu-id="00fae-114">Compilare questo esempio con l'opzione del compilatore [ `-unsafe` ](../../language-reference/compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="00fae-114">Compile this example with the [`-unsafe`](../../language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span>
  
 [!code-csharp[address-of-a-variable](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#8)]  
  
## <a name="see-also"></a><span data-ttu-id="00fae-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00fae-115">See also</span></span>

- [<span data-ttu-id="00fae-116">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="00fae-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="00fae-117">Tipi di puntatori</span><span class="sxs-lookup"><span data-stu-id="00fae-117">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="00fae-118">Tipi</span><span class="sxs-lookup"><span data-stu-id="00fae-118">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="00fae-119">unsafe</span><span class="sxs-lookup"><span data-stu-id="00fae-119">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="00fae-120">Istruzione fixed</span><span class="sxs-lookup"><span data-stu-id="00fae-120">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="00fae-121">stackalloc</span><span class="sxs-lookup"><span data-stu-id="00fae-121">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
