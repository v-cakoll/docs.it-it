---
title: + Operatore
ms.date: 07/20/2015
f1_keywords:
- vb.+
helpviewer_keywords:
- arithmetic operators [Visual Basic], addition
- + operator
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
- sum operator [Visual Basic]
ms.assetid: 5694778f-0a2c-4539-8009-f66f318fb46d
ms.openlocfilehash: 6ae3feae6ecb63b82426f2aa69359625bbffcec8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84372116"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="871f3-102">Operatore + (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="871f3-102">+ Operator (Visual Basic)</span></span>
<span data-ttu-id="871f3-103">Somma due numeri o restituisce il valore positivo di un'espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="871f3-103">Adds two numbers or returns the positive value of a numeric expression.</span></span> <span data-ttu-id="871f3-104">Può essere usato anche per concatenare due espressioni stringa.</span><span class="sxs-lookup"><span data-stu-id="871f3-104">Can also be used to concatenate two string expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="871f3-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="871f3-105">Syntax</span></span>  
  
```vb
expression1 + expression2
```
  
<span data-ttu-id="871f3-106">Oppure</span><span class="sxs-lookup"><span data-stu-id="871f3-106">or</span></span>

```vb  
+expression1  
```  
  
## <a name="parts"></a><span data-ttu-id="871f3-107">Parti</span><span class="sxs-lookup"><span data-stu-id="871f3-107">Parts</span></span>  
  
|<span data-ttu-id="871f3-108">Termine</span><span class="sxs-lookup"><span data-stu-id="871f3-108">Term</span></span>|<span data-ttu-id="871f3-109">Definizione</span><span class="sxs-lookup"><span data-stu-id="871f3-109">Definition</span></span>|  
|---|---|  
|`expression1`|<span data-ttu-id="871f3-110">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="871f3-110">Required.</span></span> <span data-ttu-id="871f3-111">Qualsiasi espressione numerica o stringa.</span><span class="sxs-lookup"><span data-stu-id="871f3-111">Any numeric or string expression.</span></span>|  
|`expression2`|<span data-ttu-id="871f3-112">Obbligatorio a meno che l' `+` operatore non calcoli un valore negativo.</span><span class="sxs-lookup"><span data-stu-id="871f3-112">Required unless the `+` operator is calculating a negative value.</span></span> <span data-ttu-id="871f3-113">Qualsiasi espressione numerica o stringa.</span><span class="sxs-lookup"><span data-stu-id="871f3-113">Any numeric or string expression.</span></span>|  
  
## <a name="result"></a><span data-ttu-id="871f3-114">Risultato</span><span class="sxs-lookup"><span data-stu-id="871f3-114">Result</span></span>  
 <span data-ttu-id="871f3-115">Se `expression1` e `expression2` sono entrambi numerici, il risultato è la somma aritmetica.</span><span class="sxs-lookup"><span data-stu-id="871f3-115">If `expression1` and `expression2` are both numeric, the result is their arithmetic sum.</span></span>  
  
 <span data-ttu-id="871f3-116">Se `expression2` è assente, l' `+` operatore è l'operatore di identità *unario* per il valore non modificato di un'espressione.</span><span class="sxs-lookup"><span data-stu-id="871f3-116">If `expression2` is absent, the `+` operator is the *unary* identity operator for the unchanged value of an expression.</span></span> <span data-ttu-id="871f3-117">In questo senso, l'operazione consiste nel mantenere il segno di `expression1` , pertanto il risultato è negativo se `expression1` è negativo.</span><span class="sxs-lookup"><span data-stu-id="871f3-117">In this sense, the operation consists of retaining the sign of `expression1`, so the result is negative if `expression1` is negative.</span></span>  
  
 <span data-ttu-id="871f3-118">Se `expression1` e `expression2` sono entrambe stringhe, il risultato è la concatenazione dei relativi valori.</span><span class="sxs-lookup"><span data-stu-id="871f3-118">If `expression1` and `expression2` are both strings, the result is the concatenation of their values.</span></span>  
  
 <span data-ttu-id="871f3-119">Se `expression1` e `expression2` sono di tipi misti, l'azione eseguita dipende dai relativi tipi, dal relativo contenuto e dall'impostazione dell' [istruzione Option Strict](../statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="871f3-119">If `expression1` and `expression2` are of mixed types, the action taken depends on their types, their contents, and the setting of the [Option Strict Statement](../statements/option-strict-statement.md).</span></span> <span data-ttu-id="871f3-120">Per ulteriori informazioni, vedere le tabelle in "osservazioni".</span><span class="sxs-lookup"><span data-stu-id="871f3-120">For more information, see the tables in "Remarks."</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="871f3-121">Tipi supportati</span><span class="sxs-lookup"><span data-stu-id="871f3-121">Supported Types</span></span>  
 <span data-ttu-id="871f3-122">Tutti i tipi numerici, inclusi i tipi senza segno e a virgola mobile e `Decimal` , e `String` .</span><span class="sxs-lookup"><span data-stu-id="871f3-122">All numeric types, including the unsigned and floating-point types and `Decimal`, and `String`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="871f3-123">Commenti</span><span class="sxs-lookup"><span data-stu-id="871f3-123">Remarks</span></span>  
 <span data-ttu-id="871f3-124">In generale, `+` se possibile, esegue l'aggiunta aritmetica e concatena solo quando entrambe le espressioni sono stringhe.</span><span class="sxs-lookup"><span data-stu-id="871f3-124">In general, `+` performs arithmetic addition when possible, and concatenates only when both expressions are strings.</span></span>  
  
 <span data-ttu-id="871f3-125">Se nessuna delle due espressioni è un `Object` , Visual Basic esegue le azioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="871f3-125">If neither expression is an `Object`, Visual Basic takes the following actions.</span></span>  
  
|<span data-ttu-id="871f3-126">Tipi di dati delle espressioni</span><span class="sxs-lookup"><span data-stu-id="871f3-126">Data types of expressions</span></span>|<span data-ttu-id="871f3-127">Azione per compilatore</span><span class="sxs-lookup"><span data-stu-id="871f3-127">Action by compiler</span></span>|  
|---|---|  
|<span data-ttu-id="871f3-128">Entrambe le espressioni sono tipi di dati numerici ( `SByte` ,, `Byte` `Short` , `UShort` , `Integer` , `UInteger` , `Long` , `ULong` , `Decimal` , `Single` o `Double` )</span><span class="sxs-lookup"><span data-stu-id="871f3-128">Both expressions are numeric data types (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, or `Double`)</span></span>|<span data-ttu-id="871f3-129">Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="871f3-129">Add.</span></span> <span data-ttu-id="871f3-130">Il tipo di dati del risultato è un tipo numerico appropriato per i tipi di dati di `expression1` e `expression2` .</span><span class="sxs-lookup"><span data-stu-id="871f3-130">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="871f3-131">Vedere le tabelle "aritmetiche di interi" nei [tipi di dati dei risultati dell'operatore](data-types-of-operator-results.md).</span><span class="sxs-lookup"><span data-stu-id="871f3-131">See the "Integer Arithmetic" tables in [Data Types of Operator Results](data-types-of-operator-results.md).</span></span>|  
|<span data-ttu-id="871f3-132">Entrambe le espressioni sono di tipo`String`</span><span class="sxs-lookup"><span data-stu-id="871f3-132">Both expressions are of type `String`</span></span>|<span data-ttu-id="871f3-133">Concatenare.</span><span class="sxs-lookup"><span data-stu-id="871f3-133">Concatenate.</span></span>|  
|<span data-ttu-id="871f3-134">Un'espressione è un tipo di dati numerico e l'altra è una stringa</span><span class="sxs-lookup"><span data-stu-id="871f3-134">One expression is a numeric data type and the other is a string</span></span>|<span data-ttu-id="871f3-135">Se `Option Strict` è `On` , genera un errore del compilatore.</span><span class="sxs-lookup"><span data-stu-id="871f3-135">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="871f3-136">Se `Option Strict` è `Off` , convertire in modo implicito `String` in `Double` e aggiungere.</span><span class="sxs-lookup"><span data-stu-id="871f3-136">If `Option Strict` is `Off`, then implicitly convert the `String` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="871f3-137">Se `String` non può essere convertito in `Double` , viene generata un' <xref:System.InvalidCastException> eccezione.</span><span class="sxs-lookup"><span data-stu-id="871f3-137">If the `String` cannot be converted to `Double`, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
|<span data-ttu-id="871f3-138">Un'espressione è un tipo di dati numerico e l'altra [non è nulla](../nothing.md)</span><span class="sxs-lookup"><span data-stu-id="871f3-138">One expression is a numeric data type, and the other is [Nothing](../nothing.md)</span></span>|<span data-ttu-id="871f3-139">Aggiungere, con `Nothing` valore pari a zero.</span><span class="sxs-lookup"><span data-stu-id="871f3-139">Add, with `Nothing` valued as zero.</span></span>|  
|<span data-ttu-id="871f3-140">Un'espressione è una stringa e l'altra è`Nothing`</span><span class="sxs-lookup"><span data-stu-id="871f3-140">One expression is a string, and the other is `Nothing`</span></span>|<span data-ttu-id="871f3-141">Concatenate, con `Nothing` valore "".</span><span class="sxs-lookup"><span data-stu-id="871f3-141">Concatenate, with `Nothing` valued as "".</span></span>|  
  
 <span data-ttu-id="871f3-142">Se un'espressione è un' `Object` espressione, Visual Basic esegue le azioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="871f3-142">If one expression is an `Object` expression, Visual Basic takes the following actions.</span></span>  
  
|<span data-ttu-id="871f3-143">Tipi di dati delle espressioni</span><span class="sxs-lookup"><span data-stu-id="871f3-143">Data types of expressions</span></span>|<span data-ttu-id="871f3-144">Azione per compilatore</span><span class="sxs-lookup"><span data-stu-id="871f3-144">Action by compiler</span></span>|  
|---|---|  
|<span data-ttu-id="871f3-145">`Object`l'espressione include un valore numerico e l'altro è un tipo di dati numerico</span><span class="sxs-lookup"><span data-stu-id="871f3-145">`Object` expression holds a numeric value and the other is a numeric data type</span></span>|<span data-ttu-id="871f3-146">Se `Option Strict` è `On` , genera un errore del compilatore.</span><span class="sxs-lookup"><span data-stu-id="871f3-146">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="871f3-147">Se `Option Strict` è `Off` , aggiungere.</span><span class="sxs-lookup"><span data-stu-id="871f3-147">If `Option Strict` is `Off`, then add.</span></span>|  
|<span data-ttu-id="871f3-148">`Object`l'espressione include un valore numerico e l'altro è di tipo`String`</span><span class="sxs-lookup"><span data-stu-id="871f3-148">`Object` expression holds a numeric value and the other is of type `String`</span></span>|<span data-ttu-id="871f3-149">Se `Option Strict` è `On` , genera un errore del compilatore.</span><span class="sxs-lookup"><span data-stu-id="871f3-149">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="871f3-150">Se `Option Strict` è `Off` , convertire in modo implicito `String` in `Double` e aggiungere.</span><span class="sxs-lookup"><span data-stu-id="871f3-150">If `Option Strict` is `Off`, then implicitly convert the `String` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="871f3-151">Se `String` non può essere convertito in `Double` , viene generata un' <xref:System.InvalidCastException> eccezione.</span><span class="sxs-lookup"><span data-stu-id="871f3-151">If the `String` cannot be converted to `Double`, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
|<span data-ttu-id="871f3-152">`Object`l'espressione include una stringa e l'altra è un tipo di dati numerico</span><span class="sxs-lookup"><span data-stu-id="871f3-152">`Object` expression holds a string and the other is a numeric data type</span></span>|<span data-ttu-id="871f3-153">Se `Option Strict` è `On` , genera un errore del compilatore.</span><span class="sxs-lookup"><span data-stu-id="871f3-153">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="871f3-154">Se `Option Strict` è `Off` , convertire in modo implicito la stringa `Object` in `Double` e aggiungere.</span><span class="sxs-lookup"><span data-stu-id="871f3-154">If `Option Strict` is `Off`, then implicitly convert the string `Object` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="871f3-155">Se la stringa `Object` non può essere convertita in `Double` , viene generata un' <xref:System.InvalidCastException> eccezione.</span><span class="sxs-lookup"><span data-stu-id="871f3-155">If the string `Object` cannot be converted to `Double`, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
|<span data-ttu-id="871f3-156">`Object`l'espressione include una stringa e l'altra è di tipo`String`</span><span class="sxs-lookup"><span data-stu-id="871f3-156">`Object` expression holds a string and the other is of type `String`</span></span>|<span data-ttu-id="871f3-157">Se `Option Strict` è `On` , genera un errore del compilatore.</span><span class="sxs-lookup"><span data-stu-id="871f3-157">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="871f3-158">Se `Option Strict` è `Off` , convertire in modo implicito `Object` in `String` e concatenare.</span><span class="sxs-lookup"><span data-stu-id="871f3-158">If `Option Strict` is `Off`, then implicitly convert `Object` to `String` and concatenate.</span></span>|  
  
 <span data-ttu-id="871f3-159">Se entrambe le espressioni sono `Object` espressioni, Visual Basic esegue le azioni seguenti ( `Option Strict Off` solo).</span><span class="sxs-lookup"><span data-stu-id="871f3-159">If both expressions are `Object` expressions, Visual Basic takes the following actions (`Option Strict Off` only).</span></span>  
  
|<span data-ttu-id="871f3-160">Tipi di dati delle espressioni</span><span class="sxs-lookup"><span data-stu-id="871f3-160">Data types of expressions</span></span>|<span data-ttu-id="871f3-161">Azione per compilatore</span><span class="sxs-lookup"><span data-stu-id="871f3-161">Action by compiler</span></span>|  
|---|---|  
|<span data-ttu-id="871f3-162">Entrambe le `Object` espressioni contengono valori numerici</span><span class="sxs-lookup"><span data-stu-id="871f3-162">Both `Object` expressions hold numeric values</span></span>|<span data-ttu-id="871f3-163">Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="871f3-163">Add.</span></span>|  
|<span data-ttu-id="871f3-164">Entrambe `Object` le espressioni sono di tipo`String`</span><span class="sxs-lookup"><span data-stu-id="871f3-164">Both `Object` expressions are of type `String`</span></span>|<span data-ttu-id="871f3-165">Concatenare.</span><span class="sxs-lookup"><span data-stu-id="871f3-165">Concatenate.</span></span>|  
|<span data-ttu-id="871f3-166">Un' `Object` espressione include un valore numerico e l'altra include una stringa</span><span class="sxs-lookup"><span data-stu-id="871f3-166">One `Object` expression holds a numeric value and the other holds a string</span></span>|<span data-ttu-id="871f3-167">Converte in modo implicito la stringa `Object` in `Double` e Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="871f3-167">Implicitly convert the string `Object` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="871f3-168">Se la stringa `Object` non può essere convertita in un valore numerico, viene generata un' <xref:System.InvalidCastException> eccezione.</span><span class="sxs-lookup"><span data-stu-id="871f3-168">If the string `Object` cannot be converted to a numeric value, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
  
 <span data-ttu-id="871f3-169">Se una `Object` delle due espressioni restituisce [Nothing](../nothing.md) o <xref:System.DBNull> , l' `+` operatore lo considera come `String` con un valore di "".</span><span class="sxs-lookup"><span data-stu-id="871f3-169">If either `Object` expression evaluates to [Nothing](../nothing.md) or <xref:System.DBNull>, the `+` operator treats it as a `String` with a value of "".</span></span>  
  
> [!NOTE]
> <span data-ttu-id="871f3-170">Quando si utilizza l' `+` operatore, potrebbe non essere possibile determinare se si verificherà l'aggiunta o la concatenazione di stringhe.</span><span class="sxs-lookup"><span data-stu-id="871f3-170">When you use the `+` operator, you might not be able to determine whether addition or string concatenation will occur.</span></span> <span data-ttu-id="871f3-171">Usare l' `&` operatore per la concatenazione per eliminare l'ambiguità e per fornire codice autodocumentato.</span><span class="sxs-lookup"><span data-stu-id="871f3-171">Use the `&` operator for concatenation to eliminate ambiguity and to provide self-documenting code.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="871f3-172">Overload</span><span class="sxs-lookup"><span data-stu-id="871f3-172">Overloading</span></span>  
 <span data-ttu-id="871f3-173">L' `+` operatore può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="871f3-173">The `+` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="871f3-174">Se il codice usa questo operatore su una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="871f3-174">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="871f3-175">Per altre informazioni, vedere [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="871f3-175">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="871f3-176">Esempio</span><span class="sxs-lookup"><span data-stu-id="871f3-176">Example</span></span>  
 <span data-ttu-id="871f3-177">Nell'esempio seguente viene usato l' `+` operatore per aggiungere numeri.</span><span class="sxs-lookup"><span data-stu-id="871f3-177">The following example uses the `+` operator to add numbers.</span></span> <span data-ttu-id="871f3-178">Se gli operandi sono entrambi numerici, Visual Basic calcola il risultato aritmetico.</span><span class="sxs-lookup"><span data-stu-id="871f3-178">If the operands are both numeric, Visual Basic computes the arithmetic result.</span></span> <span data-ttu-id="871f3-179">Il risultato aritmetico rappresenta la somma dei due operandi.</span><span class="sxs-lookup"><span data-stu-id="871f3-179">The arithmetic result represents the sum of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#6)]  
  
 <span data-ttu-id="871f3-180">È anche possibile usare l' `+` operatore per concatenare le stringhe.</span><span class="sxs-lookup"><span data-stu-id="871f3-180">You can also use the `+` operator to concatenate strings.</span></span> <span data-ttu-id="871f3-181">Se gli operandi sono entrambe stringhe, Visual Basic li concatena.</span><span class="sxs-lookup"><span data-stu-id="871f3-181">If the operands are both strings, Visual Basic concatenates them.</span></span> <span data-ttu-id="871f3-182">Il risultato della concatenazione rappresenta una singola stringa costituita dal contenuto dei due operandi uno dopo l'altro.</span><span class="sxs-lookup"><span data-stu-id="871f3-182">The concatenation result represents a single string consisting of the contents of the two operands one after the other.</span></span>  
  
 <span data-ttu-id="871f3-183">Se gli operandi sono di tipo misto, il risultato dipende dall'impostazione dell' [istruzione Option Strict](../statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="871f3-183">If the operands are of mixed types, the result depends on the setting of the [Option Strict Statement](../statements/option-strict-statement.md).</span></span> <span data-ttu-id="871f3-184">Nell'esempio seguente viene illustrato il risultato quando `Option Strict` è `On` .</span><span class="sxs-lookup"><span data-stu-id="871f3-184">The following example illustrates the result when `Option Strict` is `On`.</span></span>  
  
 [!code-vb[VbVbalrOperators#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class3.vb#53)]  
  
 [!code-vb[VbVbalrOperators#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#50)]  
[!code-vb[VbVbalrOperators#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#51)]  
  
 <span data-ttu-id="871f3-185">Nell'esempio seguente viene illustrato il risultato quando `Option Strict` è `Off` .</span><span class="sxs-lookup"><span data-stu-id="871f3-185">The following example illustrates the result when `Option Strict` is `Off`.</span></span>  
  
 [!code-vb[VbVbalrOperators#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#54)]  
  
 [!code-vb[VbVbalrOperators#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#50)]  
[!code-vb[VbVbalrOperators#52](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#52)]  
  
 <span data-ttu-id="871f3-186">Per eliminare l'ambiguità, è consigliabile utilizzare l' `&` operatore anziché `+` per la concatenazione.</span><span class="sxs-lookup"><span data-stu-id="871f3-186">To eliminate ambiguity, you should use the `&` operator instead of `+` for concatenation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="871f3-187">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="871f3-187">See also</span></span>

- [<span data-ttu-id="871f3-188">Operatore&</span><span class="sxs-lookup"><span data-stu-id="871f3-188">& Operator</span></span>](concatenation-operator.md)
- [<span data-ttu-id="871f3-189">Operatori di concatenazione</span><span class="sxs-lookup"><span data-stu-id="871f3-189">Concatenation Operators</span></span>](concatenation-operators.md)
- [<span data-ttu-id="871f3-190">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="871f3-190">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="871f3-191">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="871f3-191">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="871f3-192">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="871f3-192">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="871f3-193">Operatori aritmetici in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="871f3-193">Arithmetic Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [<span data-ttu-id="871f3-194">Option Strict Statement</span><span class="sxs-lookup"><span data-stu-id="871f3-194">Option Strict Statement</span></span>](../statements/option-strict-statement.md)
