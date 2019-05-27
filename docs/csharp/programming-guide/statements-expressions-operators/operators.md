---
title: Operatori - Guida per programmatori C#
ms.custom: seodec18
ms.date: 04/30/2019
helpviewer_keywords:
- operators [C#]
- C# language, operators
- operators [C#], about operators
ms.assetid: 214e7b83-1a41-4f7c-9867-64e9c0bab39f
ms.openlocfilehash: fd10999066f599d819ef188e09028c64c6a5e9e6
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2019
ms.locfileid: "65064050"
---
# <a name="operators-c-programming-guide"></a><span data-ttu-id="2cfb1-102">Operatori (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="2cfb1-102">Operators (C# Programming Guide)</span></span>

<span data-ttu-id="2cfb1-103">Nel linguaggio C# un *operatore* è un elemento del programma che si applica a uno o più *operandi* in un'espressione o in un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="2cfb1-103">In C#, an *operator* is a program element that is applied to one or more *operands* in an expression or statement.</span></span> <span data-ttu-id="2cfb1-104">Gli operatori che accettano un unico operando, ad esempio l'operatore di incremento (`++`) o `new`, sono denominati operatori *unari* .</span><span class="sxs-lookup"><span data-stu-id="2cfb1-104">Operators that take one operand, such as the increment operator (`++`) or `new`, are referred to as *unary* operators.</span></span> <span data-ttu-id="2cfb1-105">Quelli che accettano due operandi, ad esempio gli operatori aritmetici (`+`,`-`,`*`,`/`), sono denominati operatori *binari* .</span><span class="sxs-lookup"><span data-stu-id="2cfb1-105">Operators that take two operands, such as arithmetic operators (`+`,`-`,`*`,`/`), are referred to as *binary* operators.</span></span> <span data-ttu-id="2cfb1-106">L'operatore condizionale (`?:`) accetta tre operandi ed è l'unico operatore ternario disponibile in C#.</span><span class="sxs-lookup"><span data-stu-id="2cfb1-106">One operator, the conditional operator (`?:`), takes three operands and is the sole ternary operator in C#.</span></span>  
  
 <span data-ttu-id="2cfb1-107">L'istruzione C# riportata di seguito contiene un unico operatore unario e un unico operando.</span><span class="sxs-lookup"><span data-stu-id="2cfb1-107">The following C# statement contains a single unary operator and a single operand.</span></span> <span data-ttu-id="2cfb1-108">L'operatore di incremento `++`modifica il valore dell'operando `y`.</span><span class="sxs-lookup"><span data-stu-id="2cfb1-108">The increment operator, `++`, modifies the value of the operand `y`.</span></span>  
  
 [!code-csharp[csProgGuideStatements#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#5)]  
  
 <span data-ttu-id="2cfb1-109">L'istruzione C# riportata di seguito contiene due operatori binari, ciascuno con due operandi.</span><span class="sxs-lookup"><span data-stu-id="2cfb1-109">The following C# statement contains two binary operators, each with two operands.</span></span> <span data-ttu-id="2cfb1-110">L'operatore di assegnazione `=`ha come operandi la variabile integer `y` e l'espressione `2 + 3` .</span><span class="sxs-lookup"><span data-stu-id="2cfb1-110">The assignment operator, `=`, has the integer variable `y` and the expression `2 + 3` as operands.</span></span> <span data-ttu-id="2cfb1-111">L'espressione `2 + 3` è costituita dall'operatore di addizione e due operandi, `2` e `3`.</span><span class="sxs-lookup"><span data-stu-id="2cfb1-111">The expression `2 + 3` itself consists of the addition operator and two operands, `2` and `3`.</span></span>  
  
 [!code-csharp[csProgGuideStatements#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#6)]  
  
<span data-ttu-id="2cfb1-112">Un operando può essere un'espressione valida composta da codice di qualsiasi lunghezza e può includere un numero qualsiasi di sottoespressioni.</span><span class="sxs-lookup"><span data-stu-id="2cfb1-112">An operand can be a valid expression that is composed of any length of code, and it can comprise any number of sub expressions.</span></span> <span data-ttu-id="2cfb1-113">In un'espressione che contiene più operatori, l'ordine in cui vengono applicati gli operatori è determinata dalla *precedenza tra operatori*, l' *associatività*e le parentesi.</span><span class="sxs-lookup"><span data-stu-id="2cfb1-113">In an expression that contains multiple operators, the order in which the operators are applied is determined by *operator precedence*, *associativity*, and parentheses.</span></span>  

## <a name="operator-precedence"></a><span data-ttu-id="2cfb1-114">Precedenza tra gli operatori</span><span class="sxs-lookup"><span data-stu-id="2cfb1-114">Operator precedence</span></span>
  
<span data-ttu-id="2cfb1-115">Ogni operatore ha una precedenza definita.</span><span class="sxs-lookup"><span data-stu-id="2cfb1-115">Each operator has a defined precedence.</span></span> <span data-ttu-id="2cfb1-116">In un'espressione che contiene più operatori che dispongono di diversi livelli di precedenza, la precedenza degli operatori determina l'ordine in cui gli operatori verranno valutati.</span><span class="sxs-lookup"><span data-stu-id="2cfb1-116">In an expression that contains multiple operators that have different precedence levels, the precedence of the operators determines the order in which the operators are evaluated.</span></span> <span data-ttu-id="2cfb1-117">L'istruzione che segue, ad esempio, assegna il valore 3 a `n1`:</span><span class="sxs-lookup"><span data-stu-id="2cfb1-117">For example, the following statement assigns 3 to `n1`:</span></span>

```csharp
n1 = 11 - 2 * 4;
```

<span data-ttu-id="2cfb1-118">La moltiplicazione viene eseguita per prima perché ha la precedenza sulla sottrazione.</span><span class="sxs-lookup"><span data-stu-id="2cfb1-118">The multiplication is executed first because multiplication takes precedence over subtraction.</span></span>

<span data-ttu-id="2cfb1-119">Per l'elenco completo degli operatori C# ordinati in base al livello di precedenza, vedere [Operatori C#](../../language-reference/operators/index.md).</span><span class="sxs-lookup"><span data-stu-id="2cfb1-119">For the complete list of C# operators ordered by precedence level, see [C# operators](../../language-reference/operators/index.md).</span></span>
  
## <a name="associativity"></a><span data-ttu-id="2cfb1-120">Associazione</span><span class="sxs-lookup"><span data-stu-id="2cfb1-120">Associativity</span></span>

 <span data-ttu-id="2cfb1-121">Quando in un'espressione sono presenti due o più operatori con la stessa precedenza, verranno valutati in base all'associazione.</span><span class="sxs-lookup"><span data-stu-id="2cfb1-121">When two or more operators that have the same precedence are present in an expression, they are evaluated based on associativity.</span></span> <span data-ttu-id="2cfb1-122">Gli operatori che prevedono l'associazione all'operando sinistro vengono valutati nell'ordine da sinistra a destra.</span><span class="sxs-lookup"><span data-stu-id="2cfb1-122">Left-associative operators are evaluated in order from left to right.</span></span> <span data-ttu-id="2cfb1-123">L'espressione `x * y / z` viene ad esempio valutata come `(x * y) / z`.</span><span class="sxs-lookup"><span data-stu-id="2cfb1-123">For example, `x * y / z` is evaluated as `(x * y) / z`.</span></span> <span data-ttu-id="2cfb1-124">Gli operatori che prevedono l'associazione all'operando destro vengono valutati nell'ordine da destra a sinistra.</span><span class="sxs-lookup"><span data-stu-id="2cfb1-124">Right-associative operators are evaluated in order from right to left.</span></span> <span data-ttu-id="2cfb1-125">Ad esempio, l'operatore di assegnazione prevede l'associazione all'operando destro.</span><span class="sxs-lookup"><span data-stu-id="2cfb1-125">For example, the assignment operator is right associative.</span></span> <span data-ttu-id="2cfb1-126">Se non fosse così, il codice seguente restituirà un errore.</span><span class="sxs-lookup"><span data-stu-id="2cfb1-126">If it were not, the following code would result in an error.</span></span>  
  
```csharp  
int a, b, c;  
c = 1;  
// The following two lines are equivalent.  
a = b = c;  
a = (b = c);  
  
// The following line, which forces left associativity, causes an error.  
//(a = b) = c;  
```  
  
 <span data-ttu-id="2cfb1-127">Facendo un altro esempio, l'operatore ternario ([?:](../../../csharp/language-reference/operators/conditional-operator.md)) prevede l'associazione all'operando destro.</span><span class="sxs-lookup"><span data-stu-id="2cfb1-127">As another example the ternary operator ([?:](../../../csharp/language-reference/operators/conditional-operator.md)) is right associative.</span></span> <span data-ttu-id="2cfb1-128">La maggior parte degli operatori binari prevede l'associazione all'operando sinistro.</span><span class="sxs-lookup"><span data-stu-id="2cfb1-128">Most binary operators are left associative.</span></span>  
  
 <span data-ttu-id="2cfb1-129">Se gli operatori in un'espressione sono impostati su associativo o associativo da destra, gli operandi di ogni espressione vengono valutati per primi, da sinistra a destra.</span><span class="sxs-lookup"><span data-stu-id="2cfb1-129">Whether the operators in an expression are left associative or right associative, the operands of each expression are evaluated first, from left to right.</span></span> <span data-ttu-id="2cfb1-130">Negli esempi seguenti viene illustrato l'ordine di valutazione degli operatori e degli operandi.</span><span class="sxs-lookup"><span data-stu-id="2cfb1-130">The following examples illustrate the order of evaluation of operators and operands.</span></span>  
  
|<span data-ttu-id="2cfb1-131">Istruzione</span><span class="sxs-lookup"><span data-stu-id="2cfb1-131">Statement</span></span>|<span data-ttu-id="2cfb1-132">Ordine di valutazione</span><span class="sxs-lookup"><span data-stu-id="2cfb1-132">Order of evaluation</span></span>|  
|---------------|-------------------------|  
|`a = b`|<span data-ttu-id="2cfb1-133">a, b, =</span><span class="sxs-lookup"><span data-stu-id="2cfb1-133">a, b, =</span></span>|  
|`a = b + c`|<span data-ttu-id="2cfb1-134">a, b, c, +, =</span><span class="sxs-lookup"><span data-stu-id="2cfb1-134">a, b, c, +, =</span></span>|  
|`a = b + c * d`|<span data-ttu-id="2cfb1-135">a, b, c, d, \*, +, =</span><span class="sxs-lookup"><span data-stu-id="2cfb1-135">a, b, c, d, \*, +, =</span></span>|  
|`a = b * c + d`|<span data-ttu-id="2cfb1-136">a, b, c, \*, d, +, =</span><span class="sxs-lookup"><span data-stu-id="2cfb1-136">a, b, c, \*, d, +, =</span></span>|  
|`a = b - c + d`|<span data-ttu-id="2cfb1-137">a, b, c, -, d, +, =</span><span class="sxs-lookup"><span data-stu-id="2cfb1-137">a, b, c, -, d, +, =</span></span>|  
|`a += b -= c`|<span data-ttu-id="2cfb1-138">a, b, c, -=, +=</span><span class="sxs-lookup"><span data-stu-id="2cfb1-138">a, b, c, -=, +=</span></span>|  
  
## <a name="adding-parentheses"></a><span data-ttu-id="2cfb1-139">Aggiunta di parentesi</span><span class="sxs-lookup"><span data-stu-id="2cfb1-139">Adding parentheses</span></span>

 <span data-ttu-id="2cfb1-140">È possibile modificare l'ordine imposto dalla precedenza degli operatori e dall'associatività usando le parentesi.</span><span class="sxs-lookup"><span data-stu-id="2cfb1-140">You can change the order imposed by operator precedence and associativity by using parentheses.</span></span> <span data-ttu-id="2cfb1-141">Ad esempio, il risultato dell'espressione `2 + 3 * 2` restituisce normalmente 8, in quanto gli operatori di moltiplicazione hanno la precedenza su quelli di addizione.</span><span class="sxs-lookup"><span data-stu-id="2cfb1-141">For example, `2 + 3 * 2` ordinarily evaluates to 8, because multiplicative operators take precedence over additive operators.</span></span> <span data-ttu-id="2cfb1-142">Tuttavia, se si scrive l'espressione in questo modo `(2 + 3) * 2`, l'addizione è presa in considerazione prima della moltiplicazione e il risultato sarà 10.</span><span class="sxs-lookup"><span data-stu-id="2cfb1-142">However, if you write the expression as `(2 + 3) * 2`, the addition is evaluated before the multiplication, and the result is 10.</span></span> <span data-ttu-id="2cfb1-143">Negli esempi seguenti viene illustrato l'ordine di valutazione delle espressioni tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="2cfb1-143">The following examples illustrate the order of evaluation in parenthesized expressions.</span></span> <span data-ttu-id="2cfb1-144">Come negli esempi precedenti, gli operandi vengono valutati prima di applicare l'operatore.</span><span class="sxs-lookup"><span data-stu-id="2cfb1-144">As in previous examples, the operands are evaluated before the operator is applied.</span></span>  
  
|<span data-ttu-id="2cfb1-145">Istruzione</span><span class="sxs-lookup"><span data-stu-id="2cfb1-145">Statement</span></span>|<span data-ttu-id="2cfb1-146">Ordine di valutazione</span><span class="sxs-lookup"><span data-stu-id="2cfb1-146">Order of evaluation</span></span>|  
|---------------|-------------------------|  
|`a = (b + c) * d`|<span data-ttu-id="2cfb1-147">a, b, c, +, d, \*, =</span><span class="sxs-lookup"><span data-stu-id="2cfb1-147">a, b, c, +, d, \*, =</span></span>|  
|`a = b - (c + d)`|<span data-ttu-id="2cfb1-148">a, b, c, d, +, -, =</span><span class="sxs-lookup"><span data-stu-id="2cfb1-148">a, b, c, d, +, -, =</span></span>|  
|`a = (b + c) * (d - e)`|<span data-ttu-id="2cfb1-149">a, b, c, +, d, e, -, \*, =</span><span class="sxs-lookup"><span data-stu-id="2cfb1-149">a, b, c, +, d, e, -, \*, =</span></span>|  
  
## <a name="operator-overloading"></a><span data-ttu-id="2cfb1-150">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="2cfb1-150">Operator overloading</span></span>

<span data-ttu-id="2cfb1-151">È possibile definire il comportamento di determinati operatori per classi e struct personalizzati.</span><span class="sxs-lookup"><span data-stu-id="2cfb1-151">You can define the behavior of certain operators for custom classes and structs.</span></span> <span data-ttu-id="2cfb1-152">Questo processo è denominato *overload degli operatori*.</span><span class="sxs-lookup"><span data-stu-id="2cfb1-152">This process is referred to as *operator overloading*.</span></span> <span data-ttu-id="2cfb1-153">Per altre informazioni, vedere [Operatori che supportano l'overload](overloadable-operators.md) e l'articolo relativo alla parola chiave [operator](../../language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="2cfb1-153">For more information, see [Overloadable operators](overloadable-operators.md) and the [operator](../../language-reference/keywords/operator.md) keyword article.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2cfb1-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2cfb1-154">See also</span></span>

- [<span data-ttu-id="2cfb1-155">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="2cfb1-155">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="2cfb1-156">Istruzioni, espressioni e operatori</span><span class="sxs-lookup"><span data-stu-id="2cfb1-156">Statements, Expressions, and Operators</span></span>](index.md)
- [<span data-ttu-id="2cfb1-157">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="2cfb1-157">C# Operators</span></span>](../../language-reference/operators/index.md)
- [<span data-ttu-id="2cfb1-158">Parole chiave per gli operatori</span><span class="sxs-lookup"><span data-stu-id="2cfb1-158">Operator Keywords</span></span>](../../language-reference/keywords/operator-keywords.md)
