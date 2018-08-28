---
title: Tipi di dati costanti e letterali (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declaring constants [Visual Basic], literal data types
- data types [Visual Basic], declaring
- constants [Visual Basic], declaring
- explicit declarations
- literals [Visual Basic], coercing data type
- declarations [Visual Basic], data types
ms.assetid: 057206d2-3a5b-40b9-b3af-57446f9b52fa
ms.openlocfilehash: 1d030f8058cd497212c20bca8f064f2bedc99fce
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "42999927"
---
# <a name="constant-and-literal-data-types-visual-basic"></a><span data-ttu-id="e8248-102">Tipi di dati costanti e letterali (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e8248-102">Constant and Literal Data Types (Visual Basic)</span></span>
<span data-ttu-id="e8248-103">Un valore letterale è un valore espresso come se stessa anziché come valore di una variabile o il risultato di un'espressione, ad esempio il numero 3 oppure la stringa "Hello".</span><span class="sxs-lookup"><span data-stu-id="e8248-103">A literal is a value that is expressed as itself rather than as a variable's value or the result of an expression, such as the number 3 or the string "Hello".</span></span> <span data-ttu-id="e8248-104">Una costante è un nome significativo che prende il posto di un valore letterale e mantiene lo stesso valore in tutto il programma, a differenza di una variabile, il cui valore può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="e8248-104">A constant is a meaningful name that takes the place of a literal and retains this same value throughout the program, as opposed to a variable, whose value may change.</span></span>  
  
 <span data-ttu-id="e8248-105">Quando [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) viene `Off` e [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) è `On`, è necessario dichiarare in modo esplicito tutte le costanti con un tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="e8248-105">When [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) is `Off` and [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) is `On`, you must declare all constants explicitly with a data type.</span></span> <span data-ttu-id="e8248-106">Nell'esempio seguente, il tipo di dati `MyByte` viene dichiarato in modo esplicito come tipo di dati `Byte`:</span><span class="sxs-lookup"><span data-stu-id="e8248-106">In the following example, the data type of `MyByte` is explicitly declared as data type `Byte`:</span></span>  
  
 [!code-vb[VbVbalrConstants#1](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_1.vb)]  
  
 <span data-ttu-id="e8248-107">Quando `Option Infer` viene `On` oppure `Option Strict` viene `Off`, è possibile dichiarare una costante senza specificare un tipo di dati con un `As` clausola.</span><span class="sxs-lookup"><span data-stu-id="e8248-107">When `Option Infer` is `On` or `Option Strict` is `Off`, you can declare a constant without specifying a data type with an `As` clause.</span></span> <span data-ttu-id="e8248-108">Il compilatore determina il tipo della costante dal tipo dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="e8248-108">The compiler determines the type of the constant from the type of the expression.</span></span> <span data-ttu-id="e8248-109">Viene eseguito il cast di un valore letterale integer numerico per impostazione predefinita per il `Integer` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="e8248-109">A numeric integer literal is cast by default to the `Integer` data type.</span></span> <span data-ttu-id="e8248-110">Tipo di dati predefinito per numeri a virgola mobile sono `Double`e le parole chiave `True` e `False` specificare un `Boolean` costante.</span><span class="sxs-lookup"><span data-stu-id="e8248-110">The default data type for floating-point numbers is `Double`, and the keywords `True` and `False` specify a `Boolean` constant.</span></span>  
  
## <a name="literals-and-type-coercion"></a><span data-ttu-id="e8248-111">Valori letterali e coercizione dei tipi</span><span class="sxs-lookup"><span data-stu-id="e8248-111">Literals and Type Coercion</span></span>  
 <span data-ttu-id="e8248-112">In alcuni casi, è possibile forzare un valore letterale per un particolare tipo di dati; ad esempio, quando si assegna un valore letterale integrale particolarmente elevato a una variabile di tipo `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="e8248-112">In some cases, you might want to force a literal to a particular data type; for example, when assigning a particularly large integral literal value to a variable of type `Decimal`.</span></span> <span data-ttu-id="e8248-113">Nell'esempio seguente genera un errore:</span><span class="sxs-lookup"><span data-stu-id="e8248-113">The following example produces an error:</span></span>  
  
```  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 <span data-ttu-id="e8248-114">L'errore deriva dalla rappresentazione del valore letterale.</span><span class="sxs-lookup"><span data-stu-id="e8248-114">The error results from the representation of the literal.</span></span> <span data-ttu-id="e8248-115">Il `Decimal` tipo di dati può contenere un valore così elevato, ma il valore letterale è rappresentato in modo implicito come una `Long`, che non è possibile.</span><span class="sxs-lookup"><span data-stu-id="e8248-115">The `Decimal` data type can hold a value this large, but the literal is implicitly represented as a `Long`, which cannot.</span></span>  
  
 <span data-ttu-id="e8248-116">È possibile assegnare un valore letterale in un particolare tipo di dati in due modi: aggiungendo un carattere tipo oppure inserendoli all'interno di caratteri di inclusione.</span><span class="sxs-lookup"><span data-stu-id="e8248-116">You can coerce a literal to a particular data type in two ways: by appending a type character to it, or by placing it within enclosing characters.</span></span> <span data-ttu-id="e8248-117">Un carattere o racchiudere i caratteri deve immediatamente preceduto e/o seguire il valore letterale, senza spazi o caratteri di qualsiasi tipo.</span><span class="sxs-lookup"><span data-stu-id="e8248-117">A type character or enclosing characters must immediately precede and/or follow the literal, with no intervening space or characters of any kind.</span></span>  
  
 <span data-ttu-id="e8248-118">Per garantire il funzionamento dell'esempio precedente, è possibile aggiungere il `D` tipo di carattere per il valore letterale, in modo che essere rappresentato come un `Decimal`:</span><span class="sxs-lookup"><span data-stu-id="e8248-118">To make the previous example work, you can append the `D` type character to the literal, which causes it to be represented as a `Decimal`:</span></span>  
  
 [!code-vb[VbVbalrConstants#2](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_2.vb)]  
  
 <span data-ttu-id="e8248-119">Nell'esempio seguente illustra l'uso corretto di caratteri che la contiene e caratteri di tipo:</span><span class="sxs-lookup"><span data-stu-id="e8248-119">The following example demonstrates correct usage of type characters and enclosing characters:</span></span>  
  
 [!code-vb[VbVbalrConstants#3](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_3.vb)]  
  
 <span data-ttu-id="e8248-120">La seguente tabella mostra i caratteri che la contiene e i caratteri di tipo disponibili in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e8248-120">The following table shows the enclosing characters and type characters available in Visual Basic.</span></span>  
  
|<span data-ttu-id="e8248-121">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="e8248-121">Data type</span></span>|<span data-ttu-id="e8248-122">Carattere di inclusione</span><span class="sxs-lookup"><span data-stu-id="e8248-122">Enclosing character</span></span>|<span data-ttu-id="e8248-123">Carattere di tipo accodati</span><span class="sxs-lookup"><span data-stu-id="e8248-123">Appended type character</span></span>|  
|---|---|---|  
|`Boolean`|<span data-ttu-id="e8248-124">(nessuno)</span><span class="sxs-lookup"><span data-stu-id="e8248-124">(none)</span></span>|<span data-ttu-id="e8248-125">(nessuno)</span><span class="sxs-lookup"><span data-stu-id="e8248-125">(none)</span></span>|  
|`Byte`|<span data-ttu-id="e8248-126">(nessuno)</span><span class="sxs-lookup"><span data-stu-id="e8248-126">(none)</span></span>|<span data-ttu-id="e8248-127">(nessuno)</span><span class="sxs-lookup"><span data-stu-id="e8248-127">(none)</span></span>|  
|`Char`|<span data-ttu-id="e8248-128">"</span><span class="sxs-lookup"><span data-stu-id="e8248-128">"</span></span>|<span data-ttu-id="e8248-129">C</span><span class="sxs-lookup"><span data-stu-id="e8248-129">C</span></span>|  
|`Date`|#|<span data-ttu-id="e8248-130">(nessuno)</span><span class="sxs-lookup"><span data-stu-id="e8248-130">(none)</span></span>|  
|`Decimal`|<span data-ttu-id="e8248-131">(nessuno)</span><span class="sxs-lookup"><span data-stu-id="e8248-131">(none)</span></span>|<span data-ttu-id="e8248-132">1!d oppure @</span><span class="sxs-lookup"><span data-stu-id="e8248-132">D or @</span></span>|  
|`Double`|<span data-ttu-id="e8248-133">(nessuno)</span><span class="sxs-lookup"><span data-stu-id="e8248-133">(none)</span></span>|<span data-ttu-id="e8248-134">R o n</span><span class="sxs-lookup"><span data-stu-id="e8248-134">R or #</span></span>|  
|`Integer`|<span data-ttu-id="e8248-135">(nessuno)</span><span class="sxs-lookup"><span data-stu-id="e8248-135">(none)</span></span>|<span data-ttu-id="e8248-136">I o %</span><span class="sxs-lookup"><span data-stu-id="e8248-136">I or %</span></span>|  
|`Long`|<span data-ttu-id="e8248-137">(nessuno)</span><span class="sxs-lookup"><span data-stu-id="e8248-137">(none)</span></span>|<span data-ttu-id="e8248-138">L o &</span><span class="sxs-lookup"><span data-stu-id="e8248-138">L or &</span></span>|  
|`Short`|<span data-ttu-id="e8248-139">(nessuno)</span><span class="sxs-lookup"><span data-stu-id="e8248-139">(none)</span></span>|<span data-ttu-id="e8248-140">S</span><span class="sxs-lookup"><span data-stu-id="e8248-140">S</span></span>|  
|`Single`|<span data-ttu-id="e8248-141">(nessuno)</span><span class="sxs-lookup"><span data-stu-id="e8248-141">(none)</span></span>|<span data-ttu-id="e8248-142">F o!</span><span class="sxs-lookup"><span data-stu-id="e8248-142">F or !</span></span>|  
|`String`|<span data-ttu-id="e8248-143">"</span><span class="sxs-lookup"><span data-stu-id="e8248-143">"</span></span>|<span data-ttu-id="e8248-144">(nessuno)</span><span class="sxs-lookup"><span data-stu-id="e8248-144">(none)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e8248-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8248-145">See Also</span></span>  
 [<span data-ttu-id="e8248-146">Costanti definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="e8248-146">User-Defined Constants</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)  
 [<span data-ttu-id="e8248-147">Procedura: Dichiarare una costante</span><span class="sxs-lookup"><span data-stu-id="e8248-147">How to: Declare A Constant</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)  
 [<span data-ttu-id="e8248-148">Cenni preliminari sulle costanti</span><span class="sxs-lookup"><span data-stu-id="e8248-148">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)  
 [<span data-ttu-id="e8248-149">Istruzione Option Strict</span><span class="sxs-lookup"><span data-stu-id="e8248-149">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="e8248-150">Istruzione Option Explicit</span><span class="sxs-lookup"><span data-stu-id="e8248-150">Option Explicit Statement</span></span>](../../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [<span data-ttu-id="e8248-151">Cenni preliminari sulle enumerazioni</span><span class="sxs-lookup"><span data-stu-id="e8248-151">Enumerations Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)  
 [<span data-ttu-id="e8248-152">Procedura: dichiarare un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="e8248-152">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [<span data-ttu-id="e8248-153">Qualifica di nomi ed enumerazioni</span><span class="sxs-lookup"><span data-stu-id="e8248-153">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [<span data-ttu-id="e8248-154">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="e8248-154">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)  
 [<span data-ttu-id="e8248-155">Costanti ed enumerazioni</span><span class="sxs-lookup"><span data-stu-id="e8248-155">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
