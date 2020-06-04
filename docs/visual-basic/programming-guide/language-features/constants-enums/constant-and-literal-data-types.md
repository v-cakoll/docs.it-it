---
title: Tipi di dati costanti e letterali
ms.date: 07/20/2015
helpviewer_keywords:
- declaring constants [Visual Basic], literal data types
- data types [Visual Basic], declaring
- constants [Visual Basic], declaring
- explicit declarations
- literals [Visual Basic], coercing data type
- declarations [Visual Basic], data types
ms.assetid: 057206d2-3a5b-40b9-b3af-57446f9b52fa
ms.openlocfilehash: b94259326b42104db05d9fc5bb09f686075d0759
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414531"
---
# <a name="constant-and-literal-data-types-visual-basic"></a><span data-ttu-id="3e429-102">Tipi di dati costanti e letterali (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3e429-102">Constant and Literal Data Types (Visual Basic)</span></span>
<span data-ttu-id="3e429-103">Un valore letterale è un valore espresso come se stesso anziché come valore di una variabile oppure il risultato di un'espressione, ad esempio il numero 3 o la stringa "Hello".</span><span class="sxs-lookup"><span data-stu-id="3e429-103">A literal is a value that is expressed as itself rather than as a variable's value or the result of an expression, such as the number 3 or the string "Hello".</span></span> <span data-ttu-id="3e429-104">Una costante è un nome significativo che prende il posto di un valore letterale e mantiene lo stesso valore in tutto il programma, anziché una variabile, il cui valore può cambiare.</span><span class="sxs-lookup"><span data-stu-id="3e429-104">A constant is a meaningful name that takes the place of a literal and retains this same value throughout the program, as opposed to a variable, whose value may change.</span></span>  
  
 <span data-ttu-id="3e429-105">Quando [Option deduce](../../../language-reference/statements/option-infer-statement.md) è `Off` e [Option Strict](../../../language-reference/statements/option-strict-statement.md) è `On` , è necessario dichiarare in modo esplicito tutte le costanti con un tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="3e429-105">When [Option Infer](../../../language-reference/statements/option-infer-statement.md) is `Off` and [Option Strict](../../../language-reference/statements/option-strict-statement.md) is `On`, you must declare all constants explicitly with a data type.</span></span> <span data-ttu-id="3e429-106">Nell'esempio seguente il tipo di dati di `MyByte` viene dichiarato in modo esplicito come tipo di dati `Byte` :</span><span class="sxs-lookup"><span data-stu-id="3e429-106">In the following example, the data type of `MyByte` is explicitly declared as data type `Byte`:</span></span>  
  
 [!code-vb[VbVbalrConstants#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#1)]  
  
 <span data-ttu-id="3e429-107">Quando `Option Infer` è `On` o `Option Strict` è `Off` , è possibile dichiarare una costante senza specificare un tipo di dati con una `As` clausola.</span><span class="sxs-lookup"><span data-stu-id="3e429-107">When `Option Infer` is `On` or `Option Strict` is `Off`, you can declare a constant without specifying a data type with an `As` clause.</span></span> <span data-ttu-id="3e429-108">Il compilatore determina il tipo della costante dal tipo dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="3e429-108">The compiler determines the type of the constant from the type of the expression.</span></span> <span data-ttu-id="3e429-109">Per impostazione predefinita, viene eseguito il cast di un valore letterale integer numerico al `Integer` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="3e429-109">A numeric integer literal is cast by default to the `Integer` data type.</span></span> <span data-ttu-id="3e429-110">Il tipo di dati predefinito per i numeri a virgola mobile è `Double` e le parole chiave `True` e `False` specificano una `Boolean` costante.</span><span class="sxs-lookup"><span data-stu-id="3e429-110">The default data type for floating-point numbers is `Double`, and the keywords `True` and `False` specify a `Boolean` constant.</span></span>  
  
## <a name="literals-and-type-coercion"></a><span data-ttu-id="3e429-111">Valori letterali e coercizione del tipo</span><span class="sxs-lookup"><span data-stu-id="3e429-111">Literals and Type Coercion</span></span>  
 <span data-ttu-id="3e429-112">In alcuni casi, potrebbe essere necessario forzare un valore letterale in un tipo di dati specifico. ad esempio, quando si assegna un valore letterale integrale particolarmente grande a una variabile di tipo `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="3e429-112">In some cases, you might want to force a literal to a particular data type; for example, when assigning a particularly large integral literal value to a variable of type `Decimal`.</span></span> <span data-ttu-id="3e429-113">Nell'esempio seguente viene generato un errore:</span><span class="sxs-lookup"><span data-stu-id="3e429-113">The following example produces an error:</span></span>  
  
```vb  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 <span data-ttu-id="3e429-114">Errore risultante dalla rappresentazione del valore letterale.</span><span class="sxs-lookup"><span data-stu-id="3e429-114">The error results from the representation of the literal.</span></span> <span data-ttu-id="3e429-115">Il `Decimal` tipo di dati può avere un valore di questo tipo, ma il valore letterale viene rappresentato in modo implicito come `Long` , che non può.</span><span class="sxs-lookup"><span data-stu-id="3e429-115">The `Decimal` data type can hold a value this large, but the literal is implicitly represented as a `Long`, which cannot.</span></span>  
  
 <span data-ttu-id="3e429-116">È possibile assegnare un valore letterale a un particolare tipo di dati in due modi: aggiungendovi un carattere di tipo o inserendolo all'interno di caratteri di inclusione.</span><span class="sxs-lookup"><span data-stu-id="3e429-116">You can coerce a literal to a particular data type in two ways: by appending a type character to it, or by placing it within enclosing characters.</span></span> <span data-ttu-id="3e429-117">Un carattere di tipo o caratteri di inclusione devono immediatamente precedere e/o seguire il valore letterale, senza spazi o caratteri di qualsiasi tipo.</span><span class="sxs-lookup"><span data-stu-id="3e429-117">A type character or enclosing characters must immediately precede and/or follow the literal, with no intervening space or characters of any kind.</span></span>  
  
 <span data-ttu-id="3e429-118">Per far funzionare l'esempio precedente, è possibile aggiungere il `D` carattere tipo al valore letterale, che ne determina la rappresentazione come `Decimal` :</span><span class="sxs-lookup"><span data-stu-id="3e429-118">To make the previous example work, you can append the `D` type character to the literal, which causes it to be represented as a `Decimal`:</span></span>  
  
 [!code-vb[VbVbalrConstants#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#2)]  
  
 <span data-ttu-id="3e429-119">Nell'esempio seguente viene illustrato il corretto utilizzo di caratteri di tipo e caratteri di inclusione:</span><span class="sxs-lookup"><span data-stu-id="3e429-119">The following example demonstrates correct usage of type characters and enclosing characters:</span></span>  
  
 [!code-vb[VbVbalrConstants#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#3)]  
  
 <span data-ttu-id="3e429-120">Nella tabella seguente vengono illustrati i caratteri di inclusione e i caratteri di tipo disponibili in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="3e429-120">The following table shows the enclosing characters and type characters available in Visual Basic.</span></span>  
  
|<span data-ttu-id="3e429-121">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="3e429-121">Data type</span></span>|<span data-ttu-id="3e429-122">Carattere di inclusione</span><span class="sxs-lookup"><span data-stu-id="3e429-122">Enclosing character</span></span>|<span data-ttu-id="3e429-123">Carattere tipo aggiunto</span><span class="sxs-lookup"><span data-stu-id="3e429-123">Appended type character</span></span>|  
|---|---|---|  
|`Boolean`|<span data-ttu-id="3e429-124">(nessuna)</span><span class="sxs-lookup"><span data-stu-id="3e429-124">(none)</span></span>|<span data-ttu-id="3e429-125">(nessuna)</span><span class="sxs-lookup"><span data-stu-id="3e429-125">(none)</span></span>|  
|`Byte`|<span data-ttu-id="3e429-126">(nessuna)</span><span class="sxs-lookup"><span data-stu-id="3e429-126">(none)</span></span>|<span data-ttu-id="3e429-127">(nessuna)</span><span class="sxs-lookup"><span data-stu-id="3e429-127">(none)</span></span>|  
|`Char`|<span data-ttu-id="3e429-128">"</span><span class="sxs-lookup"><span data-stu-id="3e429-128">"</span></span>|<span data-ttu-id="3e429-129">C</span><span class="sxs-lookup"><span data-stu-id="3e429-129">C</span></span>|  
|`Date`|#|<span data-ttu-id="3e429-130">(nessuna)</span><span class="sxs-lookup"><span data-stu-id="3e429-130">(none)</span></span>|  
|`Decimal`|<span data-ttu-id="3e429-131">(nessuna)</span><span class="sxs-lookup"><span data-stu-id="3e429-131">(none)</span></span>|<span data-ttu-id="3e429-132">D o @</span><span class="sxs-lookup"><span data-stu-id="3e429-132">D or @</span></span>|  
|`Double`|<span data-ttu-id="3e429-133">(nessuna)</span><span class="sxs-lookup"><span data-stu-id="3e429-133">(none)</span></span>|<span data-ttu-id="3e429-134">R o #</span><span class="sxs-lookup"><span data-stu-id="3e429-134">R or #</span></span>|  
|`Integer`|<span data-ttu-id="3e429-135">(nessuna)</span><span class="sxs-lookup"><span data-stu-id="3e429-135">(none)</span></span>|<span data-ttu-id="3e429-136">I o%</span><span class="sxs-lookup"><span data-stu-id="3e429-136">I or %</span></span>|  
|`Long`|<span data-ttu-id="3e429-137">(nessuna)</span><span class="sxs-lookup"><span data-stu-id="3e429-137">(none)</span></span>|<span data-ttu-id="3e429-138">L o &</span><span class="sxs-lookup"><span data-stu-id="3e429-138">L or &</span></span>|  
|`Short`|<span data-ttu-id="3e429-139">(nessuna)</span><span class="sxs-lookup"><span data-stu-id="3e429-139">(none)</span></span>|<span data-ttu-id="3e429-140">S</span><span class="sxs-lookup"><span data-stu-id="3e429-140">S</span></span>|  
|`Single`|<span data-ttu-id="3e429-141">(nessuna)</span><span class="sxs-lookup"><span data-stu-id="3e429-141">(none)</span></span>|<span data-ttu-id="3e429-142">F o!</span><span class="sxs-lookup"><span data-stu-id="3e429-142">F or !</span></span>|  
|`String`|<span data-ttu-id="3e429-143">"</span><span class="sxs-lookup"><span data-stu-id="3e429-143">"</span></span>|<span data-ttu-id="3e429-144">(nessuna)</span><span class="sxs-lookup"><span data-stu-id="3e429-144">(none)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3e429-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e429-145">See also</span></span>

- [<span data-ttu-id="3e429-146">Costanti definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="3e429-146">User-Defined Constants</span></span>](user-defined-constants.md)
- [<span data-ttu-id="3e429-147">Procedura: dichiarare una costante</span><span class="sxs-lookup"><span data-stu-id="3e429-147">How to: Declare A Constant</span></span>](how-to-declare-a-constant.md)
- [<span data-ttu-id="3e429-148">Cenni preliminari sulle costanti</span><span class="sxs-lookup"><span data-stu-id="3e429-148">Constants Overview</span></span>](constants-overview.md)
- [<span data-ttu-id="3e429-149">Option Strict Statement</span><span class="sxs-lookup"><span data-stu-id="3e429-149">Option Strict Statement</span></span>](../../../language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="3e429-150">Istruzione Option Explicit</span><span class="sxs-lookup"><span data-stu-id="3e429-150">Option Explicit Statement</span></span>](../../../language-reference/statements/option-explicit-statement.md)
- [<span data-ttu-id="3e429-151">Cenni preliminari sulle enumerazioni</span><span class="sxs-lookup"><span data-stu-id="3e429-151">Enumerations Overview</span></span>](enumerations-overview.md)
- [<span data-ttu-id="3e429-152">Procedura: dichiarare un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="3e429-152">How to: Declare an Enumeration</span></span>](how-to-declare-enumerations.md)
- [<span data-ttu-id="3e429-153">Qualifica di nomi ed enumerazioni</span><span class="sxs-lookup"><span data-stu-id="3e429-153">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="3e429-154">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="3e429-154">Data Types</span></span>](../../../language-reference/data-types/index.md)
- [<span data-ttu-id="3e429-155">Costanti ed enumerazioni</span><span class="sxs-lookup"><span data-stu-id="3e429-155">Constants and Enumerations</span></span>](../../../language-reference/constants-and-enumerations.md)
